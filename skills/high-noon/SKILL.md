---
name: high-noon
description: House design system "High Noon". Use for ANY document, report, deck, web page, PDF or one-pager we produce (competitor reports, explainers, memos, pitch material). White ground, navy type, one cobalt accent, a sky-blue gradient for hero/feature bands, light serif headlines, and a real Big Dipper constellation drawn as starbursts. Covers tokens, type, layouts per format (web page, slide deck, printable doc), components, motion and copy rules. Includes a ready HTML template and a step-by-step procedure to turn a Markdown report into a High Noon web report.
---

# High Noon design system

Calm, premium, airy. Most surfaces are white with navy text. Blue is rare and valuable: one cobalt accent, plus a sky gradient used only for heroes and 1–2 feature bands per piece. Light serif headlines give height and air. Never decorative clutter.

## 0. Quick start: Markdown report → web report

If you receive a report as Markdown (or text) and must output it in this design:

1. Read `references/markdown-to-report.md` and follow its procedure and mapping table.
2. Copy `templates/report-web.html`. It has all styles, the constellation and every component. Do not edit its `<style>` or `<script>`.
3. Replace the sample content in `<body>` with the report content. Use only the template's components.
4. Output one `.html` file. Run the checklist at the end of the reference.

The sections below define the system. The template already applies them.

## 1. Tokens (use these exact values)

| Token | Value | Use |
|---|---|---|
| Ground | `#ffffff` | page / slide background |
| Ink | `#1b2740` | body text |
| Navy | `#0b1f3a` | wordmark, darkest headlines |
| Cobalt (accent) | `#1757d6` | labels, key numbers, links, bars, one highlight per view |
| Panel | `#eef4ff` | filled cards |
| Line | `#d6deee` | rules, borders, table lines |
| Muted | `#5b6577` | secondary text, captions |
| Sky gradient | `linear-gradient(180deg,#0f55c8 0%,#1a6fdc 45%,#3a93e8 100%)` | hero, title slide, feature bands |
| On-blue line | `rgba(255,255,255,.4)` | borders/rules on sky gradient |
| Caution | `#b7791f` | "Partial / Beta" status only |
| Low score on blue | `#ffd166` | weakest bar on a blue band only |

Radius: cards 16px, chips/small tiles 12px. No shadows. No other colors. No green, no gradients other than the sky gradient.

## 2. Type

- Headlines: **Newsreader**, weight 300, letter-spacing −0.02em, line-height ~0.95–1. Italic Newsreader 300 for a single emphasized word or sub-name.
- Body, labels, numbers in tables: **Manrope** 400/500/600/700.
- Eyebrow labels: Manrope 13px (web) / 24px (slides), uppercase, letter-spacing .08em, Muted or Cobalt, weight 600–700.
- Big stat numbers: Newsreader 300 (hero stats) or Manrope 700 (table/tile numbers).
- Google Fonts: `Newsreader:ital,opsz,wght@0,6..72,300;0,6..72,400;1,6..72,300` and `Manrope:wght@400;500;600;700`.

Sizes
- Web: h1 `clamp(64px,11vw,170px)`; h2 `clamp(34px,4.6vw,58px)`; lead 20px/500; body 16–17px, line-height 1.6; tables 14.5px.
- Slides (1920×1080): title 150px; slide headline 72–84px; body 24–28px (never below 22px); stat numbers 40–64px.
- Print/PDF: h1 40–48pt; h2 22–26pt; body 10.5–11pt (never below 10pt; captions 8.5pt min).

## 3. The constellation (signature motif)

- Shape: the real **Big Dipper (Ursa Major)**, handle top-left → bowl bottom-right. Seven stars, in this relative layout (scale freely):
  `[[100,230],[260,310],[320,410],[390,520],[340,630],[500,750],[600,660]]`, edges `0-1,1-2,2-3,3-4,4-5,5-6,6-3`.
- Star style: **16-ray starburst** (long rays every 90°, medium every 45°, short in between), white core, soft radial glow. Star sizes ~5–7.5 units.
- Background: ~150 tiny white dots (r 0.3–1.6, opacity .25–.85) plus ~10 tiny starbursts. No hexagons, no grids, no labels, no star names, no invented patterns.
- **Web:** connection lines are hidden; hovering (tap on touch) a Dipper star draws only that star's connections (dash-draw ~0.5s) and scales the connected stars ×1.25.
- **Slides / print:** lines shown statically, white, 1.5px, opacity ~.7.
- Stars live **only on sky-gradient surfaces** and **never overlap text**: give them their own column/area (web hero: two-column grid, text left, stars right, wraps below text on narrow screens).

