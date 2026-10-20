---
name: plain-summary
description: Summarize a document, report, or academic article in plain, understandable language for a reader outside the field. Use when asked to summarize, explain, simplify, "give me the gist of", or "what does this paper say" about any attached or linked PDF, DOCX, article, or pasted text — especially research papers, journal articles, preprints, white papers, policy documents, and long reports. Produces a fixed-structure summary with jargon translated, key numbers kept, and a glossary.
---

# Plain-language summary of a document or academic article

Turn a dense document into a summary that an intelligent reader with no background in the field can follow in a few minutes. Keep what matters (the question, the method, the findings, the numbers, the caveats) and translate everything else.

## Inputs to confirm before starting
Ask only if the answer is not obvious from the request. Otherwise use the defaults and say which you used in one line at the top.
- **Source**: attached file, link, or pasted text. If it is a link, fetch it. If it is a PDF or DOCX, read it from disk (use the file-reading / pdf-reading skills when they exist).
- **Reader** (default: a curious adult outside the field, no specialist vocabulary). Other options the user may name: "high-school level", "executive", "a colleague in an adjacent field".
- **Length** (default: short, under 400 words). Options: `short` (≤400 words), `medium` (≤800 words), `long` (≤1500 words, adds a section-by-section walkthrough).
- **Format** (default: markdown in the chat reply). If the user asks for a doc, file, or something to share, use the session's doc tool or write a `.md` file.

## Workflow
1. **Read the whole document first.** For a paper, read the abstract, introduction, results, discussion, and conclusion at minimum; skim methods for sample size, duration, and design. Do not summarize from the abstract alone — abstracts overstate.
2. **Identify the document type** and pick the matching template below (academic article, report / white paper, or general document).
3. **Collect the hard facts** before writing: the main claim, the numbers that back it (sample size, effect size, percentages, dates, costs), the method in one sentence, and every limitation the authors admit.
4. **Write the summary** following the template. Write it in your own words. Quote the source only when a phrase is the finding itself (e.g. a named effect) and keep any quote under 15 words.
5. **Translate jargon**: for every technical term you cannot avoid, define it in a few words the first time it appears, in parentheses or in the glossary. If a term appears more than once, add it to the glossary.
6. **Verify**: every number in the summary must appear in the source. If the source gives a range or a confidence interval, keep it; do not round it into a single confident figure. If the source does not say something, do not fill the gap — write "the paper does not say".
7. **Read it back as the target reader.** Remove any sentence they would need to look up to understand.

## Template — academic article or research paper

Use these headings exactly. Each section opens with one plain sentence that answers the heading.

**Title:** the paper's title, then authors (first author et al.), venue or journal, and year on one line.

**One-line takeaway** — one sentence a reader could repeat to a friend. No jargon. Example: "People who slept less than six hours were about twice as likely to catch a cold in the study."

1. **What question were they asking?** — the problem and why anyone cares. Two to four sentences. Name the gap the paper claims to fill.
2. **What did they do?** — the method as a story, not a protocol: who or what was studied, how many, for how long, what was measured, what was compared against. State the study design in plain terms (e.g. "a randomized experiment", "an observational survey", "a computer simulation", "a review of 40 earlier studies").
3. **What did they find?** — the main results with the numbers kept. Lead with the headline result, then two to four supporting results. Distinguish what the authors *showed* from what they *suggest*. Where a result is small, uncertain, or not statistically significant, say so plainly.
4. **Why does it matter?** — what changes if the finding holds: for practice, policy, further research, or everyday life. Keep this to what the authors argue plus one sentence of your own framing, clearly marked as such.
5. **Caveats and limitations** — bullets. Include: limitations the authors admit; sample size and who was left out; whether the result is correlation or cause; whether it has been replicated (if known from the paper); conflicts of interest or funding noted in the paper; anything that looks overstated between the abstract and the results.
6. **Key terms** — glossary table (term · plain meaning). Only terms that appear in the summary or that a reader will meet in the original.

For `long` length add **7. Section-by-section walkthrough** — one paragraph per major section of the paper, in order.

## Template — report, white paper, or policy document

**Title / author / date** on one line.

**One-line takeaway.**

1. **What is this document and who is it for?**
2. **The main argument or recommendation** — in plain words, with the top three supporting points.
3. **The evidence** — what data, cases, or sources it relies on, and how strong they look (first-hand data vs. citing others vs. opinion).
4. **What it asks the reader to do or decide** — recommendations, actions, deadlines, costs, if any.
5. **What it leaves out or glosses over** — gaps, assumptions, counter-arguments not addressed.
6. **Key terms** — glossary table.

## Template — general document (contract, memo, long email, manual, article)

**What it is, who wrote it, when.**

**One-line takeaway.**

1. **Main points** — three to seven bullets, each one plain sentence.
2. **Anything the reader must act on, agree to, or watch for** — dates, obligations, money, risks.
3. **What is unclear or missing.**
4. **Key terms** (only if the document is technical).

## Language rules
- Short sentences: aim for under 20 words; never more than 30.
- One idea per sentence, one topic per paragraph.
- Prefer the common word: "use" not "utilize", "show" not "demonstrate", "about" not "approximately", "people" not "subjects" or "participants" (unless the distinction matters).
- Active voice: "The researchers measured…" not "Measurements were taken…".
- Concrete over abstract: say "about 1 in 5" as well as "20%"; say "roughly the length of a football field" only if the comparison is accurate.
- Keep numbers. Do not replace "a 12% reduction (95% CI 4–19%)" with "a big reduction". Round for readability (12%, not 12.37%) but keep the uncertainty.
- Mark your own interpretation explicitly: "My read:" or "(this is my framing, not the authors')".
- No hype words: avoid "groundbreaking", "revolutionary", "proves". Papers rarely prove; they find, suggest, estimate, or show.
- Never invent a detail that is not in the source. If the user asks something the source does not answer, say so.

## Quality check before sending
- [ ] The one-line takeaway contains no undefined technical term.
- [ ] Every number traces to the source.
- [ ] Study design and sample size are stated for any research paper.
- [ ] At least one limitation is listed, even for a strong paper.
- [ ] Correlation vs. causation is stated correctly.
- [ ] Word count is within the chosen length.
- [ ] The target reader could explain the finding to someone else after reading it once.

## Output
Default: the summary as markdown in the reply. If the user asked for a doc or file, deliver that and add one line in chat saying which length and reader you used. Offer to go deeper on any section, produce a different length, or compare the paper against another one.
