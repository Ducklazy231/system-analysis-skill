# Business & System Analysis Skill

A reusable instruction set for AI-assisted Business Analysis (BA) and System Analysis (SA). This skill works across projects and covers business workflows, requirements, API integration, and practical technical documentation.

**Version:** 1.1.0  
**Canonical instructions:** [`SKILL.md`](SKILL.md)  
**Indonesian README:** [`README.md`](README.md)

## Coverage

| Area | Scope |
|---|---|
| Business analysis | Discovery, As-Is/To-Be, stakeholder needs, scope and business rules |
| Deliverables | BRD, PRD, FRD, SRS, MoM, Jira, SOP, UAT |
| Technical analysis | API integration, ERD, architecture, data flows, sequence diagrams |
| Quality control | Evidence, decision status, traceability, acceptance criteria |
| Writing | Anti-AI Slop guidance for Indonesian and clear English |
| Documents | Readable DOCX/PDF typography, margins, tables and diagrams |

This skill contains **no confirmed requirements for a particular project**. Obtain business rules, roles, API contracts, and system status from the active project's evidence.

## Getting started

1. Attach or load [`SKILL.md`](SKILL.md) as instructions for your AI tool.
2. Provide source documents, meeting notes, screenshots, and technical evidence.
3. Specify the deliverable, language, and file format.

Example prompt:

> Apply SKILL.md. Review the attached inventory requirements. Write an As-Is/To-Be analysis, business rules, field specifications, and testable acceptance criteria in clear English. Separate observed facts, confirmed decisions, proposals, and open questions.

A repository file is **not automatically loaded by every AI tool**. Use supported project instruction mechanisms or explicitly attach and reference it. `AGENTS.md` and `CLAUDE.md` are short pointers for environments that read those conventions.

## Principles

- **Evidence over assumptions.** Keep `Existing / Observed`, `Confirmed`, `Proposed`, and `Need Confirmation` separate.
- **Write for execution.** Requirements should describe actors, triggers, behavior, validation, and observable outcomes.
- **Remove filler.** Avoid generic consulting language, unsupported metrics, and ornamental introductions.
- **Keep technical flows accurate.** HTTP acknowledgment does not necessarily mean business completion. An async webhook is not the original request's HTTP response.
- **Use practical document formatting.** Word/PDF deliverables should look like internal working documents rather than presentation slides.

## Examples and guides

- [General usage guide](docs/usage-en.md)
- [Indonesian usage guide](docs/penggunaan-id.md)
- [Indonesian Anti-AI Slop standard](docs/anti-ai-slop-id.md)
- [Sequence diagram guide](docs/sequence-diagrams.md)
- [Word/PDF style guide](docs/word-pdf-style.md)
- [GitHub publishing steps](docs/github-publish.md)
- [Illustrative BRD](examples/brd-example.md)
- [Illustrative Jira ticket](examples/jira-example.md)
- [Submit form sequence](examples/diagrams/sequence-submit-form.mmd)
- [Approval sequence](examples/diagrams/sequence-approval.mmd)
- [External API/webhook sequence](examples/diagrams/sequence-external-webhook.mmd)

The source diagrams are editable Mermaid files. All example roles, paths, error codes, states, and data are illustrative rather than actual contracts.

See [change history](CHANGELOG.md) and [contribution guidance](CONTRIBUTING.md). No public redistribution license has been selected.