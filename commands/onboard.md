---
description: Set up the Offer Creation Pipeline and build your complete offer package. Handles brand setup (first time) then walks you through Offer Doc, Pitch Deck (HTML), VSL + Landing Page, and DM Openers — all in one guided conversation.
argument-hint: ""
allowed-tools: Read, Write, Bash, AskUserQuestion
---

# Offer Creation Pipeline — Onboard + Build

You are running the complete Offer Creation Pipeline. This single command handles everything: brand setup (if needed) and then the full offer build — Offer Doc, HTML Pitch Deck, VSL + Landing Page, and DM Openers.

**This is interactive.** Each step requires user input. Do not skip ahead or batch steps. Ask one question at a time, wait for the answer, then move on.

---

## Phase 0 — Settings Check

Try to read `.claude/offer-creation.local.md`.

### If settings exist:

Parse all YAML frontmatter fields. Show:
> "Welcome back, **{user_name} / {business_name}**. Your brand settings are already configured.
>
> A) Proceed to offer creation
> B) Update your brand settings first
> C) Start fresh (new settings from scratch)"

- If A: proceed to Phase 1.
- If B: ask which section they want to change (profile, brand identity, voice, credibility, target audience, output preferences). Update only that section, rewrite the file. Then proceed to Phase 1.
- If C: run brand setup below (Steps 1-8), then proceed to Phase 1.

### If no settings file exists:

Run the brand setup below. This is mandatory before building an offer.

---

## Brand Setup — Steps 1-8

Walk the user through setup **one section at a time**. Wait for each answer before moving to the next. Do not ask all questions at once.

### Step 1 — User profile

Ask:
> "Welcome. I'll set up the Offer Creation Pipeline for your business — should take about 5 minutes.
>
> Let's start: What's your name and your business name? (Optional: website URL)"

### Step 2 — Brand identity

Ask these one at a time. Provide defaults — if user says "use defaults" or similar, accept them and move on.

**2a. Primary brand color:**
> "What's your primary brand color? Give me a hex code.
>
> Default: #463187 (purple). Press enter or say 'default' to use it."

**2b. Accent color:**
> "What's your accent color? Used sparingly for emphasis.
>
> Default: #FF6719 (orange)."

**2c. Background colors:**
> "Background colors — a main and an alternate.
>
> Default: #FFFFFF (white) + #E0D6FF (soft lavender)."

**2d. Title font:**
> "What font for titles and headings?
>
> Default: Archivo Black. Common alternatives: Montserrat Bold, Inter Bold, Poppins Bold."

**2e. Body font:**
> "What font for body text?
>
> Default: Montserrat. Common alternatives: Inter, Open Sans, Lato."

### Step 3 — Voice and tone

Ask these one at a time.

**3a. Voice:**
> "Describe your voice in 3 words — how should your content sound?
>
> Example: 'direct, practical, warm' or 'professional, approachable, no-BS'"

**3b. Anchor examples:**
> "Give me 2-3 sentences that sound like YOU. These could be from your website, a post, or just something you'd say to a client. I'll use these as a tone anchor."

**3c. Banned words:**
> "Are there words or phrases you never want in your copy? List them.
>
> Common bans: synergy, leverage, unlock, empower, game-changer, guru, hustle."

### Step 4 — Credibility and proof

**4a. Bio:**
> "Give me your bio in 2-3 sentences. Focus on: what you do, who you help, and your most impressive credential or result."

**4b. Proof points:**
> "List your strongest proof points — results, metrics, milestones, or achievements that show you know what you're doing.
>
> Example: 'Helped 50+ consultants build their LinkedIn pipeline', '2x revenue in 90 days for 3 clients', 'Built and sold 2 SaaS products'"

**4c. Testimonials (optional):**
> "Paste any testimonials you want to use in your materials. These will appear in your pitch deck and landing page. Skip if you don't have any yet."

### Step 5 — Target audience

