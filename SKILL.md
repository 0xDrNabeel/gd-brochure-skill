---
name: gd-brochure
description: "God-mode professional brochure & marketing-collateral design skill — tri-fold/double-sided A4 brochures, flyers, rack cards, one-sheets, posters, infographics, leave-behinds, and promotional material for medical, pharma, corporate, or consumer use. Combines evidence-based content rigor (pharma), real print typesetting rules, and anti-slop design taste. Produces print-ready PDF + editable HTML/SVG + PNG proof. Trigger: user asks to design, build, redraw, critique, or export any brochure, flyer, leaflet, rack card, detail aid, one-sheet, poster, or print collateral."
version: 2.0.0
author: Hermes Agent (Nabeel)
license: MIT
metadata:
  hermes:
    tags: [design, brochure, flyer, print, pdf, html, svg, pharma, medical, collateral, branding]
    related_skills: [claude-design, docx, powerpoint, canvas-design]
---

# GD-BROCHURE — God-Mode Professional Brochure Design

The single reference for producing a brochuure, flyer, or print collateral that looks professionally designed (not AI-generated) AND carries accurate, defensible copy. Merge of the strongest rules from: Marketing Collateral Design (Grade A), Brochure Design Generation, taste-skill, Impeccable, canvas-design, claude-design, LICA print-design principles, and pharma-detail-aids.

## When to Use

- Any printed/shippable marketing piece: tri-fold A4 brochure, bi-fold, flyer/leaflet, rack card, one-sheet/one-pager, poster, infographic, business card, press kit.
- Medical / pharmaceutical / HCP promotional material (evidence-gated, regulatory-sensitive).
- Corporate, event, hospitality, product, or services collateral.
- Redesigning or critiquing an existing print piece.

**Deliverable default:** self-contained `HTML` source (embedded CSS) + rendered **PDF** (print) + **PNG** (proof/digital). Use `docx`/`pptx` only when the user explicitly needs non-technical editing in Word/PowerPoint.

## The Core Rule (read every time)

> **Image models are art departments, NOT typesetters.**

Never render headline text, prices, claims, or legal copy as pixels inside an image. All real wording must be deterministic HTML/SVG text. Generate/source imagery separately; compose text and vector elements deterministically. This keeps copy exact, editable, and print-sharp.

## Phase 0 — Brief & Content (never skip)

Ask/collect before designing:
1. **Product/service + one primary message.** A viewer must get the subject + intended action within **3 seconds**.
2. **Audience** — consumer vs HCP (doctor/pharmacist) vs technical buyer. Changes language, density, claims allowed.
3. **Evidence/claims**: for medical/pharma, cite REAL label + PubMed evidence (see Pharma section). Never fabricate numbers.
4. **Format**: tri-fold (A4, 6 panels), bi-fold (4), flyer (1 side), rack card (US 4x6 / 10x21cm), one-sheet (A4). Ask, or default A4 tri-fold.
5. **Brand** — logo, primary + accent colors, fonts (ask or propose). If none, build a restrained palette.
6. **Language** — confirm (Arabic / English / bilingual — user is Baghdad-based; medical pros often prefer English).
7. **Outputs needed** — print PDF, digital PNG, editable docx, or all three.

## Phase 1 — Research (medical/pharma mandatory, corporate optional)

For clinical/promotional claims, never fabricate. Chain:
1. **Label / specs** — user's photo or official HCP portal = ground truth.
2. **Evidence** — PubMed MCP tools; search by *ingredient + condition + population* (brand-name searches return empty). Capture PMID, journal, year, key finding.
3. **Format every claim** as `Ingredient X → mechanism → evidence [Study, Journal, Year]` with citation.
4. Frame interventions as *nutritional support / adjunct*, never "treats/cures." Applies to licensed professionals note at footer.

## Phase 2 — Design System (anti-slop fundamentals)

Before any styling, set the system:

### Typography
- **Max 2 families** (1 serif/editorial + 1 sans), 3 sizes max per family. A serif display (e.g. Cormorant Garamond, Fraunces, Newsreader) + clean sans (Jost, Inter, Geist, Archivo) reads high-end.
- Headline hierarchy via **size, weight, spacing, contrast** — not decoration.
- Body ≥ 10pt print, any line of small legal text ≥ 7pt. WCAG-contrast against backgrounds.
- Don't fake "AI fonts" — avoid heavy/default template look. Optionally load from Google Fonts, but embed/download for self-contained PDF.

### Palette
- Choose 1 base + 1 accent max (start). Cooler/cleaner reads premium; avoid every-element-equal color.
- Medical: trust cues — deep teal/navy/steel blue, soft white, one warm accent (amber/mint). Reserve red for warnings only.
- Check contrast: text_on_accent and text_on_photo both need AA.

### Layout / Grid
- **One grid** before styling: margins, columns, baseline rhythm, alignment anchors.
- **One focal system** — pick image-led, type-led, or info-led. Don't give everything equal weight.
- **Real hierarchy before decoration** — solve order with scale/spacing/alignment/contrast first.
- Standard print: A4 tri-fold panels each ~98–99mm wide, margins 12–15mm, approx 300dpi for raster.

### Imagery
- Separate image generation from layout. Prefer: user product photos > CSS-drawn product/shapes > Wikimedia Commons generic medical imagery > licensed stock.
- **Base64-embed** all images in the HTML so `file://` headless-Chromium PDF rendering keeps them.

