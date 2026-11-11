# Usage guide

The repository supplies an English skill and a natural Indonesian skill. Both work across projects, but they are **instructions**, not sources of project facts.

## Automatic BRD, PRD and FSD for new systems

For a from-scratch application, project or module, the skill creates **three separate primary documents** by default:

- **BRD** for Business Owners and non-technical stakeholders. Focus on business problems, objectives, stakeholder responsibilities, scope, Business Rules, and rendered business workflows.
- **PRD** for Product/PM/UI/UX. Define target users, modules, features, user stories, screen behavior, and rendered user journey/user flow.
- **FSD** for Developers, System Analysts and QA. Define detailed functionality, validation, permissions, status transitions, rendered sequence diagrams, rendered ERD with PK/FK separators where relevant, integrations, and test mapping.

The supporting analysis is included inside the appropriate document. The user does not need to request the stakeholder table, ERD or sequence diagram separately.

**The ERD must be readable with no overlapping tables, text or connectors.** Use a larger canvas, not image compression. Show Primary Key, Foreign Key and regular fields as separate groups with horizontal divider lines.

Use a **plain title only**. Do not add invented subtitle banners, project Status/Version, Product Owner, Target Release, or a placeholder Document Information table. All text Calibri black `#000000`, white table cells and visible black full-grid borders.

See [the three-document standard](document-suite.md), [BRD](brd-standard.md), [PRD](prd-standard.md), [FSD](fsd-standard.md) and [greenfield workflow](greenfield-documentation.md).

For a narrow Jira issue or a field change, deliver only the requested task.

## Choose a language

- [system-analysis-en](../skills/system-analysis-en/SKILL.md): English documentation.
- [system-analysis-id](../skills/system-analysis-id/SKILL.md): Bahasa Indonesia that sounds like real BA/SA work. Technical terms and actual UI field names stay in English.

Install the version you want using [copy-paste CLI instructions](installation.md).

## Use in supported coding agents

After installation, ask for the skill by name or provide a task that matches its description. You can explicitly instruct the agent to apply it.

English prompt:

> Apply system-analysis-en. Create an FSD based on the provided MoM. Include functional requirements, field validations, role permissions, state transitions, sequence diagrams, and open questions. Do not treat proposals as confirmed requirements.

Indonesian prompt:

> Pakai system-analysis-id. Buat Jira bug dari case ini dengan As-Is, To-Be, Acceptance Criteria, dan error handling. Technical terms tetap English. Enggak perlu intro panjang.

## Context that helps

When available, supply the objective, actor and role, screenshots, current workflow, expected behavior, related system or API contract, meeting decisions, unresolved decisions, and requested output format.

A working skill should not invent a role, status, API endpoint, or permission to fill in gaps. It can document a proposal if clearly labeled.

## Task examples

**Business process review**

> Compare the As-Is and To-Be process. Identify gaps, dependency risks, and testable Business Rules.

**API analysis**

> Document the trigger, request/response mapping, status rules, webhook, retry, failure behavior, and reconciliation. Create a Mermaid sequence diagram with distinct happy and error paths.

**Jira**

> Write a concise bug ticket including actual vs expected behavior, reproduction steps if evidenced, and acceptance criteria.

**DOCX**

> Create a clean editable Word document using the skill's A4 layout with plain headings, readable tables, and no decorative cover.

**PDF**

> Export a print-ready PDF and check for broken page breaks, clipped tables, unreadable diagrams, and missing fonts.

## Validation

Check that documented claims are supported by the supplied sources, decisions are labeled correctly, diagrams match written requirements, and the final wording sounds natural for the intended audience.

Not all chat clients automatically read files from a linked GitHub repository. If the platform does not support skill auto-discovery, attach the file or include it in the project context.