**5a. Ideal client:**
> "Who is your ideal client? Describe them in 1-2 sentences — their role, business type, and situation."

**5b. Industry:**
> "What industry or niche do they operate in?"

**5c. Biggest pain point:**
> "What is their single biggest pain point — the thing that would make them seek you out?"

### Step 6 — Output preferences

**6a. Output folder:**
> "Where should the pipeline save all deliverables (Offer Doc, pitch deck, VSL, landing page, DM openers)?
>
> Default: `05_Attachments/output/offer-creation/`"

**6b. Landing page format:**
> "When the pipeline creates your landing page, do you want:
>
> A) Copy only (structured markdown — you paste into your own builder)
> B) Full HTML with your brand styling (ready to deploy)
> C) Both"

### Step 7 — Write settings file

Build the settings content from all answers. Use the Write tool to create `.claude/offer-creation.local.md`:

```
---
user_name: [name]
business_name: [business name]
website: [url or empty]
brand_primary_color: "[hex without #]"
brand_accent_color: "[hex without #]"
brand_bg_colors: "[main hex], [alternate hex]"
brand_title_font: "[font name]"
brand_body_font: "[font name]"
voice_words: "[3 words]"
voice_examples: |
  [example 1]
  [example 2]
voice_banned_words: "[comma-separated]"
bio: |
  [bio text]
proof_points: |
  [proof point 1]
  [proof point 2]
  [proof point 3]
testimonials: |
  [testimonial 1]
  [testimonial 2]
icp_description: "[ideal client description]"
icp_industry: "[industry]"
icp_pain_point: "[biggest pain point]"
output_dir: "[path]"
landing_page_format: "[copy | html | both]"
---

# Offer Creation Pipeline — Your Settings

Configured for: [user_name] / [business_name]
Last updated: [today's date]

Run /offer-creation:onboard again to update any section.
```

### Step 8 — Settings summary

Show:
```
Brand setup complete.

Profile:     [name] / [business_name]
Brand:       [primary color] + [accent color]
Fonts:       [title font] / [body font]
Voice:       [3 words]
ICP:         [1-line description]
Output:      [output_dir]
Landing:     [format preference]
```

Then immediately proceed to Phase 1:
> "Now let's build your offer."

---

## Phase 1 — Offer Doc

Set `output_dir` from settings (default: `05_Attachments/output/offer-creation/`). Ensure the output directory exists. If not, create it.

Check if `{output_dir}/offer-doc.md` exists.

### If it exists:

Read it and show a summary:
> "**Offer Doc found:** {Offer Name}
> Transformation: {Signature Transformation}
> Price: {price} | Value: ${total perceived value}
>
> Options:
> A) Continue to Pitch Deck
> B) Redo the Offer Doc from scratch
> C) Refine specific sections of the Offer Doc
> D) View the full Offer Doc"

If A: proceed to Phase 2.
If B: read and follow `skills/offer-onboarding/SKILL.md`. Start from Step 1.
If C: read and follow `skills/offer-onboarding/SKILL.md`. Start from Step 0 (refinement path).
If D: show the full doc, then ask A/B/C again.

### If it does not exist:

> "No Offer Doc found. Let's build your offer from scratch."

Read and follow `skills/offer-onboarding/SKILL.md`. Execute all steps interactively.

After completion:
> "Offer Doc complete. Ready for the Pitch Deck?"

Wait for confirmation before proceeding.

---

## Phase 2 — HTML Pitch Deck

Check if `{output_dir}/*-pitch-deck.html` exists.

### If it exists:

> "**Pitch Deck found:** {filename}
>
> Options:
> A) Continue to VSL + Landing Page
> B) Redo the Pitch Deck"

If A: proceed to Phase 3.
If B: read and follow `skills/offer-pitch-deck/SKILL.md`.

### If it does not exist:

> "Creating your pitch deck from the Offer Doc — as a styled HTML presentation."

Read and follow `skills/offer-pitch-deck/SKILL.md`. Execute all steps.

