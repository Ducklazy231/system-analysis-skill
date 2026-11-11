# BRD Standard — Business Requirements Document

**Audience:** Business Owner, management, Process Owner and non-technical stakeholders.

**Goal:** Establish the business need, business process change, outcomes and decision points. A business stakeholder should understand and validate the BRD without reading code, API contracts, or database schemas.

## Required sections

| Section | What to include |
|---|---|
| Business Background | Current business situation and reason for analysis |
| Problem Statement | Clearly observed problems, impacted roles and known impact |
| Business Objectives | Intended business outcomes, measured success only with supporting data |
| Stakeholder Register | Named stakeholders if given, otherwise clearly proposed role groups and decision owner gaps |
| Business Scope | In Scope, Out of Scope, assumptions and business constraints |
| As-Is Process | Current workflow only if an existing process is known |
| To-Be Process | **Rendered high-level workflow or swimlane** with business roles, decisions, hand-offs and exception path |
| Business Requirements | Stable IDs, actor, business need, rationale, expected outcome and decision status |
| Business Rules | Conditions/policies needed for the business process, confirmed vs proposed |
| Risks and Dependencies | Decisions, other departments and processes needed for adoption |
| Business Acceptance Criteria | How the business confirms the objective is met |
| Open Questions / Decisions | What is undecided, the impact and owner if known |

**Not a BRD default:** raw JSON, API endpoint, ERD, relational schema, deployment topology or SQL. Technical implementation belongs in FSD.

## Example requirement (hypothetical)

| ID | Business need | Expected result | Status |
|---|---|---|---|
| BR-001 | Staff need to check stock in the selected warehouse without opening every item | Stock can be reviewed by warehouse | Proposed |

The corresponding feature specification belongs in PRD and field validation / data mapping belongs in FSD.

## Business review checklist

- The problem is tangible, not generic "process optimization".
- Objectives describe the outcome rather than prescribing a specific technical solution.
- Actors and decision makers are confirmed or marked Need Confirmation.
- As-Is is not invented when the product is new.
- The diagram is an **embedded rendered graphic**, not a code block.
- All stated business rules and approval authority are supported or clearly proposed.
- No fabricated release date, version, owner, or decorative subtitle.

[Three-document standard](document-suite.md) · [Word/PDF layout](word-pdf-style.md)

## Document presentation and short-brief behavior

Start with a **plain unnumbered BRD title**, e.g. `Accounting Module — Business Requirements Document (BRD)`. No `01.` or `01_BRD` prefix, decorative subtitle, role/status/version line, or generic `Item | Keterangan` metadata table. Do not invent Project Owner, approval, Target Release or business metrics.

Even when the initial project brief is short, provide a **full BRD**: explain available business context, objectives, affected actors and stakeholder map (Proposed when unknown), scope, proposed business rules, a rendered To-Be process with alternative paths, and business acceptance. Use Need Confirmation for gaps, not entire blank sections. Never fabricate an As-Is process or measured financial impact.
