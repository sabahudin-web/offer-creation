---
name: offer-pitch-deck
description: Creates a 23-slide Hormozi-style pitch deck as a styled HTML presentation from an Offer Doc. Uses brand colors, fonts, and responsive CSS. Presents slide outline for approval before generating. No PowerPoint dependency.
tools:
  - Read
  - Write
  - AskUserQuestion
---

# Offer Pitch Deck (HTML)

You are creating a pitch deck from the user's Offer Doc. This is a 23-slide Hormozi-style deck that sells through clarity, proof, and specificity — delivered as a single HTML file that can be opened in any browser.

---

## Step 1 — Read inputs

1. Read the Offer Doc from `{output_dir}/offer-doc.md` (output_dir from settings).
2. Read settings from `.claude/offer-creation.local.md`.
3. Extract these mandatory variables from the Offer Doc:

| Variable | Source Section |
|----------|---------------|
| Offer Name | ## Offer Name |
| Target Audience | ## Ideal Client |
| Core Problem | ## Core Problems > Problem 1 |
| All 3 Problems | ## Core Problems |
| Desired Outcome | ## Dream Outcome |
| Signature Transformation | ## Signature Transformation |
| One Outcome | ## One Outcome |
| Unique Mechanism | ## Unique Mechanism |
| Proven Path (3 phases) | ## Proven Path |
| Objections + Counters (3) | ## Objections and Counters |
| Value Stack | ## Value Stack |
| Bonus Stack | ## Bonus Stack |
| Guarantee | ## Guarantee |
| Investment / Price | ## Investment |
| Urgency / Scarcity | ## Urgency / Scarcity |
| Next Steps / CTA | ## Next Steps |

From settings:
| Variable | Field |
|----------|-------|
| User Name | user_name |
| Business Name | business_name |
| Bio | bio |
| Proof Points | proof_points |
| Testimonials | testimonials |

4. If any critical fields are missing from the Offer Doc, ask the user to provide them before continuing. Do not generate a deck with gaps.

---

## Step 2 — Ask for additional context

Before generating, ask:
> "I have your Offer Doc loaded. A few quick questions to make this deck specific:
>
> 1. Is this deck for a specific client/prospect, or a general-purpose sales deck?
> 2. Do you have any case study details beyond what's in your proof points? (specific client name, before/after numbers, timeline)
> 3. Any design preferences beyond your brand colors? (dark background, light background, minimal, bold)"

If for a specific client: use their name/company throughout the personalized slides.
If general-purpose: use "your business" / "your team" language.

---

## Step 3 — Build brand system

Read from settings and build the color/typography system:

```
Primary Color:    #{brand_primary_color} (titles, anchors, key numbers)
Accent Color:     #{brand_accent_color} (ONE emphasis point per slide max)
Background Main:  #{first bg color} (majority of slides)
Background Alt:   #{second bg color} (section dividers, emphasis slides)
Text Dark:        #2C262E (body copy and labels)
Text Light:       #FFFFFF (on dark backgrounds)

Title Font:       {brand_title_font} — 2.5-3rem
Subtitle Font:    {brand_body_font} Bold — 1.4-1.6rem
Body Font:        {brand_body_font} — 1-1.1rem
Caption Font:     {brand_body_font} — 0.8-0.9rem
```

Design rules (non-negotiable):
- One message per slide — if it doesn't move the deal forward, delete it
- Left-align body text, center only titles
- Vary layouts across slides (never repeat the same layout consecutively)
- No accent lines under titles (hallmark of AI-generated slides)
- 40%+ whitespace on every slide
- Dark/light sandwich: alternate background colors every 3-5 slides

---

## Step 4 — Generate slide outline

Create a text outline of all 23 slides with the actual content from the Offer Doc. Present to user for review.

### Slide Structure

**Slide 1 — Cover**
Goal: Pattern interrupt + authority
```
[Bold hook statement derived from Signature Transformation]

{Business Name}
```

**Slide 2 — Personalized Intro**
Goal: Make it about THEM immediately
```
[If for specific client: "Built specifically for {Client Name} / {Company Name}"]
[If general: "Built for {target audience description}"]

{1 sentence showing you understand their situation — derived from Core Problem #1}
```

**Slide 3 — Core Problem (Emotional Hook)**
Goal: Trigger pain + relevance
```
{Core Problem #1 — framed emotionally, not logically}

"If this isn't fixed, it leads to: {consequence from Problem #1}"
```

**Slide 4 — Problem Agitation**
Goal: Increase urgency
```
And to make things worse:

1. {Problem #1 — specific operational or financial pain}
2. {Problem #2 — what's not working}
3. {Problem #3 — future risk if ignored}
```

**Slide 5 — Big Promise**
Goal: Shift from pain to hope
```
{Signature Transformation statement}

WITHOUT {biggest pain from Core Problems}
In {timeframe from Proven Path}
```

