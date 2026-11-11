# Three-document BA/SA standard: BRD, PRD, and FSD

**Default for a substantial new system, application, or module:** create exactly **three primary documentation deliverables**, not 19 separate files:

1. **BRD — Business Requirements Document** for business stakeholders and decision makers.
2. **PRD — Product Requirements Document** for Product, PM, UI/UX, BA/SA, and engineering planning.
3. **FSD — Functional Specification Document** for System Analysts, Developers, QA, Database and integration teams.

The prior 19-area coverage matrix remains a **completeness checklist**, not 19 independent file outputs. Stakeholders and high-level workflows belong in BRD. Personas, features, product behavior and journeys belong in PRD. Detailed validation, field specifications, API mapping, ERD, rendered sequences and test traceability belong in FSD. Supporting material is included in the most relevant document or as a referenced appendix, not duplicated throughout all three.

## Triggers and scope

This default applies to requests to **design or document a new project/system/module from scratch**, or to produce a complete requirements package. It does not override explicit user requests for only one document, a Jira ticket, a bug analysis, a small change, or a short edit.

When a user explicitly asks for files and editable business documents, create three separate files using the available artifact tools. Prefer names `01_BRD`, `02_PRD`, and `03_FSD` with the requested extension. When no format is specified, provide three clearly separated Markdown deliverables or files rather than presuming the user requires DOCX or PDF. A Markdown outline alone is not a finished document.

Do not ask separately whether the user also wants stakeholders, workflow, ERD, sequence diagrams or test scenarios. Those are part of the relevant document's standard when applicable.

## 1. BRD — business decision document

**Primary readers:** Business Owner, Department Head, Management, Process Owner, and non-technical stakeholders.

**Question answered:** Why does the business need the change, what business outcome is expected, which people and processes are affected, and what should be agreed?

**Writing level:** Plain business-oriented language. Explain activities and decisions, not internal implementation. Avoid technical details such as schema, endpoint method, JSON payload, SQL, ORM, or deployment design.

### BRD must-have sections

| Section | Minimum useful contents |
|---|---|
| Business Context and Background | Current business situation and reason for change |
| Problem Statement / Opportunity | Specific pain points, affected process and demonstrated impact |
| Business Objectives and Success Criteria | Target business outcomes, evidence-based KPIs where data is available |
| Stakeholders and Responsibilities | Business Owner, Process Owner, decision maker, impacted actors, known PIC, proposed RACI as needed |
| Business Scope | In scope, out of scope, business boundaries, exclusions |
| As-Is Process | Existing process and known pain points, only when an actual existing process exists |
| To-Be Business Workflow | **Rendered** high-level business process or swimlane with actors, handoffs, decisions and relevant exceptions |
| Business Requirements | ID, actor, need, rationale, expected outcome, decision status |
| Business Rules and Policies | Relevant approvals, restrictions and conditions as business decisions |
| Assumptions, Dependencies and Risks | Dependencies that affect business adoption or policy |
| Business Acceptance / Sign-off Criteria | How the business judges the change successful |
| Decisions and Open Questions | Confirmed, Proposed, Need Confirmation and decision owner |

**Must not default to:** table schemas, field-by-field API payloads, ERD, SQL, endpoint code, technical deployment.

## 2. PRD — product definition document

**Primary readers:** Product Owner, Product Manager, UI/UX, BA/SA, Tech Lead, and cross-functional product teams.

**Question answered:** What product should be built, for whom, with which modules and features, and how should users experience it?

**Writing level:** Product-level behavior and interaction, more detailed than BRD but not a line-by-line backend specification.

### PRD must-have sections