## Phase 3 — Brochure Structure (proven template)

### Medical / pharma (evidence-led):
```
[Cover: product + tagline + audience cue]
Panel 1  The Clinical Problem   — prevalence, management gap, why nutrition/intervention matters
Panel 2  Product Overview       — what it is, age/format, key composition table, differentiation
Panel 3  Evidence-Based Benefits— Ingredient → mechanism → evidence [PMID]; evidence cards
Panel 4  Clinical Scenarios     — patient profiles, "consider when..."
Panel 5  Dosing & Usage         — prep steps, daily intake, safety
Panel 6  About / Contact / Refs — manufacturer, regulatory disclaimer, references
```
Tri-fold reading order (front): cover → center → right; (back when unfolded): left → center-left → center. Place the **call-to-action / key offer on the correct physical panel**.

**Bi-fold (A4 folded once → 4 panels, ~148×210mm each):** page 1 outside = back cover (left) + front cover (right); page 2 inside = clinical content. See `templates/bi-fold-medical.html`.

### Consumer / corporate (benefit-led):
```
Cover (hook + brand) → Problem/Pain → Solution/Offer → How it works → Proof/Testimonials(Social) → Pricing/Package → CTA + contact → Footer/legal
```

## Phase 4 — Component Library (use these, don't reinvent)

- **Nutrition/fact tables** — real per-100g/100ml numbers, clean ruled layout.
- **Evidence cards** — claim + mechanism + citation [PMID].
- **Stat boxes / callout** — one big number + short label, for the focal stat.
- **Dosing/prep steps** — numbered vertical steps with icons.
- **Testimonial / quote block** — serif quote, attribution.
- **Offer/pricing card** — clear price, CTA button.
- **Image overlay panel** — product shot over a soft color wash.
- **Footer** — tiny legal/regulatory line, consistent border.

## Phase 5 — Production (print workflow)

1. Author `brochure.html` with embedded CSS — panel/section layout matching chosen format.
2. **Verify by rendering, not by inspection.** Render → look → fix → re-render (loop).
3. Render PDF via headless Chromium:
```bash
chromium-browser --headless=new --no-sandbox --disable-gpu \
  --disable-software-rasterizer --disable-dev-shm-usage \
  --print-to-pdf=/home/ubuntu/brochure.pdf \
  --print-to-pdf-no-header --no-pdf-header-footer \
  "file:///home/ubuntu/brochure.html"
```
   - File MUST live in `/home/ubuntu/` (snap Chromium can't read `/tmp`).
   - Set print page height to **296mm** (not 297mm) to avoid blank trailing pages.
   - Verify: `pdfinfo brochure.pdf | grep Pages`. DBus/AppArmor stderr noise is harmless; look for "bytes written".
4. Render PNG proof from the same HTML (Chromium `--screenshot` or screenshot a `@media screen` variant). Check at intended print size, and at phone-thumbnail for digital pieces.
5. **Context proof:** review print at physical size or faithful proof, digital at thumbnail size.
6. Optional editable master: export to `docx` for client edits (use docx skill); deliver alongside PDF.

## Phase 6 — QA Checklist (run before shipping)

- ☐ Text, numbers, URLs, legal exact — no pixel-rendered copy
- ☐ One clear primary message; 3-sec comprehension
- ☐ Claims tied to real evidence/label (medical: PMIDs present)
- ☐ Color contrast AA on all text backgrounds
- ☐ One grid + one focal system respected; no equal-weight clutter
- ☐ Correct fold/panel order for format; CTA on right panel
- ☐ Brand colors/fonts applied; no template/AI-slop tell
- ☐ Appears at correct final size/sharpenness for print
- ☐ PDF pages correct; images embedded (base64), not broken links

## Pitfalls

1. **Never fabricate nutrition/medical numbers.** Wrong numbers destroy doctor credibility. Ask for the label photo if exact values missing.
2. **No "treats/cures" claims.** Frame as support/adjunct; include regulatory disclaimer.
3. **Brand-name PubMed search returns empty** — search ingredient+condition+population.
4. **Don't render real text as pixels.** Deterministic HTML/SVG text only.
5. **External image URLs break in `file://` PDF** — base64-embed everything.
6. **Standard 297mm causes blank pages** — use 296mm.
7. **Skipping render-QA.** Source inspection is not visual QA — render, look, fix.
8. **Too many colors/fonts** = AI-slop. Restraint reads professional.

## Local layout & ownership

This skill is agent-owned and lives at `~/.hermes/skills/creative/gd-brochure/`. Make edits in place THERE (`SKILL.md` + `templates/`); the GitHub repo `gd-brochure-skill` is the public mirror. Reuse the bundled template for real jobs — do not rebuild brochure CSS from scratch each time. Additional evidence depth (calcium/vitD/iron → bone, Novalac Genio 3 Plus label) lives in the `pharma-detail-aids` skill's `references/` — load that skill when a medical/pharma job needs the citations.

## References (bundled)

- `templates/tri-fold-medical.html` — clean A4 tri-fold skeleton (panel grid, nutrition tables, evidence cards, stat boxes, dosing steps, image overlay). Fully commented: replace content + brand tokens, render to PDF.
- `templates/bi-fold-medical.html` — A4 bi-fold (hi-fold) skeleton, 4 panels ~148×210mm each: page 1 outside (back cover + front cover), page 2 inside (clinical content + evidence + dosing). Same component library, landscape pages.