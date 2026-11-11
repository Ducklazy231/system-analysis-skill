# Changelog

## 1.3.0 — 2026-11-11

- Enforced pure black text (#000000) in Word/PDF for every element, including body, headings, table content, captions and hyperlinks. Kept Calibri as the single default font.
- Removed gray body, blue hyperlink and auto-theme text-color defaults. Tables remain plain white with visible black full-grid borders and no colored/shaded headers or alternating rows.
- Added mandatory full greenfield documentation mode: new systems/projects/modules automatically receive comprehensive BA/SA coverage including stakeholders and RACI, Project Charter, BRD, PRD, FRD/SRS, workflows, swimlanes, sequence diagrams, ERD with data dictionary, architecture, permission, API mapping, UAT and decision log.
- Kept small tasks appropriately scoped. Unverified people, architecture and business decisions must stay Proposed or Need Confirmation.
- Added `docs/greenfield-documentation.md`, a rendered ERD example and its editable Mermaid source.
- Updated AGENTS.md, CLAUDE.md, English and Indonesian skills, README and DOCX/PDF guide to apply these rules.

## 1.2.1 — 2026-11-11

- Standardized **Calibri** as the default font for body text, headings, tables, and document captions.
- Required visible full table borders (black or dark gray), white backgrounds, and no table shading or color fills in Word/PDF.
- Required **rendered diagrams** as primary deliverables for flowcharts, workflows, swimlanes, and sequence diagrams rather than code-only or text-only outputs.
- Required embedded SVG/PNG/vector diagrams inside requested Word/PDF artifacts, with editable source as optional extra.
- Added example rendered SVG flowchart and sequence diagram, embedded visually in README and diagrams guide.
- Updated English, Indonesian, and bilingual master SKILL.md files to keep behavior consistent.

## 1.2.0 — 2026-11-10

- Made the repository documentation English-first.
- Added `skills/system-analysis-en/SKILL.md` as a standalone English BA/SA skill.
- Added `skills/system-analysis-id/SKILL.md` as a standalone Indonesian BA/SA skill with natural workplace wording.
- Preserved technical English terms in the Indonesian skill and examples.
- Updated root `SKILL.md` to a bilingual-aware English-first master.
- Added verified CLI command syntax for Claude Code, Codex CLI, Gemini CLI, Cursor, GitHub Copilot, and OpenCode.
- Updated installation guide, README, examples, Mermaid diagram guidance, and Word/PDF style documentation.

## 1.1.0 — 2026-11-10

- Added Indonesian Anti-AI Slop standards.
- Added sequence diagram patterns with normal and failure paths.
- Expanded natural DOCX/PDF formatting rules.

## 1.0.0 — Previous baseline

- Consolidated cross-project BA/SA analysis methods and deliverable quality standards.

The changelog describes instruction content revisions, not releases of a software product.
