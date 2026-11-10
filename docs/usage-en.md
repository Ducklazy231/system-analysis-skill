# Usage guide

Treat `SKILL.md` as a cross-project working standard, not as a source of facts about the current system.

## AI tool setup

| Environment | Practical setup |
|---|---|
| ChatGPT | Attach `SKILL.md` or include it in relevant project instructions. Explicitly ask the model to follow it. |
| Claude | Include `SKILL.md` in project knowledge. `CLAUDE.md` can point to it in supported coding environments. |
| Coding agents | Put the files in the workspace. `AGENTS.md` gives compatible agents a short instruction pointer. |
| Other models | Attach the Markdown file or paste its instructions into supported project/system guidance. |

Not every platform automatically reads Markdown files stored in a repository. Confirm the instructions are in context when using a new tool.

## Recommended task inputs

Provide the deliverable type, process description, source evidence, confirmed business decisions, open questions, desired language, and output format. Set the level of detail based on the intended audience.

## Sample prompts

**Functional requirements**

> Apply SKILL.md. Create a functional specification for the attached inventory requirements. Include actors, preconditions, flows, field validations, error paths, and acceptance criteria. Separate verified requirements from proposals.

**API/sequence analysis**

> Apply SKILL.md. Document the integration between Order Service and an external provider using the supplied API contract. Add a Mermaid sequence diagram covering the initial request, acknowledgment, asynchronous callback, retry, and duplicate event handling. Do not invent endpoint contracts.

**DOCX**

> Create an editable Word document using the skill's clean internal-document formatting rules. No ornamental cover, decorative callouts, or repeated generic executive summary.

Review final outputs for evidence, traceability, technical consistency, and natural writing.
