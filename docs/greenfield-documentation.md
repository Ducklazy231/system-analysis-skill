# Greenfield system documentation — complete delivery contract

This guide applies when a user asks for a **new application, project, or module from scratch**. Instead of stopping at a project overview or PRD, the AI agent should create an integrated BA/SA documentation package and the associated rendered diagrams automatically.

The requirement does **not** apply to small, scoped changes such as a Jira bug, one field, one workflow correction, or a short rewriting request.

## Rendered documentation workflow

The following example shows the **end-to-end documentation process with proposed stakeholder roles**, rather than a text-only checklist:

![Rendered greenfield documentation workflow](../examples/diagrams/greenfield-documentation-workflow.svg)

The illustration is not an assignment of actual people or approval authority.

## 1. Default deliverable package

| Deliverable | What must be addressed | Evidence / status |
|---|---|---|
| 01. Project Charter | Problem, objective, target users, constraints, outcome and key assumptions | Source evidence or Proposed |
| 02. Stakeholder Register + RACI | Stakeholder/role, responsibility, decision rights, consulted/informed roles, known PIC | Named owner if given, otherwise Need Confirmation |
| 03. Scope | Modules, release boundaries, in/out scope, dependencies and priorities | Confirmed or Proposed |
| 04. BRD | Business goals, actors, process needs, Business Requirements and Rules | Traceable to supplied context |
| 05. PRD | Product objectives, personas, use cases, features, user journeys, priority | Confirmed or Proposed |
| 06. FRD / SRS | Functional requirements, field specifications, validation, errors and acceptance | Testable, tracked with IDs |
| 07. As-Is / To-Be | Existing process if present, documented gaps, target process | Never invent an As-Is for a greenfield project |
| 08. Workflow + Swimlane | Business workflow and actor handoff, happy and exception paths | **Rendered diagram required** |
| 09. User Story / Use Case | Actor, trigger, preconditions, normal and alternate flows, outcomes | Each links back to features |
| 10. Sequence Diagrams | Calls, input/output, validation, state updates, asynchronous steps and failures | **Rendered diagram required** |
| 11. ERD + Data Dictionary | Entities, PK/FK, cardinality, key attributes, types, constraints | **Rendered ERD** and editable schema notes |
| 12. System Architecture | Modules, services, boundaries, dependencies, data stores, security assumptions | **Rendered architecture** if applicable |
| 13. API Specification | Source/target, trigger, auth, endpoints if verified, data mapping, callback/retry | Mark missing contracts Need Confirmation |
| 14. Role Permission | Actors, module access, actions, field-level visibility, authorization checks | Confirm owner and policy |
| 15. Business Rules / Status | Conditions, calculation, approval logic, exceptions and status transitions | No invented final decisions |
| 16. Screen Requirements | List/detail/create/edit views, fields, actions, empty/error states, navigation | UI/UX ready |
| 17. UAT | Test scenarios, data prerequisites, happy path, failure cases, expected result | Traceability to requirement IDs |
| 18. Risk & Delivery | Dependencies, non-functional needs, migration, release/UAT concerns, sign-off checklist | Assumptions clearly labeled |
| 19. Decision Log | Open questions, trade-offs, impact, approver, change log and decisions | Track Need Confirmation |

The agent must **cover each section**. `Not Applicable` is acceptable when there is a clear reason. `Need Confirmation` is required for missing decisions. Neither should be used to avoid feasible analysis.

## 2. Stakeholder mapping

Only call someone a confirmed stakeholder or assign them an actual approval responsibility when the user or supporting source identifies that fact.

If the user provides no stakeholder names, create a **proposed role-based map**, for example:

| Role | Example responsibilities | Mapping status |
|---|---|---|
| Business Owner | Business objective and policy decisions | Proposed, owner unknown |
| Product Owner | Backlog and product acceptance | Need Confirmation |
| Project Manager | Delivery dependencies and timeline | Need Confirmation |
| Business / System Analyst | Requirement, process and integration analysis | Proposed |
| UI/UX | Screen specification and prototype | Proposed |
| Frontend / Backend | UI, backend logic and service implementation | Proposed |
| Database / Data | Data model, storage, migration and quality | Proposed if needed |
| QA / UAT | Test scenario and validation | Proposed |
| Security / Infrastructure | Authorization, environments and operational readiness | Proposed if relevant |
| Operations / Support | Handover, SOP and support process | Proposed if relevant |