| Section | Minimum useful contents |
|---|---|
| Product Overview and Purpose | Description and link to business objective / BRD |
| User Problem and Needs | Pain points by user segment or role |
| Product Goals and Success Metrics | Product outcomes and measurable indicators when supported |
| Target Users / Roles / Personas | Who uses the product and their needs |
| Product Scope and Release Priority | In/out scope, P0/P1/P2 or chosen prioritization scheme |
| Module and Feature Breakdown | Feature inventory, descriptions and grouping |
| User Stories and Use Cases | Actor, goal, preconditions, main/alternate flows |
| User Journey and **Rendered User Flow** | Navigation between relevant screens, happy and exception paths |
| Product Behavior Requirements | What each feature does from the user's perspective, conditional visibility and product states |
| UI/UX Requirements | Screen inventory, interactions, empty/error states, references to wireframes/prototypes when given |
| Feature Acceptance Criteria | Testable product and user-facing acceptance conditions |
| Product Dependencies and Constraints | Business/technical dependencies and relevant NFRs, without inventing implementation |
| Release Considerations and Open Questions | Delivery boundaries, deferred features and unresolved product decisions |

**Must not default to:** unverified DB column types, SQL, raw endpoint contracts, infrastructure implementation, duplicated business justification paragraphs.

## 3. FSD — functional specification document

**Primary readers:** System Analyst, Frontend, Backend, QA, Database Engineer, Tech Lead, and relevant integration teams.

**Question answered:** Exactly how must each system function behave, what information is read or saved, which validations and permissions apply, and what happens on error?

**Writing level:** Specific, implementation-ready, testable and traceable to BRD and PRD, while marking unknown implementation decisions clearly.

### FSD must-have sections

| Section | Minimum useful contents |
|---|---|
| System Boundary and Module Overview | Systems/modules, dependencies, links to related PRD/BRD IDs |
| Functional Requirement Matrix | FSD requirement ID, linked PRD/BRD IDs, actor, trigger, expected behavior and status |
| Actor / Role Definition | Roles and scopes relevant to functionality |
| Detailed Functional Workflow | Step-by-step main flow, alternate flow, exception and state changes |
| **Rendered Sequence Diagrams** | Frontend/backend/database/external calls, request/response, sync vs async, validation and failure |
| Screen and Field Specification | Field name, type, required, default, visibility, editable, source, validation |
| Validation and Error Handling | Business/field validation, duplicate, unauthorized, timeout, failure and user-visible message |
| Business Logic / Calculation | Conditions, formulas, derived fields, processing and rounding when relevant |
| State Transition Matrix | Current status, action, actor, condition, next status, exception |
| Role Permission Matrix | View, Create, Edit, Submit, Approve, Reject, Cancel, Delete, Send, field-level restrictions as applicable |
| **Rendered ERD and Data Dictionary** | For relational storage: entities, fields, PK/FK, cardinality, constraints, source of truth and relationships |
| API / Integration Specification | If applicable: verified endpoints and methods, auth, payload mapping, responses, webhook, retry and idempotency |
| Non-Functional Requirements | Security, performance, audit, availability, compliance when relevant and testable |
| Technical Dependencies and Interfaces | External systems, services, config, environment assumptions and dependencies |
| Functional Acceptance and Test Traceability | Acceptance Criteria, UAT/Test Case mapping, normal/boundary/negative scenarios |
| Open Technical Questions | Unresolved schemas, role decisions, contracts and rules with impact |

When a subsystem does not have relational persistence, mark ERD `Not Applicable` with a reason. Do not manufacture entities only to fill a document. When no external integration exists, API section can be `Not Applicable`. **Do not represent unconfirmed proposed data structures or API URLs as approved facts.**

## 4. Cross-document traceability

Use stable IDs that link each artifact without copying full descriptions into every document.

| BRD | PRD | FSD | Test case |
|---|---|---|---|
| BR-001 | PR-001 | FS-001 | TC-001 |
| BR-002 | PR-002 | FS-002, FS-003 | TC-002, TC-003 |

This is an illustrative mapping, not a rigid one-to-one rule. One business requirement may map to many product requirements, and one feature may have multiple functional specifications. Include source/evidence and decision status where practical.