**Slide 6 — Key Outcomes**
Goal: Value clarity
```
Outcome 1: {One Outcome — primary transformation}
Outcome 2: {Unique Mechanism — the differentiator}
Outcome 3: {Dream Outcome — emotional/lifestyle benefit}
```

**Slide 7 — Visual Proof (optional)**
Goal: Make it tangible
```
{Proof points with specific metrics}
{Before/after if available}
{Screenshots or dashboards if applicable}
```
Skip if no proof points available. Note: "[Proof slide — add when results are available]"

**Slide 8 — How It Works**
Goal: Remove confusion (3 steps max)
```
Step 1: {Phase 1 name} — {what happens}
Step 2: {Phase 2 name} — {what happens}
Step 3: {Phase 3 name} — {what happens}
```

**Slide 9 — Demo / Process**
Goal: Show, don't tell
```
{Detailed walkthrough of the Proven Path}
{Timeline: Phase 1 timeline → Phase 2 timeline → Phase 3 timeline}
{Milestones at each phase}
```

**Slide 10 — Objection Handling**
Goal: Kill hesitation early
```
You might be thinking:

"{Objection 1}" → {Counter 1}
"{Objection 2}" → {Counter 2}
"{Objection 3}" → {Counter 3}
```

**Slide 11 — Customer Wins (Proof)**
Goal: Credibility with metrics
```
{Proof point 1 with specific number}
{Proof point 2 with specific number}
{Proof point 3 with specific number}
```
Use logos/names if available from testimonials.

**Slide 12 — Testimonial**
Goal: Trust transfer
```
"{Best testimonial quote — short, specific, result-driven}"

— {Name, Company}
```
If no testimonials in settings, skip this slide.

**Slide 13 — Social Proof Story**
Goal: Relatability
```
We worked with {similar client from proof points}
They had: {problem}
We helped them: {solution using Unique Mechanism}
Result: {specific measurable outcome}
```

**Slide 14 — Why You (Differentiation)**
Goal: Kill competition
```
The difference:
We use {Unique Mechanism}

Proven by: {proof points}

This solves: {core problem}
Result: {specific outcome}
```

**Slide 15 — Team**
Goal: De-risk
```
{User Name} — {role derived from bio}
{1 sentence credibility from bio}
```
For solopreneurs: one slide is fine. If they mention a team, ask for team details.

**Slide 16 — Future Vision**
Goal: Emotional close
```
Imagine in {timeframe from Proven Path Phase 3}:

- {Pain from Problem 1} — gone
- {One Outcome} — achieved
- {Dream Outcome} — your new reality
```

**Slide 17 — Core Offer**
Goal: Sell
```
{Offer Name}

Get {One Outcome}
WITHOUT {biggest pain}
In {timeframe}
```

**Slide 18 — What's Included**
Goal: Stack value
```
{Value Stack — all components with perceived values}

Total Value: ${total perceived value}
```

**Slide 19 — Pricing Tiers**
Goal: Anchor value
```
{Investment structure from Offer Doc}

Your Investment: {price}
Value You Get: ${total perceived value}
```
If multiple tiers exist, show all. If single price, show value comparison.

**Slide 20 — Bonus Stack**
Goal: Increase urgency
```
{Bonus 1} — Value: ${value}
{Bonus 2} — Value: ${value}
{Bonus 3} — Value: ${value}
```

**Slide 21 — Guarantee**
Goal: Remove risk
```
{Guarantee type and specific promise}

{Conditions if conditional guarantee}
```

**Slide 22 — Scarcity Offer**
Goal: Force decision
```
{Urgency/Scarcity from Offer Doc}

{Price or founding offer if applicable}
```

**Slide 23 — Next Steps (Close)**
Goal: Convert
```
Next Steps:
1. {CTA from Offer Doc}
2. {Follow-up action}
3. Begin your transformation in {timeframe}
```

Ask user:
> "Here's the slide outline with your actual content. Review it and tell me:
> - Any slides to skip or add?
> - Any content to change?
> - Ready to generate?"

---

## Step 5 — Generate HTML presentation

Create a single self-contained HTML file with embedded CSS and JavaScript for slide navigation. The file must work offline with no external dependencies (except Google Fonts).

