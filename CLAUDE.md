# Claude Code project guidance

For BA/SA work, select one skill edition:

- `skills/system-analysis-en/SKILL.md` for English deliverables.
- `skills/system-analysis-id/SKILL.md` for natural Indonesian deliverables with unchanged technical terminology.

Apply the user's current project evidence and decisions. Do not invent roles, APIs, states, approvals, metrics, or sign-off. Use practical, testable requirements and detailed but readable sequence diagrams.

For global installation via Claude Code, see `docs/installation.md`. For an agent that automatically detects project skills, the language-specific skill folder is the preferred reference.

## Greenfield and document defaults

For requests to document a new application, project, or module from scratch, create the **full BA/SA package by default**. This includes stakeholder register/RACI, scope, BRD, PRD, FRD/SRS, workflows and swimlanes, rendered ERD and sequence diagrams, architecture as relevant, validation and permissions, UI/UX requirements, UAT and open decisions. The user does not need to ask for each artifact. See [greenfield guide](docs/greenfield-documentation.md). Use Proposed and Need Confirmation to avoid inventing business decisions.

For Word/PDF always use Calibri with **solid black #000000 text on every element**. Keep tables white with full visible black grid lines and no shading. Include requested diagrams as rendered images/vector shapes, never just Mermaid code.
