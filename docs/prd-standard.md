# PRD Standard — Product Requirements Document

**Audience:** Product Owner, PM, UI/UX, BA/SA and product planning/engineering teams.

**Goal:** Translate approved or proposed business needs into product features, modules, user journeys, screens and testable product behavior. The PRD describes **what the user sees and does**, not how every database operation is implemented.

## Required sections

| Section | What to include |
|---|---|
| Product Overview | Product purpose linked to business objectives and BRD |
| User Problem and Needs | User segments, specific pain points and goals |
| Product Goals / Metrics | Intended product outcomes, measures only when supported |
| Users, Roles, Personas | Relevant user groups and capabilities |
| Scope and Prioritization | In/Out Scope, P0/P1/P2 or chosen priority method |
| Module / Feature Breakdown | Features grouped by module, purpose and user |
| User Stories / Use Cases | Actor, goal, precondition, main and alternate paths |
| User Journey and User Flow | **Rendered diagram** showing screen and action progression |
| Product Behavior | User-visible state, button/action, conditional visibility and feedback |
| UI/UX Screen Requirements | Screen inventory, inputs, actions, navigation and empty/error states |
| Feature Acceptance Criteria | Testable outcomes from the user's point of view |
| Dependencies and Constraints | Product dependencies and important restrictions |
| Open Product Questions | Pending UX/product decisions and impact |

The PRD can reference a wireframe or prototype only when it exists. Do not fabricate a Figma URL or claim a design was approved.

## Example feature (hypothetical)

| ID | BRD link | Feature | Product behavior | Status |
|---|---|---|---|---|
| PR-001 | BR-001 | Warehouse Stock Filter | Staff select a warehouse and the stock list refreshes to show matching items | Proposed |

FSD expands this into field specifications, role permission, validation, data sources and test cases.

## Product review checklist

- Every feature has a clear user value and links to a business requirement.
- Module scope and release priorities are clear.
- User journeys and **rendered user flows** match the written steps.
- Main, empty, error and permission-related UI states are covered.
- Product design decisions are not confused with unconfirmed implementation architecture.
- No invented stakeholder metadata or colored subtitle below the title.

[Three-document standard](document-suite.md) · [BRD standard](brd-standard.md) · [FSD standard](fsd-standard.md)

## Document presentation and short-brief behavior

Begin with a **plain unnumbered PRD title** and a real two-column information table: `Item | Keterangan` for Indonesian or `Item | Description` for English. The table can include Module, Document Version, Date, Related Systems, Status and other relevant known context. For unknown values use `Need Confirmation`, never fabricated metadata. Plain white cells, black full grid, Calibri black text. No extra colored subtitle.

From a short project brief, deliver a **substantive PRD**: feature/module inventory, target users, user stories, main and alternate user flows, screen inventory, user-visible behavior, error states, acceptance criteria and open product decisions. Render user flows as visual diagrams and label design recommendations `Proposed`.
