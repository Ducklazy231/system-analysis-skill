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

Start with a **plain unnumbered PRD title**, e.g. `Accounting Module — Product Requirements Document (PRD)`. Do not prepend `01.`, department/status/version subtitles or an opening `Item | Keterangan` table, even if metadata is known. If ownership matters, put the known owner under the relevant stakeholder or product-responsibility section.

From a short new-product brief, still provide a **substantive PRD**: proposed feature/module breakdown, target users, user stories, main and alternate user flows, user-facing behavior, screen inventory, validation feedback, acceptance criteria and unresolved product decisions. Render user flows as visual diagrams. Use Proposed and Need Confirmation honestly rather than inventing approved features or release dates.
