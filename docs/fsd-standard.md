# FSD Standard — Functional Specification Document

**Audience:** System Analyst, Frontend/Backend Developers, QA, Database Engineer, Tech Lead and integration owners.

**Goal:** Describe exactly how the system must behave, what is validated/read/written, which role can perform each action, how the state changes and how QA can test it. It should be specific enough for implementation without claiming unknown designs are confirmed.

## Required sections

| Section | What to include |
|---|---|
| System Boundary / Module | Components, entry points, related BRD/PRD IDs |
| Functional Requirement Matrix | FS IDs, trigger, actor, precondition, condition, behavior, output and decision status |
| Actors and Roles | Role definitions, permission boundaries and data access |
| Detailed Functional Workflow | Main path, alternate paths, failure path and state changes |
| Sequence Diagrams | **Rendered diagrams** with lifelines, calls, responses, validation and async callbacks when relevant |
| Screen and Field Specification | Name, data type, required, default, editable/visible, source, validation and error message |
| Business Logic | Formula, conditions, rounding, duplicate handling, calculation source |
| Validation / Error Handling | Invalid input, unauthorized, missing record, timeout, duplicate, storage failure |
| Status Transition Matrix | Current status, action, role, condition, next status and exception |
| Role Permission Matrix | View, Create, Edit, Submit, Approve, Reject, Cancel, Delete, Send when applicable |
| ERD + Data Dictionary | **Rendered ERD** with PK/FK sections, cardinality, constraints and consistent fields if relational storage exists |
| API / Integration | Only if used: verified contract, method, auth, request/response, mapping, retry, webhook, reconciliation |
| NFR / Dependencies | Audit, security, performance, operational and deployment constraints when applicable |
| Acceptance Criteria and Test Mapping | Link each FS requirement to happy, boundary, validation, security and failure test cases |
| Open Technical Questions | Unconfirmed data schema, behavior or API decisions |

## Mandatory ERD quality

**Entity boxes may not overlap.** Never allow connector lines to cross field content, cardinality labels to obscure a table, or a field to be clipped. Use a larger canvas or separate diagrams by bounded context, with a cross-module overview as needed. Never force a large ERD into a single tiny portrait image.

Within each entity/table, divide:
1. **PRIMARY KEY (PK)**
2. **FOREIGN KEY (FK)**
3. **ATTRIBUTES**

Use solid **horizontal separator lines** and explicit key markers. Show `PK, FK` together where a field has both roles. FK mapping, cardinality and entity field names must agree with Data Dictionary and functional behavior.

[Rendered sample ERD](../examples/diagrams/erd-request-management.svg) · [Editable Mermaid example](../examples/diagrams/erd-request-management.mmd)

## Illustrative requirement

| ID | PRD link | Action | Validation | Expected result | Status |
|---|---|---|---|---|---|
| FS-001 | PR-001 | Select warehouse on Stock List | Check role and allowed warehouse list | Backend returns stock records limited to selected warehouse | Proposed |

This example does not establish an actual backend service or endpoint.

## FSD review checklist

- All requirements are traceable to PRD/BRD or have a documented rationale.
- Actors, triggers, preconditions, validations, outputs and errors are testable.
- Status, Role Permission and UI conditional states match each other.
- Rendered workflow, sequence diagram and ERD match the written behavior.
- All database entities include clearly marked PK/FK, relationships and cardinality.
- No overlapped ERD table, connector, label or field.
- Diagram source does not substitute for rendered diagram in Word/PDF.
- API contracts and real customer data are not invented.
- All text black #000000, Calibri, white fully bordered tables, no decorative metadata under title.

[Three-document standard](document-suite.md) · [BRD standard](brd-standard.md) · [PRD standard](prd-standard.md)
