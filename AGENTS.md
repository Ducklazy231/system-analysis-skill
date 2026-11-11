# Instructions for AI coding agents

Use the appropriate language-specific BA/SA skill:

- English: `skills/system-analysis-en/SKILL.md`
- Natural Indonesian with English technical terms: `skills/system-analysis-id/SKILL.md`
- English-first bilingual master: `SKILL.md`

Apply the user's project evidence. Separate `Existing / Observed`, `Confirmed`, `Proposed` and `Need Confirmation`. Do not invent stakeholder names, approval rules, fields, schemas, endpoints, metrics, or sign-off.

## Default for a new system or module

Automatically create **three complete primary documents**: **BRD, PRD and FSD**, not 19 independent artifacts.

1. BRD is for non-technical business stakeholders. Include problems, objectives, scope, stakeholder mapping and rendered business workflow.
2. PRD is for Product/PM/UI/UX and feature decisions. Include target users, module/feature inventory, product behavior, user stories and rendered user flow.
3. FSD is for System Analyst, Developers and QA. Include technical functional behavior, fields, validation, permissions, state transitions, errors, UAT/test mapping, rendered sequence diagrams and rendered ERD where relational data is used.

Each document has mandatory sections and traceability rules in `docs/document-suite.md`. Do not ask whether to also produce ERD, workflow, stakeholder mapping or test cases. They belong inside the three primary documents.

**For a narrow Jira bug, one field, or short edit, perform only the requested task.**

## ERD quality gate

- Never overlap entities, fields, connectors, relationship text or cardinality.
- Never compress large ERDs into illegible images. Use a larger canvas or split by domain with a relationship overview.
- Draw visible horizontal separator lines inside each table between **Primary Key (PK)**, **Foreign Key (FK)** and **Attributes**. Label key fields explicitly and show `PK, FK` if both apply.
- Route connectors around table contents and inspect the rendered output. Include editable source only as supplementary material.

## Document appearance

- **Calibri** for all text, **solid black #000000** for every title, paragraph, table cell, heading, caption and hyperlink.
- White page, white cells, clearly visible black table borders. No colored/shaded headers or zebra stripes.
- **Plain unnumbered title**, then a **required two-column Item/Keterangan table (ID) or Item/Description table (EN)** with black visible full borders. Include relevant Module, Document Version, Date, Related Systems, Status with genuine or `Need Confirmation` values. No extra decorative subtitle.
- Include the **document information table by default** for BRD/PRD/FSD and substantial standalone documents. Never invent its values or duplicate them as a decorative banner.
- Render diagrams as actual visual graphics in the requested document, not raw Mermaid code alone.

Other guides: `docs/word-pdf-style.md`, `docs/sequence-diagrams.md`, `docs/brd-standard.md`, `docs/prd-standard.md`, `docs/fsd-standard.md`.

## Strict first-page and short-brief quality gate

- Never prefix a visible document title with `01.`, `1.`, `01_BRD`, a numbered list marker, or any file-order index. Default file names: `BRD`, `PRD`, `FSD` (extension determined by request), without numeric prefixes.
- The first page must contain a plain unnumbered title, **immediately followed by the real information table**, then substantive content. No status/version ribbon or decorative subtitle.
- **Do create the opening `Item | Keterangan` / `Item | Description` table** by default. Use verified details and `Need Confirmation` for missing values, black full borders and white cells. Do not manufacture version or ownership information.
- A one-paragraph new-system brief still triggers **substantive complete BRD/PRD/FSD**. Never stop with generic intros, shallow outlines or empty sections. Use specific `Proposed` designs, record `Need Confirmation` issues, and render diagrams. Never claim missing data or chosen architecture was confirmed.
- Inspect the first page of generated Word/PDF in white print preview where possible, checking unnumbered title, a visible Item/Keterangan (or Item/Description) table, black Calibri text, unshaded fully bordered cells, and rendered diagrams.
