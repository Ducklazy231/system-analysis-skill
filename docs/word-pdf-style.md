# Word and PDF formatting standard

Produce documents that resemble normal internal BA/SA work, not a decorative AI-generated brochure. Use an organization's own template if provided.

## Default page style

| Element | Default |
|---|---|
| Page size | A4 portrait |
| Margins | 2.2 cm top/bottom, approximately 2.3–2.5 cm left/right |
| Font | **Calibri** for body, headings, and tables |
| Body | 10.5–11 pt, **solid black #000000 only** |
| Line spacing | 1.1–1.15 |
| Paragraph gap | 4–6 pt after |
| Document title | 15–16 pt, left-aligned, **black #000000** |
| Section heading | 12–13 pt, bold when needed, **black #000000** |
| Table | Calibri 9–10 pt **black #000000 text**, full visible grid (0.5–0.75 pt solid black border on every cell), **white background**, no shading or color fill |
| Header and footer | Do not add unless requested |

## Non-negotiable solid-black text rules

All document text must be **pure black #000000 (RGB 0/0/0)**. This applies to body paragraphs, every heading level, document title, table headers and cells, captions, footnotes, figure labels, bullet/numbered lists, hyperlinks, and metadata.

- Do not use dark charcoal, gray subtitles, blue hyperlinks, automatic theme accents, faded caption text, conditional text colors or colored heading styles.
- In DOCX, override the font color in **Normal, Title, Heading 1/2/3, Caption, List, Hyperlink, table styles and text runs**. Do not rely on theme defaults. Hyperlinks can remain underlined but must be black.
- In PDF, verify rendered output is black and white for all text. White page, white table cells and solid black borders.
- The default font remains **Calibri** for everything.
- Text in all embedded flowcharts, sequence diagrams and ERD should also be black. The diagram's shapes may be colored only when required to convey meaning or explicitly requested. Never use faint gray labels.
- Inspect actual generated file previews to catch unexpected text-color changes before delivery.

## Non-negotiable font, table, and rendered-diagram rules

- **Font: Calibri only by default**, including title, headings, paragraphs, captions, and tables. Never silently substitute Aptos or Arial. If Calibri is unavailable, report the fallback, or honor the user's specified corporate template.
- **Tables: visible full borders on every cell** with solid black lines (about 0.5–0.75 pt). Keep every cell white with **no background color, gray header fill, alternating row shading, colored banding, or gradient**. Use black Calibri bold for column headings. Grid lines must remain visible when printed or exported.
- **Flowcharts, workflows, swimlanes, BPMN, sequence diagrams, and architecture diagrams must be delivered as rendered graphics**, not just Mermaid syntax, plain text explanations, or ASCII layouts. When the requested output is DOCX/PDF, embed the actual SVG/PNG/vector visual in the right section of the document.
- Provide Mermaid, draw.io, or SVG source as an additional editable artifact if requested or useful. Never substitute source code for a visible diagram.
- Inspect the output if tools permit. If a renderer is unavailable, state the limitation instead of claiming that a diagram is rendered.

## Avoid AI-template aesthetics

- Decorative cover pages when not requested.
- Oversized titles, cards, random icons, and brightly colored summary boxes.
- Generic introductions and conclusions added just to create extra pages.
- Starting every section on a new page without a real reason.
- Tables whose columns all have equal width despite different content.
- Converting editable tables into images.
- Diagram text so small it cannot be read at normal zoom.

## Full documentation when starting a system from scratch

When the user asks to create a new system/project/module from the beginning, deliver **the complete BA/SA documentation package by default**. Include stakeholders/RACI, scope, BRD, PRD, FRD/SRS, workflows and swimlanes, rendered sequence diagrams and ERD, architecture when relevant, API mapping if there are integrations, role permission, validation, Business Rules, state transitions, UAT, risk and open decisions. Don't wait for the user to ask for each one separately.

See the [full greenfield documentation blueprint](greenfield-documentation.md). It includes a deliverable coverage matrix and a rendered ERD example.

## Example of a real rendered diagram

![Rendered example flowchart](../examples/diagrams/flowchart-submit-request.svg)

![Rendered example sequence diagram](../examples/diagrams/sequence-submit-request.svg)

![Rendered example ERD](../examples/diagrams/erd-request-management.svg)

These SVG examples show the required visual output. They are hypothetical flows, not validated requirements for a particular system.

## DOCX requirements

Use actual heading styles, editable tables, consistent paragraph spacing, stable numbering, and meaningful page breaks. Repeat a header row when a table continues onto the next page if the tool supports it. Avoid splitting rows across pages where possible. Use a full visible black cell grid, enforce black text in every style and run, and embed requested diagrams as graphics. Use landscape for a genuinely wide page or diagram instead of shrinking everything.

## PDF requirements

Preserve correct content, alignment, and diagram readability. Check for clipped table cells, missing grid borders, unexpected shading, orphaned headings, empty pages, missing characters, and broken images after rendering. Verify each requested diagram is present as a rendered visual. Do not simply rename a file extension to PDF.

## Content quality still matters

A nice layout does not replace accurate requirements. Check actors, triggers, validation, permissions, business rules, exceptions, source evidence, and acceptance criteria before export.

For Indonesian writing, apply the [Anti-AI Slop guide](anti-ai-slop-id.md). Technical terms remain in English.
