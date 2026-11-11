# Greenfield documentation workflow — BRD, PRD, FSD

**Default for a project, system, application, or module from scratch:** generate **three complete primary documents**, not 19 separate files.

1. `BRD` — Business Requirements Document for non-technical business readers.
2. `PRD` — Product Requirements Document for Product/PM/UI/UX and feature decisions.
3. `FSD` — Functional Specification Document for Engineering, System Analysts and QA.

Supporting analysis remains required, but it is organized **inside the appropriate document**.

[Complete three-document standard](document-suite.md) · [BRD must-have](brd-standard.md) · [PRD must-have](prd-standard.md) · [FSD must-have](fsd-standard.md)

## Workflow for the documentation package

![Rendered greenfield documentation workflow](../examples/diagrams/greenfield-documentation-workflow.svg)

The flow describes a hypothetical collaboration pattern, not actual named stakeholders or approvals.

1. Gather business context, source decisions, stakeholder roles and open questions.
2. Draft BRD with the business problem, outcomes, stakeholders, rules and rendered To-Be business workflow.
3. Derive PRD from the BRD. Define modules, feature inventory, user journeys, user-facing behavior and rendered User Flow.
4. Derive FSD from BRD/PRD. Specify functional logic, field validation, roles, state transitions, rendered sequence diagrams, relational ERD when applicable, integration, and test mapping.
5. Review consistency and source evidence. Label anything not yet agreed as `Proposed` or `Need Confirmation`.
6. Deliver three separately identifiable files/documents in the requested format. Do not generate unrelated cover pages or 19 individual files.

## Where the content belongs

| Supporting content | Primary location |
|---|---|
| Business Owner, Process Owner, stakeholder mapping, RACI | BRD |
| Business goals, problem, scope, business approval and high-level workflow | BRD |
| Target users, features, personas, user journey, UI and release priorities | PRD |
| Product acceptance and screen-level interaction states | PRD |
| Field specification, validation, error handling, role permissions, calculations | FSD |
| ERD, Data Dictionary, sequence diagrams and technical integration | FSD |
| Test cases and traceability from BRD/PRD to functional requirements | FSD |
| Open decisions | Within the relevant document, with one consistent decision ID if tracked across all three |

## Example traceability

| Business | Product | Functional | Test |
|---|---|---|---|
| BR-001 | PR-001 | FS-001 | TC-001 |
| BR-002 | PR-002 | FS-002 and FS-003 | TC-002 and TC-003 |

The mapping is illustrative. One business requirement can drive multiple product features and functional specifications.

## Required visual outputs

Diagrams must be **actually rendered**, not merely Mermaid syntax.

### Business workflow example (BRD)

![Rendered business workflow](../examples/diagrams/flowchart-submit-request.svg)

### Sequence example (FSD)

![Rendered sequence](../examples/diagrams/sequence-submit-request.svg)

### ERD example (FSD)

![Rendered ERD with PK/FK dividers](../examples/diagrams/erd-request-management.svg)

[Editable ERD source](../examples/diagrams/erd-request-management.mmd)

**ERD layout gate:** No overlapping entities, text or connectors. Visible horizontal separators between PK, FK and attributes. Expand canvas or split diagrams instead of compressing an unreadable model.

## Document formatting and first-page information table

All three documents use Calibri, pure black text throughout, white backgrounds, and visible black full-grid table borders without shading.

First-page order: **plain unnumbered document title → real information table → actual first section**. Use `Item | Keterangan` for Indonesian and `Item | Description` for English. Choose context-appropriate rows such as Module, Document Version, Date, Related Systems and Status. Known facts are used as provided, and unknown ones are marked `Need Confirmation` or `Not specified`. Do not invent release dates or version numbers. No extra decorative subtitle or metadata banner.

## Final delivery check

- Exactly **three primary documents** for a new-system package, unless the user specifies otherwise.
- BRD is understandable to business stakeholders without implementation detail.
- PRD covers product scope, feature behavior, roles, journeys and screens.
- FSD is testable, detailed and contains relevant rendered technical diagrams.
- No imaginary existing process, owners, API contracts, data schemas or approved business rules.
- Diagrams actually exist as legible graphics, with source files as an optional extra.
- ERD has readable table sections for PK, FK and attributes and no overlap.
- No decorative subtitle/metadata under document title.
- Cross-document IDs and decisions stay consistent.

## Rule for short inputs and first-page layout

A one-paragraph new-system brief still requires substantial **BRD, PRD, and FSD** analysis, relevant rendered diagrams, and traceability. Use `Proposed` for candidate designs and `Need Confirmation` for missing decisions rather than making up facts.

Start each document with an **unnumbered title**, then the required **Item/Keterangan or Item/Description table**, then substantial content. Default filenames are `BRD`, `PRD` and `FSD` with the requested extension. Do not add ornamental subtitles or duplicate information outside the table.
