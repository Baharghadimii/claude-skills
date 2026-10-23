# Markdown → High Noon web report

Use this procedure when you receive a report as Markdown and must output it as a High Noon web page.

## Output

- One self-contained `.html` file. Name: `<subject-slug>-report.html`.
- Start from `templates/report-web.html`. Copy it fully. Do not change its `<style>` or `<script>` blocks.
- Replace only the content inside `<body>`. Use only the components and classes in the template.
- No other CSS, colors, fonts, icons, emoji or images (except charts or diagrams that the source has).
- To get a PDF, print the page from the browser. The template has print rules.

## Procedure

1. Read the full Markdown. List all sections, tables, lists and figures.
2. Map each Markdown element to a component (table below).
3. Pick the blue bands (max 2, see "Blue bands").
4. Write the claim headlines (see "Headlines").
5. Rewrite the copy in ASD-STE100 Simplified Technical English. Keep every fact, number, date, name, source and confidence label.
6. Fill the template. Delete the template components that you do not use.
7. Check the result against the checklist at the end.

## Element mapping

| Markdown | Component | Rule |
|---|---|---|
| `# Title` | Hero `h1` | Put an alternative name or ticker in `<em>(…)</em>`. Also set `<title>`, wordmark and footer. |
| Date, version or "as of" line near the top | Hero eyebrow + confidence note | Eyebrow: `Report type · Date`. Confidence note: data date + `Confidence labels: Disclosed · Reported · Estimated` if the source uses them. |
| First paragraph or TL;DR | Hero lead | One sentence. Shorten. Keep the full text in the summary lead. |
| `## Section` | `<section>` + `.sec-head` | `id` = short slug. `data-nav` = 1–2 word label. Eyebrow = `NN · Section name` (two-digit number, original order). |
| First paragraph of a section | `.lead` | 1–3 sentences. |
| Other paragraphs | `.body` | One element for each paragraph. |
| `### Sub-section` | `h3.sub` | If 2–6 consecutive `###` blocks each have only a short paragraph, use `.cards` instead (heading → `.label`). |
| 3–4 headline numbers (key figures, bold numbers in the summary) | `.stats` | Max 4 tiles. Exactly one `.key` tile (the most important number). Number in `.num`, meaning in `.cap`. |
| Bullet list | `.bullets` | A bold lead-in (`**X.**`) stays bold. |
| Numbered list | `.numbered` | — |
| Table | `.tbl` | Keep all rows and columns. A column named Source, Note, Notes, Comment or Confidence gets `class="note"` on its cells. Number columns get `num-col`. |
| Status words in a table (Live, Partial, Beta, Planned, Closed, Deprecated) | `.live` / `.partial` / `.planned` | Live → `live`. Partial, Beta → `partial`. Planned, Closed, Deprecated → `planned`. |
| Table of entity + one number, used to compare (ranking, market share, volume) | `.bars` **and** keep the table if it has more columns | Width = value ÷ largest value × 100%. Add `subject` to the report subject's row. |
| List or table of dated events | `.timeline` | Date → `.tl-date`. Keep the source order. |
| 3–6 years or phases with a short label each | `.milestones` | — |
| Blockquote, or a paragraph that starts with "Assessment", "Note", "Key takeaway", "What changed", "Bottom line" | `.callout` | Label in `<b>…</b>` as the first child. |
| "Gaps", "Unknowns", "Limitations", "Risks not covered" | `.card.outline` | — |
| SWOT (four lists or a 2×2 table) | `.swot` | Order: Strengths, Weaknesses, Opportunities, Threats. |
| Scorecard (criteria with scores 1–10) | `.score-avg` + `.bars` | Width = score × 10%. Average to 1 decimal. On a blue band, add `low` to the lowest row. |
| Learn / Avoid / Exploit, or Do / Don't / Opportunity | `.lae` | Third column gets `exploit`, second gets `avoid`. |
| Image of a chart or diagram | `.figure` | Keep the alt text and the caption. Never on a blue band. |
| Links | `<a>` | Keep all links. |
| Footnotes and source lists | Last section ("Appendix" or "Sources") as `.tbl` or `.numbered` | — |

If an element fits no rule, use `.body` paragraphs. Never drop content.

## Blue bands

- Max 2 sections get `class="band"`. The hero does not count.
- Priority: (1) the section about economics, pricing, tokens or business model; (2) SWOT or scorecard. If neither exists, use the section with the main turning point, or use no band.
- Never put two bands next to each other.

## Headlines

- Each `h2` is a claim, not a topic. Max 8 words. End with a full stop.
  - Topic: "Traction" → Claim: "Large and real, but the rate has collapsed."
- Make the claim from the section's own content. Do not add opinions that the source does not support.
- The original section name stays in the eyebrow (`07 · Traction`).
- If the Markdown heading is already a claim, use it.

## Copy rules

- ASD-STE100: short sentences (max 20 words), one idea each, active voice, simple verbs, consistent terms.
- Do not invent, round or change numbers. Keep units and dates as in the source.
- Keep confidence labels (Disclosed · Reported · Estimated) where the source has them.
- Never include the author's name or the name of our company or project. Present competitor reports neutrally ("a competing project").
- No filler, no emoji, no decorative icons.

## Checklist

- [ ] The hero is first, with the constellation on the right and no text over the stars.
- [ ] Every `##` section of the source exists, in the same order, with `id`, `data-nav` and an `NN · Name` eyebrow.
- [ ] Every table row, figure, date and source from the Markdown is in the page.
- [ ] Max 2 blue bands, not next to each other.
- [ ] Max 4 stat tiles per group, one `.key`.
- [ ] Each `h2` is a claim.
- [ ] No styles, colors or fonts outside the template.
- [ ] No author name, no own company or project name.
- [ ] The page works at 375px width (tables scroll sideways).
