# Claude Code project guidance

Pick the skill matching the requested output language:

- `skills/system-analysis-en/SKILL.md` for English.
- `skills/system-analysis-id/SKILL.md` for natural Indonesian with unchanged English technical terms.

Project-specific source evidence determines facts, not generic examples. Maintain `Confirmed`, `Existing / Observed`, `Proposed` and `Need Confirmation` labels.

## Standard documentation delivery

When asked to design or document a new application, system or module, create **three core documents by default**: BRD (business/non-technical), PRD (product/features/user journeys), and FSD (functional implementation/validation/data/QA). Place stakeholder mapping and business workflow in BRD, user flows in PRD, and ERD, sequence diagrams, data dictionary, integration and test traceability in FSD as appropriate.

Follow `docs/document-suite.md`, `docs/brd-standard.md`, `docs/prd-standard.md` and `docs/fsd-standard.md`. Do not deliver 19 separate files unless the user asks for additional standalone artifacts. Small scoped requests remain small.

## ERD and style rules

ERD: no overlapping tables, labels or connectors. Don't compress. Group and separate PK, FK and attributes with visible horizontal rules. Render the diagram and embed it in the document.

Document appearance: Calibri, pure black #000000 text, white background, full black table borders without shading. **First-page order is unnumbered title → real two-column Item/Keterangan (ID) or Item/Description (EN) table → content.** Use known metadata or Need Confirmation, without extra decorative subtitle.

[Installation and CLI guide](docs/installation.md)

## First-page and documentation-completeness rules

For BRD/PRD/FSD, begin with a **plain unnumbered title**, then **the required editable `Item | Keterangan` / `Item | Description` table**, then substantive content. Do not add decorative subtitle or status banner outside the table.

**Use the opening two-column `Item | Keterangan` or `Item | Description` table by default.** Relevant rows include Module, Document Version, Date, Related Systems, Status. Unknown values are `Need Confirmation`. Keep white cells and black full borders, without invented values or duplicate decorative metadata.

**Brief user input is enough to prepare complete documents** for a new module/system. Draft full relevant content and rendered diagrams for BRD, PRD and FSD (or the one document requested), with concrete Proposed designs and clearly marked Need Confirmation decisions. Do not fabricate current-state facts, real architecture, integrations, owners, metrics or schedules.
