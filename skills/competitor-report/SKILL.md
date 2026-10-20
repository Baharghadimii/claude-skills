---
name: competitor-report
description: Build a single-competitor profile report (crypto/AI-agent protocol or any tech company) in our standard 15-section format with charts, scorecard, sentiment and sourced funding timeline, written in ASD-STE100 Simplified Technical English. Use when asked for a competitor report, competitor profile, or competitive analysis of one named company or protocol.
---

# Competitor report (single-company profile)

Produce one report per competitor, in a doc (or a markdown file when no doc tool exists), following the exact structure below. Every figure carries a source link and a snapshot date. Nothing about the user's own project unless they ask.

## Inputs to confirm before starting
- Competitor name and canonical URLs (site, docs, GitHub, token page).
- Snapshot date (default: today) and the reader (internal team, investors, board).
- Whether to include a "your project" column (default: no).
- Language: ASD-STE100 Simplified Technical English (default). Use standard business English only when the user asks for it.

## Workflow
1. Create the doc skeleton first (title, byline with as-of date, one pending block per section below), open it, then fill one section per write.
2. Research in parallel, one track each (use subagents if available; otherwise do sequentially). Each track saves notes with every fact + URL + confidence label:
   - **Product and company**: history, founders, architecture, products, chains, roadmap, strengths/weaknesses.
   - **Funding and financials**: every round (date, amount, lead, participants, valuation), token supply/allocation/vesting/emissions, market cap and FDV history, treasury, revenue/fees, investor overlap.
   - **Traction**: usage metrics over time from the project's dashboard, on-chain explorers, DefiLlama/Dune, press; note which are self-reported.
   - **Market context**: category definition, segments, size, adjacent projects with market caps, standards, trends, risks.
   - **Sentiment, marketing and AI visibility**: GitHub issues/PRs, reviews, Reddit/X/Discord if indexed, analyst pages; theme tally (positive vs negative mentions per theme); per-channel reach (X, Discord, Telegram, YouTube, blog cadence, events, GitHub, web traffic via Similarweb); how AI search and aggregators describe the competitor and which category queries it appears in.
3. Fill the sections in order. Draw the visuals (see list) rather than tabling them. Look at each rendered chart and fix overlaps/clipping before moving on.
4. Finish with the appendices, then a verification pass: every number traceable to its link; conflicts listed in Appendix A.

## Confidence labels (use throughout)
- **Disclosed** = project primary source or on-chain.
- **Reported** = third-party press or aggregator.
- **Estimated** = derived in the report from cited figures; show the arithmetic.

## Report structure (headings exactly as below; each section opens with one sentence stating its finding with a number or date)

**Title:** `Competitor Report: <Name>` · byline: as-of date · author.

