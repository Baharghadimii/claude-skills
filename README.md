# claude-skills

Private library of reusable Claude skills. One folder per skill under `skills/`, each holding a `SKILL.md` (frontmatter `name` + `description`, then the instructions).

| Skill | Use it for |
| --- | --- |
| `competitor-report` | Single-competitor profile report in the standard 15-section format with nine charts, BDC scorecard, sentiment tally and sourced funding timeline, written in ASD-STE100 |
| `high-noon` | House design system — white ground, navy type, one cobalt accent, sky-blue gradient bands, light serif headlines, Big Dipper constellation; tokens, type, layouts per format, components, HTML report template and a Markdown → web-report procedure |
| `plain-summary` | Plain-language summary of a document, report or academic article for a reader outside the field — fixed structure (question, method, findings, why it matters, caveats, glossary), numbers kept, jargon translated |

## Adding a skill
1. Create `skills/<skill-name>/SKILL.md`.
2. Keep the frontmatter `name` equal to the folder name.
3. Add a row to the table above.