Do not silently mark each role as a real hire, assigned PIC or approver. Document RACI as `Proposed` until the owner validates it.

## 3. Work order

1. Extract factual inputs: project problem, business goals, users, existing processes, constraints, source data and open questions.
2. Identify stakeholder groups and decision boundaries.
3. Establish baseline modules and release scope.
4. Write BRD then PRD, retaining consistent terminology and requirement IDs.
5. Expand into FRD/SRS, fields, rules, validation, permissions and state transitions.
6. Derive the business workflow, actor swimlanes, sequences, entities and architecture.
7. **Render** the required diagrams and embed them in the documentation, rather than pasting only source markup.
8. Add integration contract gaps, NFR, error handling, test scenarios and UAT traceability.
9. Validate cross-document consistency and clearly separate Existing, Confirmed, Proposed, and Need Confirmation.
10. Deliver the full package without waiting for a second user prompt to request ERD, workflow, stakeholder matrix, PRD, or UAT.

If the work is too broad to substantiate every detail, keep complete coverage at an appropriate fidelity and explicitly identify remaining open decisions. Do not pretend unverified design is final.

## 4. Cross-document traceability

Assign each requirement a stable identifier and reuse it in diagrams, business rules and test scenarios.

| Requirement ID | PRD feature | FRD flow | Workflow | ERD entity | UAT ID | Decision status |
|---|---|---|---|---|---|---|
| REQ-001 (example) | Request submission | Submit & validation | WF-001 | Request | UAT-001 | Proposed |
| REQ-002 (example) | Approval review | Approval action | WF-002 | ApprovalHistory | UAT-002 | Proposed |

This is a hypothetical example, not a confirmed system design. Entity and module references can legitimately be `Not Applicable` if a requirement doesn't persist any data.

## 5. Required rendered diagram outputs

For a new system, at minimum create actual visible graphics for the **high-level workflow**, **swimlane**, **sequence diagram**, and **ERD** if the system has persisted relational data. Include **architecture/data flow** when multiple components or integrations are involved.

The diagram examples below are rendered SVG, not Mermaid text:

### Workflow example

![Rendered example workflow](../examples/diagrams/flowchart-submit-request.svg)

### Sequence diagram example

![Rendered example sequence diagram](../examples/diagrams/sequence-submit-request.svg)

### ERD example

![Rendered example ERD](../examples/diagrams/erd-request-management.svg)

[Editable ERD Mermaid source](../examples/diagrams/erd-request-management.mmd)

All three example diagrams describe **illustrative** processes and must be replaced with diagrams derived from the actual project's requirements.

## 6. DOCX/PDF deliverables

When the user asks for Word/PDF, create real files and embed the rendered diagrams as readable graphics. Default style: Calibri, **all text pure black #000000**, white pages, white table cells, and visible black borders across the full table grid. Do not use gray paragraph styles, blue hyperlinks, shaded table headers, tinted captions, or decorative backgrounds.

Provide source diagrams separately if requested. Technical source code alone is not a substitute for the rendered visuals.

If the user did not ask for a file type, provide Markdown documentation with the visual diagrams rendered where supported. Do not invent a preference for PDF over editable Word.

## 7. Completion checklist

- All relevant artifacts in the coverage matrix have substantive content, not empty headings.
- Stakeholders and approvers are supported by evidence or clearly marked Proposed / Need Confirmation.
- BRD, PRD, FRD and UAT refer to consistent requirement IDs.
- Workflow, sequence, ERD and architecture diagrams visually exist and match written rules.
- The ERD includes PK/FK and cardinality where relational data is involved.
- Every critical action defines triggers, permissions, validations, status changes and error handling.
- API endpoints, contracts, security claims and integration availability aren't invented.
- All text in Word/PDF is black and Calibri, with white, fully bordered tables.
- Open decisions and excluded scope are clear.
- The user does not need to make a second request to receive the core documentation package.