### HTML structure:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>{Offer Name} — Pitch Deck</title>
  <link href="https://fonts.googleapis.com/css2?family={title_font_url}&family={body_font_url}:wght@400;700&display=swap" rel="stylesheet">
  <style>
    /* CSS custom properties from brand settings */
    :root {
      --primary: #{brand_primary_color};
      --accent: #{brand_accent_color};
      --bg-main: #{first bg color};
      --bg-alt: #{second bg color};
      --text-dark: #2C262E;
      --text-light: #FFFFFF;
      --font-title: '{brand_title_font}', sans-serif;
      --font-body: '{brand_body_font}', sans-serif;
    }

    /* Reset and base */
    * { margin: 0; padding: 0; box-sizing: border-box; }

    /* Slide container — 16:9 aspect ratio */
    .slide {
      width: 100vw;
      height: 100vh;
      display: none;
      padding: 60px 80px;
      position: relative;
      overflow: hidden;
    }
    .slide.active { display: flex; flex-direction: column; justify-content: center; }

    /* Typography */
    .slide h1 { font-family: var(--font-title); font-size: 3rem; line-height: 1.2; }
    .slide h2 { font-family: var(--font-title); font-size: 2.2rem; line-height: 1.3; }
    .slide p, .slide li { font-family: var(--font-body); font-size: 1.1rem; line-height: 1.6; }

    /* Background alternation */
    .slide-light { background: var(--bg-main); color: var(--text-dark); }
    .slide-alt { background: var(--bg-alt); color: var(--text-dark); }
    .slide-dark { background: var(--primary); color: var(--text-light); }

    /* Navigation */
    .nav { position: fixed; bottom: 20px; right: 30px; z-index: 100; font-family: var(--font-body); font-size: 0.85rem; color: #999; }
    .nav span { cursor: pointer; padding: 5px 10px; }

    /* Print mode — one slide per page */
    @media print {
      .slide { display: flex !important; page-break-after: always; height: 100vh; }
      .nav { display: none; }
    }
  </style>
</head>
<body>
  <!-- Slides here — one div.slide per slide -->

  <div class="nav">
    <span onclick="prevSlide()">←</span>
    <span id="slideNum">1 / 23</span>
    <span onclick="nextSlide()">→</span>
  </div>

  <script>
    let current = 0;
    const slides = document.querySelectorAll('.slide');
    const total = slides.length;

    function showSlide(n) {
      slides[current].classList.remove('active');
      current = (n + total) % total;
      slides[current].classList.add('active');
      document.getElementById('slideNum').textContent = (current + 1) + ' / ' + total;
    }

    function nextSlide() { showSlide(current + 1); }
    function prevSlide() { showSlide(current - 1); }

    document.addEventListener('keydown', (e) => {
      if (e.key === 'ArrowRight' || e.key === ' ') nextSlide();
      if (e.key === 'ArrowLeft') prevSlide();
    });

    slides[0].classList.add('active');
  </script>
</body>
</html>
```

### Slide design rules:

1. **Alternate backgrounds:** Use `slide-light` for most slides, `slide-dark` for emphasis slides (1, 5, 16, 17, 23), `slide-alt` for section dividers (4, 8, 10, 18, 20)
2. **One message per slide** — keep content minimal and scannable
3. **Left-align body text, center titles** — never center paragraphs
4. **Accent color sparingly** — one highlight per slide max (key numbers, CTA buttons)
5. **Generous whitespace** — padding 60px+ on all sides
6. **Vary layouts** — mix centered, left-aligned, and split layouts across slides
7. **No decorative elements** — no accent lines under titles, no gradients, no shadows

### Navigation features:

- Arrow keys (left/right) to navigate
- Spacebar advances forward
- Click arrows in bottom-right corner
- Slide counter shows position
- Print mode renders all slides (one per page)

Output: `{output_dir}/{offer-name-slug}-pitch-deck.html`

---

## Step 6 — QA and present

After generating, tell user:

> "Pitch deck generated:
> `{output_path}`
>
> {slide count} slides with your brand styling. Open it in your browser to present — use arrow keys or spacebar to navigate.
>
> Review it and let me know if any slides need adjustments.
>
> Ready to move to VSL + Landing Page?"

---

## Embedded Warnings — Read Before Every Generation

These are the patterns that kill pitch decks. Check every slide against them:

1. **Do not stay generic.** Every slide must include specific numbers, examples, or real language from the Offer Doc. If a slide could apply to any business, it's too generic — rewrite it.

2. **Do not over-design, under-sell.** Every slide = one message. If it doesn't move the deal forward, delete it. Clarity beats aesthetics every time.

3. **Weak differentiation kills deals.** Slide 14 (Why You) must have: mechanism (what you do differently), proof (that it works), and constraint (why others can't copy it). If any are missing, flag to user.

4. **No proof = no deal.** Slides 7, 11, 12, 13 are your proof cluster. If the user has limited proof, consolidate into fewer slides but make what exists specific and measurable. Never use vague proof ("great results", "happy clients").

---

## Edge Cases

1. **No testimonials:** Skip slide 12, strengthen slides 11 and 13 with available proof points.
2. **No case studies:** Skip slide 13, add an extra outcomes slide or expand the method breakdown.
3. **Solopreneur (no team):** Slide 15 becomes a deeper "About Me" with credentials and relevant experience.
4. **Multiple pricing tiers:** Expand slide 19 to show comparison table. Consider splitting into 2 slides if 3+ tiers.
5. **User wants fewer slides:** Allow skipping optional slides (7, 12, 13, 15, 20). Minimum viable deck: slides 1, 3-5, 8, 10, 17-19, 21, 23 (12 slides).
6. **Google Fonts unavailable (offline):** The deck still works — CSS falls back to system sans-serif fonts.