1. **Executive summary** — one-sentence verdict; bullets: what it is, where it stands (3–5 live metrics), money (raised, market cap, treasury, revenue), strategic direction, sentiment and reach, and 3–5 findings for a competitor.
2. **Scope and methodology** — table: criteria, primary sources, third-party sources, confidence labels; caveats paragraph (self-reported metrics, round labels, unreachable pages).
3. **Market context** — segment table (segment · representative projects · competitor's position); size and growth signals with sources; token/market-cap ranking among peers; **positioning map** (2×2: what is sold × main buyer); one paragraph naming direct / indirect / substitute competitors.
4. **Company overview and history** — overview table (entity, founders, mission, lineage, legal structure, brand); **milestone timeline** drawing (founding → latest, 10–15 milestones on two tiers each side of the axis); one paragraph on the arc.
5. **Product and architecture** — **architecture diagram** (layers: products / protocol / framework / settlement); one paragraph per product; "what changed this year"; **feature matrix** table (capability · what · status · evidence).
6. **Token economics** (or pricing/business model for non-token companies) — supply table; **supply-by-holder and emissions-by-group bar charts**; cap and allocation; emissions; staking; liquidity; fees and burn; assessment with the design choices a competitor should not copy.
7. **Traction** — **cumulative usage line chart** with active-user markers; current-metrics table; concentration; performance (company-reported, labelled); developers/users; gaps.
8. **Funding and financials** — funding timeline table newest-first (date · event · amount · lead and participants · valuation · confidence); **funding events bar chart**; round interpretation; **market-cap line chart** since launch with the raise marked; treasury table; revenue paragraph; investors and overlap.
9. **Go-to-market, ecosystem and partnerships** — target-users table (audience · offer · channel); programs and events; partnerships by type; geography; assessment; **marketing channels table** (channel · reach · cadence · source); **AI visibility** paragraph (which queries it appears in, how aggregators/AI describe it, stale descriptions, mindshare metrics).
10. **Customer feedback and community sentiment** — how measured and its limits; **diverging sentiment chart** (negative left / positive right, by theme, with totals in subtitle and a note on channels that are private); end users; developers; token holders / customers; incidents and response; balance and trend; reading for a competitor.
11. **Governance and security** — parameters table; recent votes with turnout; security (audits, bounties, admin keys); assessment.
12. **Recent developments and roadmap** — shipped table newest-first (date · development · source); roadmap bullets (dated or explicitly undated); direction of travel.
13. **SWOT** — one 2×2 table (Internal/External × Helpful/Harmful) with dense, sourced bullets; **BDC scorecard** bar chart: 1–10 on product, people, partnerships, place, positioning, promotion, reputation, pricing, each with a one-line reason, average in subtitle.
14. **Implications for a competing project** — Learn from / Avoid / Exploit (numbered) and Triggers to watch (bullets).
15. **Appendices** — A. data conflicts and gaps table (item · conflict · handling); B. glossary; C. sources grouped (primary, market data, funding, press, market context); D. changelog table.

## Language: ASD-STE100 Simplified Technical English (default)
Write all text in ASD-STE100 (Simplified Technical English): prose, table cells, chart titles, subtitles, labels, captions and notes. Facts, figures, names and links do not change.

**Sentences**
- Maximum 25 words in a descriptive sentence; maximum 20 words in an instruction.
- One topic in each sentence. Split a long sentence into two or more sentences.
- Maximum 6 sentences in a paragraph; one topic in each paragraph.
- A list of more than three items with details: write a short sentence to introduce it, then use a bullet list or short sentences ("Q1 2025: it burned 77.9M OLAS. Q2 2025: ...").
- Source lists, ticker rankings and table cells that only list names can be longer.

**Verbs and voice**
- Use the active voice ("The DAO cut emissions", not "Emissions were cut").
- Use simple tenses: simple present, simple past, simple future. Do not use the -ing form as a verb ("It is moving" → "It moves").
- Use the imperative for instructions ("Do not copy this design").
- Do not use phrasal verbs when a simple verb exists ("set up" is acceptable as a technical name; "carry out" → "do").

**Words**
- Use approved, common words with one meaning ("use" not "utilize", "start" not "commence", "help" not "facilitate", "about" not "approximately").
- Keep one word for one meaning in the full report (for example, always "daily active agents", not also "active users").
- Technical names (OLAS, veOLAS, ERC-8004, x402, Proof of Active Agent) are allowed. Define each one in the Glossary.
- Noun clusters: maximum three words ("agent transaction count" is OK; "on-chain agent transaction count growth" is not). Use "of" or "for" to break them.
- Use articles ("the", "a") and "this/these" where they make the meaning clear.
- No contractions, no "e.g." / "i.e." (write "for example" / "that is"), no "via" (write "through"), no slang or idioms ("rug", "moat" only inside quotes).
- Do not use "~" for "about" (markdown can show it as strikethrough). Write "about".
- Avoid the possessive "'s" for things; write "the reach of Olas", "the support channels of Olas".

**Report-specific**
- Section lead sentence: the point, with a number or a date, in 25 words or fewer. If needed, use two or three short sentences.
- Quotes from sources stay as written, in quotation marks. Do not rewrite a quote into STE.
- Chart titles: one or two short sentences ("20.8M lifetime transactions. The pace is slower."). Check that longer STE titles fit the chart width.
- Confidence labels (Disclosed / Reported / Estimated) stay the same.

**STE check before delivery**
- Run a script that splits the text into sentences and lists every sentence with more than 25 words. Fix all prose sentences in the list.
- Search for "which", "e.g.", "i.e.", "via", "'s", "n't", "~" and "-ing" verb forms; rewrite where they break the rules.
- STE written this way follows the rules but is not certified. Say so to the user unless an STE checker tool was used.

## Visual rules
- One finding per chart, stated in the title with its number; subtitle = units, source, date.
- Grey for context, one accent for the subject; green/red only for sentiment or good/bad.
- Milestone timeline: dates placed from data rows, labels on two tiers per side to avoid overlaps.
- Positioning map: axes named in plain words, four quadrant labels, subject highlighted, note that placements are the report's judgement.
- Scorecard: bars 1–10, reason text under each bar, strong scores (≥7) in accent.
- After each chart, look at the render and fix clipped or overlapping labels.

## Writing rules
- First sentence of every section = the point, with a number or date.
- Specifics over adjectives; follow the STE rules above; no "this section outlines".
- Self-reported metrics are labelled; aggregator round labels are not treated as disclosed structure.
- Tables for items × attributes; charts for five or more values over time or across items; prose for two or three numbers.
- Close with one line: what the reader can do now (edit, comment, share).

## Final checks
- [ ] Every number has a link and a date; estimates show arithmetic.
- [ ] Appendix A lists every conflict between sources.
- [ ] Nine visuals present: positioning map, milestone timeline, architecture, supply + emissions, usage line, funding bars, market-cap line, sentiment, scorecard.
- [ ] Executive summary numbers match the body.
- [ ] Section numbering 1–15 continuous; changelog row added.
- [ ] STE check done: no prose sentence over 25 words; active voice; approved words; chart text in STE too.