## 5. Mandatory ERD layout quality

The ERD is a **rendered visual** inside the FSD, with editable source available as an additional deliverable when useful.

1. **Zero overlap.** Tables/entities never overlap other tables, field labels, cardinality markers, connectors or relationship descriptions. Text never crosses a border or another label.
2. **Do not compress.** Increase canvas dimensions, export at larger resolution, use landscape pages, or split by bounded context/module with a cross-module overview. Never shrink a complex schema into tiny unreadable boxes to fit one portrait page.
3. **Visible key separation.** Within each table, group Primary Keys, Foreign Keys and ordinary attributes in separate clearly labeled sections. Use **solid horizontal divider lines** between the groups. Show explicit `PK` or `FK` markers on the respective fields, not color alone.
4. **Composite/reused key.** If a column is both PK and FK, mark `PK, FK` on one field entry instead of duplicating it. Show composite keys clearly if applicable.
5. **Consistent sizing.** Make table width fit the longest field/type label and height fit all fields. Use consistent padding and legible Calibri black text on white background.
6. **Connector routing.** Route relationship lines through whitespace or dedicated connection ports. Avoid crossing table interiors, text and other lines. Add routing space as necessary. Show correct 1:1, 1:N, N:M cardinality and the actual FK relationship.
7. **Data dictionary consistency.** Names, types and relationships must agree with the field matrix and functional flows.
8. **Review actual render.** Check visually for overlap, clipped text, line collisions and illegible scaling. Correct and rerender before delivery. Do not claim to have checked if no preview/inspection was possible.

[Rendered example ERD with PK/FK dividers](../examples/diagrams/erd-request-management.svg) · [Editable example source](../examples/diagrams/erd-request-management.mmd)

## 6. Required Word and PDF presentation

- Calibri for all text. **Every text element uses pure black `#000000`**, including title, headings, paragraphs, table text, captions, and hyperlinks.
- Page and all table cells white. Full visible black grid on all table cells. No shading, colored backgrounds, decorative header fills or alternating row bands.
- **Start with the document title only.** Default heading examples: `Accounting Module — Business Requirements Document (BRD)`, `Accounting Module — Product Requirements Document (PRD)`, and `Accounting Module — Functional Specification Document (FSD)`.
- Do not automatically add a subtitle such as `Product Management & System Analysis | Status: Proposed | Version: 1.0.0`, department labels, ornamental rule lines, boxes, revision banners, or colored title decoration.
- **No fabricated document metadata.** Do not invent Version, Status, Target Release, Sprint, Product Owner, Lead System Analyst, PIC, approver, date or document author. Include document information only when provided or required by an approved company template. If none is available, **omit the metadata table entirely** and begin with actual content.
- Do not repeat the same status/owner/version under the heading and in a metadata table.
- Any required diagrams must be **visibly rendered and embedded**, not Mermaid code blocks disguised as graphics.
- Do not create decorative covers, header/footer, random icons, tinted summaries or other AI-template styling unless the user requests them.
- If a corporate template conflicts, follow explicit user instructions and report any necessary deviation.

## 7. Default delivery behavior

When generating a complete new-system package:
1. Extract source facts, confirmed decisions and missing information.
2. Prepare BRD first as the business baseline.
3. Derive PRD features and user journeys from BRD.
4. Expand FSD with precise functional behaviors, data model, diagrams, permission, errors and test traceability.
5. Render and embed business workflow in BRD, user flow in PRD, and sequence diagrams / ERD in FSD as applicable.
6. Cross-check that all three documents use the same actors, terms, business decisions and requirement IDs.
7. Deliver **three** substantive documents. Do not invent 19 other file artifacts.

For a narrow user request, keep the requested smaller scope. For a larger unknown project, draft evidence-backed sections now and mark `Proposed` or `Need Confirmation` honestly. Do not pretend placeholder content is final.
