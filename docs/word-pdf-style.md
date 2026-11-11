# Word and PDF formatting standard

Produce documents that resemble normal internal BA/SA work, not a decorative AI-generated brochure. Use an organization's own template if provided.

## Default page style

| Element | Default |
|---|---|
| Page size | A4 portrait |
| Margins | 2.2 cm top/bottom, approximately 2.3–2.5 cm left/right |
| Font | **Calibri** for body, headings, and tables |
| Body | 10.5–11 pt |
| Line spacing | 1.1–1.15 |
| Paragraph gap | 4–6 pt after |
| Document title | 15–16 pt, left-aligned |
| Section heading | 12–13 pt, bold when needed |
| Table | Calibri 9–10 pt, **full visible grid** (0.5–0.75 pt solid black/dark-gray borders on every cell), white background, no shading or color fill |
| Header and footer | Do not add unless requested |

## Non-negotiable font, table, and rendered-diagram rules

- **Font: Calibri only by default**, including title, headings, paragraphs, captions, and tables. Never silently substitute Aptos or Arial. If Calibri is unavailable, report the fallback, or honor the user's specified corporate template.
- **Tables: visible full borders on every cell** with black or dark-gray solid lines (about 0.5–0.75 pt). Keep every cell white with **no background color, gray header fill, alternating row shading, colored banding, or gradient**. Use Calibri bold for column headings. Grid lines must remain visible when printed or exported.
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

## Example of a real rendered diagram

![Rendered example flowchart](../examples/diagrams/flowchart-submit-request.svg)

![Rendered example sequence diagram](../examples/diagrams/sequence-submit-request.svg)

These SVG examples show the required visual output. They are hypothetical flows, not validated requirements for a particular system.

## DOCX requirements

Use actual heading styles, editable tables, consistent paragraph spacing, stable numbering, and meaningful page breaks. Repeat a header row when a table continues onto the next page if the tool supports it. Avoid splitting rows across pages where possible. Use a full visible cell grid and embed requested diagrams as graphics. Use landscape for a genuinely wide page or diagram instead of shrinking everything.

## PDF requirements

Preserve correct content, alignment, and diagram readability. Check for clipped table cells, missing grid borders, unexpected shading, orphaned headings, empty pages, missing characters, and broken images after rendering. Verify each requested diagram is present as a rendered visual. Do not simply rename a file extension to PDF.

## Content quality still matters

A nice layout does not replace accurate requirements. Check actors, triggers, validation, permissions, business rules, exceptions, source evidence, and acceptance criteria before export.

For Indonesian writing, apply the [Anti-AI Slop guide](anti-ai-slop-id.md). Technical terms remain in English.
