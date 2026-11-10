# Sequence diagrams — BA/SA reference

Use a sequence diagram when the main question is **which actor or system calls which component, in what order, and how the result is returned or processed**. This is not a replacement for a workflow diagram, a database ERD, or an API contract.

## Before drawing

Gather as much of the following as the available evidence supports: business event, actors, system boundary, endpoint and method, payload, authentication, validation, database operation, state update, response, error paths, and retry policy. For external integrations, also check idempotency, callback/webhook, status inquiry, and reconciliation.

If a contract is missing, label proposed behavior and mark the endpoint `Need Confirmation`. Do not invent a real-looking production URL.

## Notation

| Element | Use |
|---|---|
| `actor` | Human user or business role |
| `participant` | Frontend, API, DB, queue, service |
| `->>` | Request/message |
| `-->>` | Response/acknowledgment |
| `alt / else` | Mutually exclusive paths |
| `opt` | Optional action |
| `loop` | Meaningful repetition or retry |
| `Note over` | Event timing, boundaries, or a short technical note |
| `autonumber` | Readable step numbering |

Distinguish synchronous calls from asynchronous callbacks. Avoid placing a webhook directly inside the original HTTP response flow.

## Example 1 — Submit, validation, save

```mermaid
sequenceDiagram
    autonumber
    actor User
    participant FE as Frontend
    participant API as Backend API
    participant DB as Database
    User->>FE: Fill form and click Submit
    FE->>API: POST /requests + payload
    API->>API: Validate fields and permission
    alt Validation error
        API-->>FE: Validation error response
        FE-->>User: Show field errors
    else Valid data
        API->>DB: Insert request
        alt Save failed
            DB-->>API: Database error
            API-->>FE: Failure response
            FE-->>User: Show failure
        else Save succeeded
            DB-->>API: Request ID
            API-->>FE: Created + Request ID
            FE-->>User: Show confirmation
        end
    end
```

For this example, no specific API contract has been supplied. The endpoint and status are illustrative only.

## Example 2 — Approval workflow

```mermaid
sequenceDiagram
    autonumber
    actor Staff
    participant App as Application
    participant DB as Database
    actor Approver
    Staff->>App: Submit request
    App->>App: Validate required data
    alt Invalid request
        App-->>Staff: Show validation error
    else Request valid
        App->>DB: Save Pending Approval
        DB-->>App: Request ID
        App-->>Staff: Show submission result
        Approver->>App: Open request
        App->>DB: Fetch latest status
        DB-->>App: Current record
        Approver->>App: Approve or Reject
        App->>App: Validate role and current status
        alt Unauthorized or status changed
            App-->>Approver: Reject action
        else Approve
            App->>DB: Save Approved
            DB-->>App: Success
            App-->>Approver: Show Approved
        else Reject
            App->>App: Require rejection reason
            App->>DB: Save Rejected and reason
            DB-->>App: Success
            App-->>Approver: Show Rejected
        end
    end
```

This diagram illustrates a possible design. Approval role, statuses, and validation rules must be confirmed in a real project.

## Example 3 — External API plus asynchronous webhook

```mermaid
sequenceDiagram
    autonumber
    actor User
    participant FE as Frontend
    participant BE as Backend
    participant DB as Database
    participant EXT as External Service
    participant WH as Webhook Handler
    User->>FE: Confirm operation
    FE->>BE: POST /operations
    BE->>DB: Save Pending operation
    DB-->>BE: Internal Operation ID
    BE->>EXT: Send operation + idempotency key
    alt External request acknowledged
        EXT-->>BE: Accepted + external reference
        BE->>DB: Store reference
        BE-->>FE: Pending operation
    else Timeout or ambiguous result
        BE->>DB: Mark Verification Required
        BE-->>FE: Pending verification
    end
    FE-->>User: Show processing state
    Note over EXT,WH: Later asynchronous event
    EXT->>WH: Send webhook event
    WH->>WH: Verify signature and event ID
    alt Signature invalid
        WH-->>EXT: Reject event
    else Event already processed
        WH-->>EXT: Acknowledge duplicate
    else New valid event
        WH->>DB: Store event and update status
        alt Database failure
            DB-->>WH: Error
            WH-->>EXT: Retryable failure
        else Stored successfully
            DB-->>WH: Commit successful
            WH-->>EXT: Acknowledge event
        end
    end
```

### Review checklist for external integration

1. Is the trigger and Source of Truth explicit?
2. Is the acknowledgment different from final business completion?
3. Are retry, timeout, and duplicate requests addressed?
4. Is webhook signature verification defined by the actual provider?
5. Is the final status mapping based on the API contract?
6. Is error handling consistent with stored state?
7. Are all sensitive values excluded from logs and examples?

## Layout and readability

Make diagrams detailed enough to be useful, but avoid compressing a long end-to-end system into a single unreadable image. Split into main request flow, callback processing, and recovery/reconciliation if needed. Keep the Mermaid source editable.

See `../examples/diagrams/` for reusable `.mmd` files.
