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

Document appearance: Calibri, black #000000 text throughout, white background, fully bordered black tables without shading. Use a **plain title with no invented subtitle** or author/status/version/release metadata. Add document information only when genuine values were provided or a supplied template requires them.

[Installation and CLI guide](docs/installation.md)

## First-page and documentation-completeness rules

For all BRD/PRD/FSD artifacts, the visible document title is **plain and unnumbered**. No `01.`, `Document 1`, number prefixed to the title, decorative subtitle or department/status/version banner. Default file names are `BRD`, `PRD` and `FSD` with the requested extension.

**Never use the opening generic `Item | Keterangan` or `Item | Description` metadata table**, even when some document metadata is known. Only an explicit user request or actual required corporate template can authorize a specific Document Control section. Place genuine facts under relevant substantive sections.

**Brief user input is enough to prepare complete documents** for a new module/system. Draft full relevant content and rendered diagrams for BRD, PRD and FSD (or the one document requested), with concrete Proposed designs and clearly marked Need Confirmation decisions. Do not fabricate current-state facts, real architecture, integrations, owners, metrics or schedules.