## 4. Layout per format

### Web page (scrolling report / explainer)
- Sticky top bar: wordmark/title in Newsreader 19px Navy + horizontal-scroll anchor nav (Manrope 13.5px/600 Muted) + 3px Cobalt reading-progress bar (scroll-driven).
- Hero: sky gradient, min-height ~88vh, grid `repeat(auto-fit,minmax(340px,1fr))` — eyebrow, h1, one-sentence lead, confidence note on the left; constellation cell (aspect 7/9, max 560px) on the right.
- Sections: max-width 1120px, padding 96px 32px. Each opens with a header row: h2 left, eyebrow `NN · Section name` right, 2px Line rule below; then a 20px lead sentence; then content.
- Use the sky gradient for 1–2 feature bands max (e.g. token economics, SWOT + scorecard). Everything else white.
- Fluid: no fixed widths, tables scroll horizontally inside an `overflow-x:auto` wrapper.

### Slide deck (1920×1080)
- Padding 96px 140px. Header row: headline left, eyebrow right, 3px Line rule.
- Slide 1: sky gradient + constellation (right third), eyebrow, 150px title, one-sentence lead, confidence note.
- 2–3 content slides per deck may use the sky gradient (feature/turning-point slides); the rest white.
- Grids of 2–3 cards; one idea per slide; numbers big.

### Printable doc / PDF
- White pages, Letter/A4. Cover = sky gradient + constellation with title. Inside: same header-row pattern, Line rules, Panel cards, Cobalt numbers. Feature bands become full-width blue panels with radius 16px.

## 5. Components

- **Stat tile:** 3px top rule (Ink, or Cobalt for the key one), big number, 15px Muted caption.
- **Card:** Panel fill, radius 16, padding 24–28; Cobalt eyebrow label; body 15–16px.
- **Outline card:** 2px Line border instead of fill (secondary info / "gaps").
- **Callout:** 3px Cobalt top rule + bold Cobalt label ("Assessment.", "What changed") + body.
- **Table:** 2px Ink top rule, header row bold with 1px Ink underline, body rows 1px Line; first column semibold; last column Muted when it is a source/note column.
- **Status text:** Live = Cobalt bold; Partial/Beta = Caution bold; Planned/Closed = Muted bold.
- **Bar chart:** label | track (Panel, radius 8, 16px tall) | value. Bars Ink; the subject's bar Cobalt and bold row.
- **Timeline:** 2px Line vertical rule, hollow Cobalt-ring dots, Cobalt date, body text.
- **Numbered list:** Newsreader 300 numerals in Cobalt (01, 02 …).
- **SWOT:** 2×2 outline cards on a blue band, small "Internal/External · Helpful/Harmful" caption, Newsreader quadrant title.
- **Scorecard:** 8 bars 1–10 + big Newsreader average.
- **Learn / Avoid / Exploit:** three columns, Newsreader heading (Cobalt, Muted, Cobalt), numbered rows with Line rules; "Exploit" column on Panel.

## 6. Motion (web only)

- CSS scroll-driven only: cards rise in (`translateY(28px)`→0, opacity 0→1) with `animation-timeline:view()`; bars grow from left; reading-progress bar uses `scroll(root)`.
- Constellation hover as in §3.
- Always respect `prefers-reduced-motion` (disable all). Content must be fully visible without motion.

## 7. Copy rules

- Write in **ASD-STE100 Simplified Technical English**: short sentences, one idea each, active voice, plain verbs.
- Headlines are claims, not topics ("Large and real, but the rate has collapsed.").
- **Never** include the author's name or our own company/project name. Present reports neutrally ("Competitor report", "a competing project").
- Keep confidence labels where data is sourced: Disclosed · Reported · Estimated.
- No filler, no emoji, no decorative icons.

## 8. Don'ts

- No photos or cropped images of clouds/skies; no CSS-drawn clouds.
- No hexagon grids, seals, stamps, vertical decorative rules, or invented constellations.
- No more than two sky-gradient bands per page/deck besides the hero/title.
- No stars behind text. No white text on light surfaces; no Muted text on the sky gradient (use white at ≥85% opacity).
- No other accent colors; no green palettes.

## 9. Files in this skill

- `templates/report-web.html` — standalone web report template (plain HTML/CSS/JS, no build step).
- `references/markdown-to-report.md` — Markdown → report procedure, mapping rules, checklist.

## 10. Reference builds (in this project)

- Web page: `Olas Report Web v3 - High Noon.dc.html`
- Slide deck: `Olas Report v2 - High Noon.dc.html`
- Theme board entry: `AGEX Brand Themes Round 2.dc.html` → A2