After completion:
> "Pitch Deck generated. Ready for VSL + Landing Page?"

Wait for confirmation.

---

## Phase 3 — VSL Script + Landing Page

Check if `{output_dir}/vsl-script.md` exists AND if `{output_dir}/landing-page.md` or `{output_dir}/landing-page.html` exists.

### If both exist:

> "**VSL Script found:** {word count} words
> **Landing Page found:** {filename}
>
> Options:
> A) Continue to DM Openers
> B) Redo both VSL + Landing Page
> C) Redo VSL only
> D) Redo Landing Page only"

If A: proceed to Phase 4.
If B: read and follow `skills/offer-landing-page/SKILL.md` (full skill).
If C: read and follow `skills/offer-landing-page/SKILL.md` (Part 1 only — Steps 2-4).
If D: read and follow `skills/offer-landing-page/SKILL.md` (Part 2 only — Steps 5-6).

### If neither exists:

> "Creating your VSL script and landing page."

Read and follow `skills/offer-landing-page/SKILL.md`. Execute all steps.

### If only one exists:

Tell user which one is missing, create only the missing one using the relevant part of the skill.

After completion:
> "VSL and Landing Page complete. Ready for DM Openers?"

Wait for confirmation.

---

## Phase 4 — DM Openers

Check if `{output_dir}/dm-openers.md` exists.

### If it exists:

> "**DM Openers found:** {template count} templates
>
> Options:
> A) Finish — show final report
> B) Redo the DM Openers"

If A: proceed to Phase 5.
If B: read and follow `skills/offer-dm-opener/SKILL.md`.

### If it does not exist:

> "Creating your DM openers — curiosity triggers, not pitches."

Read and follow `skills/offer-dm-opener/SKILL.md`. Execute all steps.

After completion: proceed to Phase 5.

---

## Phase 5 — Final Report

Show the complete summary:

```
Offer Creation Pipeline — Complete

Deliverables for: {user_name} / {business_name}
Offer: {Offer Name}

  Offer Doc:      {output_dir}/offer-doc.md
  Pitch Deck:     {output_dir}/{filename}-pitch-deck.html
  VSL Script:     {output_dir}/vsl-script.md
  Landing Page:   {output_dir}/landing-page.{ext}
  DM Openers:     {output_dir}/dm-openers.md

Summary:
  Transformation: {Signature Transformation}
  Price:          {price}
  Perceived Value: ${total}
  Guarantee:      {guarantee type}
  CTA:            {next step}
  DM Templates:   {count} templates across {types} types

All files saved to: {output_dir}/
```

Then suggest next steps:
> "Your offer package is complete. Here's what to do next:
>
> 1. **Review all deliverables** — read through each file and refine anything that doesn't feel right
> 2. **Record your VSL** — use the script as a teleprompter or talking points
> 3. **Build your landing page** — paste the copy into your builder or deploy the HTML
> 4. **Open the pitch deck** — view the HTML file in your browser and present from there
> 5. **Start sending DMs** — use the template bank to open conversations

---

## Phase 6 — Plugin Restructure Offer

After showing the final report, ask:

> "Would you like me to add individual commands to this plugin so you can run each step separately in the future?
>
> This would add:
> - `/offer-creation:offer-doc` — create or refine an Offer Doc
> - `/offer-creation:pitch-deck` — generate the HTML pitch deck
> - `/offer-creation:landing-page` — create VSL + landing page
> - `/offer-creation:dm-openers` — generate DM opener templates
>
> Your `/offer-creation:onboard` command stays — use it anytime you want to create a new offer from scratch or update your brand settings.
>
> Want me to add these?"

If yes: create the 4 individual command files. Each one should:
1. Read settings (if missing, tell them to run `/offer-creation:onboard`)
2. Read the Offer Doc (required for all except offer-doc itself)
3. Call the corresponding skill
4. Save output

If no: done. The onboard command remains the single entry point.
