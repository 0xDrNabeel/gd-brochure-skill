# gd-brochure — God-Mode Brochure Design Skill

One skill to design professional, non-AI-slop brochures, flyers, and print collateral — for medical/pharma, corporate, and consumer use. Merges the strongest rules from marketing-collateral design, brochure-design-generation, taste-skill, impeccable, claude-design, and LICA print principles into a single `SKILL.md`.

## Output
- Print-ready **PDF** (headless Chromium)
- Editable **HTML** source (embedded CSS, all images base64)
- **PNG** digital proof

## Contents
- `SKILL.md` — full god-mode skill spec (brief → research → design system → structure → components → production → QA)
- `templates/tri-fold-medical.html` — A4 medical tri-fold skeleton (cover, clinical problem, product overview, evidence cards, clinical scenarios, dosing, references, disclaimer)

## Install
Drop `SKILL.md` + `templates/` into the agent's skills dir:
- Claude Code / Codex: `.agents/skills/gd-brochure/`
- Hermes: `~/.hermes/skills/creative/gd-brochure/`

## Try it
Render the bundled template to PDF:
```bash
chromium-browser --headless=new --no-sandbox --disable-gpu \
  --disable-software-rasterizer --disable-dev-shm-usage \
  --print-to-pdf=/home/ubuntu/brochure.pdf \
  --print-to-pdf-no-header --no-pdf-header-footer \
  "file:///home/ubuntu/god-brochure-skill/templates/tri-fold-medical.html"
```
(226mm page-height tweak and `pdfinfo` verification steps are in SKILL.md Phase 5.)

## License
MIT.