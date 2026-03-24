# Offer Creation Pipeline

**Version:** 1.0.0
**Author:** Sabahudin Murtic

End-to-end offer creation pipeline. Takes you from zero to a complete offer package: Offer Doc, pitch deck, VSL script, landing page, and curiosity-trigger DM openers.

---

## Quick Start

1. Install this plugin in your Claude workspace
2. Run `/offer-creation:onboard` to configure your brand, voice, and preferences
3. Run `/offer-creation:offer-creation` to start the pipeline
4. Follow the prompts — each step is interactive
5. All deliverables save to your configured output folder

---

## Commands

| Command | What It Does |
|---------|-------------|
| `/offer-creation:onboard` | One-time setup — brand colors, fonts, voice, bio, ICP. Creates your settings file. |
| `/offer-creation:offer-creation` | Full pipeline — chains all 4 skills in sequence. Can resume from any step. |

---

## Skills

| Skill | Role | Output |
|-------|------|--------|
| **offer-onboarding** | Interactive offer creation using Saba's Framework + Hormozi's Value Equation | `offer-doc.md` |
| **offer-pitch-deck** | 23-slide Hormozi-style pitch deck with brand styling | `.pptx` file |
| **offer-landing-page** | VSL script (12-section meta-framework) + landing page (11-section sales page) | `vsl-script.md` + `landing-page.md` or `.html` |
| **offer-dm-opener** | Curiosity-trigger DM templates organized by lead type and awareness level | `dm-openers.md` |

---

## How It Works

```
Settings (onboard)
    |
    v
Offer Doc ──> Pitch Deck
    |              |
    +──────────────+──> VSL + Landing Page
    |
    +──> DM Openers
```

The Offer Doc is the single source of truth. Every downstream skill reads it directly.

---

## Prerequisites

These workspace skills are referenced by the pipeline:

- **pptx skill** (`.claude/skills/pptx/`) — required for pitch deck generation (PptxGenJS + QA workflow)
- **frontend-design skill** (`.claude/skills/frontend-design/`) — optional, improves HTML landing page aesthetics

System dependencies:
- Node.js + `pptxgenjs` npm package (for .pptx creation)
- Python + `markitdown` (for deck content QA)
- LibreOffice + Poppler (for deck visual QA — `soffice`, `pdftoppm`)

---

## Output Folder

Default: `05_Attachments/output/offer-creation/`

Configurable during onboarding. All deliverables save here:
- `offer-doc.md`
- `{offer-name}-pitch-deck.pptx`
- `vsl-script.md`
- `landing-page.md` or `landing-page.html` (or both)
- `dm-openers.md`

---

## Settings File

Created by `/onboard` at `.claude/offer-creation.local.md`.

Contains: user profile, brand colors/fonts, voice/tone, bio, proof points, testimonials, ICP, output preferences. YAML frontmatter format.

---

## Frameworks Used

- **Saba's Complete Offer Framework** — transformation, 3 core problems, proven path, value stack
- **Hormozi's Grand Slam Offer** — Value Equation (dream outcome, likelihood, time delay, effort)
- **VSL Meta-Framework** — Belief Shifting + PAIS + Case Study + BFF
- **11-Section Sales Page** — Hero, Quiz, Instructor, Proof, Problems, Mistakes, Included, Bonuses, Nudge, FAQ, Guarantee
- **saba-linkedin-dm Rules** — under 300 chars, no pitching, curiosity triggers
