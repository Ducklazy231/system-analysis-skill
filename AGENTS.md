# Instructions for AI coding agents

This repository contains reusable Business Analyst and System Analyst instructions, not project-specific requirements.

## Which skill to use

- English: `skills/system-analysis-en/SKILL.md`
- Natural Indonesian: `skills/system-analysis-id/SKILL.md`
- Root working reference: `SKILL.md`

Use the edition that matches the user's requested output language. If writing in Indonesian, keep technical terms in English: API, endpoint, payload, workflow, validation, approval, role, permission, webhook, retry, sequence diagram, and actual UI field names.

Always separate `Existing / Observed`, `Confirmed`, `Proposed`, and `Need Confirmation`.

Use the supplied project's evidence for actual business decisions, API contracts, roles, status names, and requirements. Do not invent those details.

For diagrams see `docs/sequence-diagrams.md`. For Word/PDF layout see `docs/word-pdf-style.md`. For installation see `docs/installation.md`.

Do not pad a small task with a generic introduction, excessive tables, or an unnecessary conclusion.

## Mandatory greenfield documentation behavior

When asked to create or analyze a **new project, system, application, or module from scratch**, automatically produce the complete documentation package. Include stakeholder register/RACI, scope, BRD, PRD, FRD/SRS, business workflow and swimlane, rendered sequence diagrams, rendered ERD with data dictionary, architecture/data flow if relevant, role permissions, status transitions, API specs when applicable, UI/UX screen requirements, UAT, risk and decision log.

The user **does not need to request each artifact separately**. Use [the greenfield blueprint](docs/greenfield-documentation.md). Do not invent real stakeholders, roles, business rules, data schemas, or technical integration details: label proposed design and Need Confirmation. Don't apply this full-package mode to narrow Jira tickets or one-paragraph edits.

## Mandatory document rendering style

Any generated Word/PDF must use Calibri and **pure black #000000 for all text**, including titles, headings, captions, table content and hyperlinks. No blue links, gray captions, dark-charcoal body, or alternating text colors. Tables have white cells and visible full black borders, without shading. Render every required diagram into an actual visual and embed it in the document instead of merely supplying Mermaid code.
