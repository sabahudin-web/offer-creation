---
name: offer-landing-page
description: Creates a VSL script and landing page copy (with optional full HTML) from an Offer Doc. Two deliverables in one skill. The VSL uses a meta-framework (Belief Shifting + PAIS + Case Study + BFF) with diagnostic-driven emphasis. The landing page follows an 11-section high-converting sales page structure. Reads brand settings for HTML styling.
tools:
  - Read
  - Write
  - Bash
  - AskUserQuestion
---

# Offer Landing Page + VSL Script

You are creating two deliverables from the user's Offer Doc:
1. A VSL (Video Sales Letter) script
2. A landing page (copy only or full HTML)

The VSL goes first because the landing page references it in the Hero section.

---

## Step 1 — Read inputs

1. Read the Offer Doc from `{output_dir}/offer-doc.md`.
2. Read settings from `.claude/offer-creation.local.md`.
3. Optionally read the pitch deck HTML for additional context: `{output_dir}/*-pitch-deck.html` (if it exists). This gives you the slide text which may have refined messaging.

Extract from Offer Doc:
- Offer Name, Signature Transformation, One Outcome, Dream Outcome
- Core Problems (all 3), Unique Mechanism
- Proven Path (3 phases), Objections + Counters
- Value Stack, Bonus Stack, Guarantee
- Investment, Urgency/Scarcity, Next Steps
- Ideal Client, Not For You

From settings:
- Bio, Proof Points, Testimonials
- Brand colors, fonts (for HTML version)
- Voice words, examples, banned words
- Landing page format preference

---

# PART 1: VSL SCRIPT

## Step 2 — VSL diagnostic

Before writing, diagnose the offer to determine framework emphasis. Ask:

> "A few quick questions to calibrate the VSL:
>
> 1. What is your audience's awareness level?
>    A) Unaware of the problem
>    B) Problem-aware but not solution-aware
>    C) Solution-aware but haven't found the right one
>    D) Know about you specifically
>
> 2. How urgent is their problem?
>    A) Nice to solve someday
>    B) Actively looking for a solution
>    C) Hair on fire — needs fixing now
>
> 3. What proof do you have available?
>    A) Hard metrics (revenue, time saved, conversion rates)
>    B) Testimonials (quotes from clients)
>    C) Case studies (before/after stories)
>    D) Limited proof (early stage)
>
> 4. How much trust is required before they buy?
>    A) Low — impulse / low price point
>    B) Medium — need social proof
>    C) High — need relationship / call first"

Map answers to framework emphasis:

| Situation | Dominant Framework | Section Emphasis |
|-----------|-------------------|-----------------|
| Unaware audience | Belief Shifting | Heavy Hook + Problem sections |
| Problem-aware | PAIS | Heavy Agitation + Solution |
| Solution-aware | Case Study + Differentiation | Heavy Belief Shift + Proof |
| Know about you | BFF (relationship) | Lighter setup, straight to offer |
| Hair on fire + hard metrics | Direct response | Shorter VSL, proof-heavy |
| High trust required | BFF + Journey | Longer VSL, more stories |
| Limited proof | Belief Shifting + Future Pacing | Lead with mechanism, paint the future |

---

## Step 3 — VSL length

Ask:
> "How long should the VSL be?
>
> A) Short (2-3 minutes / ~400-600 words) — punchy, for warm audiences or low-ticket
> B) Medium (5-8 minutes / ~800-1200 words) — standard, story-driven with objection handling
> C) Long (10-15 minutes / ~1500-2200 words) — comprehensive, for cold traffic or high-ticket"

---

## Step 4 — Write VSL script

Use the 12-section meta-framework. Content comes from the Offer Doc. Emphasis comes from the diagnostic.

### Section 1: Hook (0-10 seconds)

**Frameworks:** Belief Shifting + Contrarian Hook

Template:
> "Most people think [common belief derived from Core Problem #1].
> But actually, [contrarian truth from Unique Mechanism].
> And that's why [specific failure your audience experiences — from Core Problems]."

Rules:
- Pattern interrupt — first 3 seconds decide if they stay
- Must feel like "this is about ME"
- Never start with "Hey" or "In this video"

### Section 2: Problem Identification (10-30 seconds)

**Frameworks:** PAIS (Pain) + BFF (relatable tone)

Template:
> "If you're [target audience from Ideal Client], you've probably experienced:
> - [Pain from Core Problem #1]
> - [Pain from Core Problem #2]
> - [Pain from Core Problem #3]"

Rules:
- Use their language, not yours
- The more specific the pain, the higher the conversion
- 3 pains maximum

### Section 3: Agitation (30-60 seconds)

**Frameworks:** PAIS (Agitate) + Emotional tension

Template:
> "And the worst part is...
> [Consequence of Problem #1 — operational or financial cost]
> Which leads to [deeper emotional cost — frustration, self-doubt, burnout]
> And if nothing changes, [future risk from Problem #3]"

Rules:
- Make the problem feel expensive (time, money, opportunity)
- No urgency = no action
- Don't overdo it — one strong agitation beats three weak ones

### Section 4: Belief Shift (60-120 seconds) — MOST IMPORTANT

**Frameworks:** Belief Shifting (core) + Authority positioning

Template:
> "The real problem isn't [what they think — the surface problem].
> It's actually [Unique Mechanism — the deeper truth].
>
> [1-2 sentences explaining WHY this is the real problem]
>
> Once you understand this, everything changes."

Rules:
- THIS IS THE MOST IMPORTANT SECTION OF THE VSL
- If this fails, the whole VSL fails
- Must reframe their understanding of the problem
- Must position you as the expert who sees what others don't

### Section 5: Solution Intro (transition)

**Frameworks:** Future Pacing + Solution transition

Template:
> "Once you understand this, you can [new possibility — One Outcome].
> Instead of [current struggle], you [desired state from Dream Outcome]."

Rules:
- Brief — this is a bridge, not a destination
- Move from problem to hope
- Curiosity should peak here

### Section 6: Case Study / Proof Block

**Frameworks:** Case Study + Cialdini (Social Proof + Authority)

Template:
> "[Name/client] was [starting point — relatable situation].
> They [tried what didn't work — relates to audience's experience].
> We applied [Unique Mechanism / method from Proven Path].
> Result: [specific measurable outcome from Proof Points]."

Rules:
- Specificity = credibility
- Bad: "They got great results"
- Good: "From 0 to 12 qualified calls in 10 days"
- If no case study available: use your own story or a hypothetical clearly labeled as "Here's what this looks like in practice"

### Section 7: Method Breakdown (optional — include for medium/long VSLs)

**Frameworks:** Teacher + Reciprocity

Template:
> "Here's how this works in simple terms:
> Step 1: [Phase 1 name] — [what happens, simplified]
> Step 2: [Phase 2 name] — [what happens, simplified]
> Step 3: [Phase 3 name] — [what happens, simplified]"

Rules:
- Don't overteach — just enough to feel real
- 3 steps maximum
- Skip for short VSLs

### Section 8: Ideal Future (desire)

**Frameworks:** PAIS (Ideal Situation) + Future Pacing

Template:
> "Imagine if instead of [current pain]:
> - [Dream Outcome benefit 1]
> - [Dream Outcome benefit 2]
> - [Dream Outcome benefit 3]
>
> That's what [timeframe from Proven Path] from now could look like."

Rules:
- Make it visual and specific
- Use present tense ("you wake up to..." not "you would wake up to...")
- Connect to their emotional desires, not just business metrics

### Section 9: Offer Intro (the vehicle)

**Frameworks:** Solution (PAIS) + Authority positioning

Template:
> "That's exactly why I created [Offer Name].
> It's designed to help you [One Outcome] without [biggest pain from Problems].
>
> Here's what's included:
> [Value Stack — top 3-4 components only, save full list for landing page]"

Rules:
- The offer is NOT the hero — the transformation is
- Keep the value stack brief in the VSL — the landing page has the full breakdown
- Lead with the core result, then stack components

### Section 10: Objection Handling

**Frameworks:** BFF + Cialdini (Consistency + Trust)

Template:
> "Now, you might be thinking: '[Objection 1]'
> And I get it. [Counter 1 — honest, not dismissive]
>
> Or maybe: '[Objection 2]'
> [Counter 2]
>
> [Optional for long VSLs: Objection 3]"

Rules:
- Pre-handle objections = higher conversion
- Be honest, not defensive
- 2 objections for short/medium, 3 for long

### Section 11: Urgency / Scarcity

**Frameworks:** Cialdini (Scarcity)

Template:
> "[Urgency element from Offer Doc]
> [Scarcity element — limited spots, deadline, founding price]
>
> If you're serious about [One Outcome]..."

Rules:
- Only use if genuine scarcity exists in the Offer Doc
- If no scarcity: skip this section entirely — fake urgency kills trust
- Never make up scarcity that doesn't exist

### Section 12: CTA (Call to Action)

**Frameworks:** Direct response

Template:
> "[CTA from Offer Doc — book a call, click the link, DM me]
> It takes less than [time estimate] and could be the start of [transformation].
>
> [Repeat Signature Transformation as closing line]"

Rules:
- One clear action — no "you can also..."
- Remove friction — tell them exactly what happens next
- End on the transformation, not the logistics

---

### VSL Output Format

Write the script with production cues:

```markdown
# VSL Script — [Offer Name]

**Length:** [short/medium/long] (~[word count] words, ~[minutes] minutes)
**Framework emphasis:** [dominant framework from diagnostic]
**Created:** [date]

---

## [HOOK] — 0:00-0:10
[Script text]

[VISUAL: suggested on-screen text or b-roll]

---

## [PROBLEM] — 0:10-0:30
[Script text]

[VISUAL: ...]

---

[...continue for all sections...]
```

Save to `{output_dir}/vsl-script.md`.

Ask user to review before proceeding to landing page:
> "VSL script draft complete ([word count] words, ~[minutes] minutes). Review it — any sections to adjust before I create the landing page?"

---

# PART 2: LANDING PAGE

## Step 5 — Write landing page copy

The landing page follows an 11-section structure. Content pulls from the Offer Doc, with the VSL script providing refined messaging for the Hero section.

### Section 1: Hero

```
[Headline — derived from Signature Transformation, punchy and benefit-driven]
[Sub-headline — One Outcome + "without" + biggest pain]

[VSL embed placeholder: "Watch the [X]-minute video to see how [Offer Name] works"]
OR
[Product mockup placeholder if no VSL]

[Primary CTA button: "{CTA from Offer Doc}"]
```

Rules:
- Headline must pass the "billboard test" — understandable in 3 seconds
- Sub-headline adds specificity
- CTA above the fold

### Section 2: Quiz (Archetypes)

Reframe the Ideal Client bullets as 2-3 specific archetypes:

```
This is for you if you're...

**The [Archetype 1 Name]**
[You're {situation}. You've tried {what didn't work}. You need {what they actually need}.]

**The [Archetype 2 Name]**
[You're {situation}. You're frustrated by {pain}. You want {outcome}.]

**The [Archetype 3 Name]** (optional)
[You're {situation}. You know {something}. You just need {the missing piece}.]
```

Derive archetypes from: Ideal Client bullets + Core Problems + ICP description from settings.

### Section 3: Your Instructor

```
Meet [User Name]

[Bio from settings — 2-3 sentences]

[1-2 additional sentences connecting bio to THIS offer specifically]
```

### Section 4: Proof

```
[Proof Points from settings — formatted as bold, scannable bullets]

Example format:
- **[Metric]** — [context]
- **[Result]** — [who achieved it]
- **[Achievement]** — [why it matters]
```

If limited proof: use "What I've built" framing — describe systems, clients served, or experience without fabricating metrics.

### Section 5: Problems (7-10 pain points)

Expand the 3 Core Problems into 7-10 specific, relatable pain points:

```
Sound familiar?

- [Pain point 1 — from Problem 1]
- [Pain point 2 — from Problem 1]
- [Pain point 3 — from Problem 1]
- [Pain point 4 — from Problem 2]
- [Pain point 5 — from Problem 2]
- [Pain point 6 — from Problem 2]
- [Pain point 7 — from Problem 3]
- [Pain point 8 — from Problem 3]
(optional: 9-10)
```

Rules:
- Each must be specific enough that the reader nods
- Use "you" language
- Mix emotional and practical pains

### Section 6: Mistakes (3 biggest)

Derive from the Objections + Counters section. Reframe objections as mistakes:

```
The 3 biggest mistakes [target audience] make:

**Mistake #1: [Mistake derived from Objection 1]**
[Why it's a mistake — 2-3 sentences]
[How {Offer Name} avoids this — 1-2 sentences]

**Mistake #2: [From Objection 2]**
[Why + how we avoid]

**Mistake #3: [From Objection 3]**
[Why + how we avoid]
```

### Section 7: Everything Included

```
Here's everything you get inside [Offer Name]:

[Value Stack — full breakdown with descriptions and perceived values]

| What You Get | Value |
|-------------|-------|
| {Core component} | ${value} |
| {Component 2} | ${value} |
| {Component 3} | ${value} |
| ... | ... |
| **Total Value** | **${total}** |
| **Your Investment** | **{price}** |
```

### Section 8: Bonuses

```
[Bonus Stack — each with name, description, and perceived value]

**BONUS #1: [Name]** (Value: ${value})
[Description — what it is and why it matters]

**BONUS #2: [Name]** (Value: ${value})
[Description]

**BONUS #3: [Name]** (Value: ${value})
[Description]
```

### Section 9: Last Nudge

```
[Urgency/Scarcity from Offer Doc]

[Restate the transformation one more time]
[Restate the value-to-price ratio]

[CTA button]
```

If no deadline or scarcity: skip the urgency. Use a "decision" framing instead:
> "You have two options: keep doing what you've been doing, or [take the next step]."

### Section 10: FAQ

Rewrite Objections as questions with answers:

```
**Q: [Objection 1 reframed as a question]**
A: [Counter — honest, direct]

**Q: [Objection 2 as question]**
A: [Counter]

**Q: [Objection 3 as question]**
A: [Counter]

**Q: How long until I see results?**
A: [From Time to Results — quick win timeline]

**Q: How much time does this require from me?**
A: [From Effort Required]

**Q: What if it doesn't work for me?**
A: [From Guarantee]
```

Add 3-4 additional common questions based on the offer type.

### Section 11: Guarantee

```
[Guarantee type and promise]

[Specific conditions if conditional]

[CTA — final button]
```

---

## Step 6 — Format and save

Check `landing_page_format` from settings:

### If "copy" (markdown only):

Save the full copy as structured markdown to `{output_dir}/landing-page.md`.

### If "html":

Generate a complete, responsive HTML file with:
- Google Fonts import for `{brand_title_font}` and `{brand_body_font}`
- CSS custom properties using brand colors from settings
- Mobile-first responsive design (max-width: 800px content area)
- Sections with alternating background colors
- CTA buttons styled with accent color
- Clean typography with proper hierarchy
- 40%+ whitespace

Read and follow `.claude/skills/frontend-design/SKILL.md` for design aesthetics if the skill is installed. If not, apply these defaults:
- Bold, distinctive design — not generic template look
- One focal point per section
- Strong contrast between sections
- Generous padding (60px+ between sections)

Save to `{output_dir}/landing-page.html`.

### If "both":

Generate both formats.

---

## Step 7 — Present results

> "Landing page and VSL script complete:
>
> VSL Script: `{output_dir}/vsl-script.md` ([word count] words, ~[minutes] min)
> Landing Page: `{output_dir}/landing-page.[ext]` ([section count] sections)
>
> Review both — any adjustments before we move to DM openers?"

---

## Edge Cases

1. **No proof points:** Mark proof sections with "[Add proof when available]" with placeholder structure that shows where metrics would go.
2. **No testimonials:** Skip testimonial subsections in both VSL and landing page. Strengthen case study / "what I've built" sections.
3. **User wants both copy and HTML:** Generate both. HTML references the same copy.
4. **VSL diagnostic shows "limited proof + unaware audience":** Lean heavily on Belief Shifting and Future Pacing. Shorter proof section, longer mechanism explanation.
5. **Short VSL selected:** Skip sections 7 (Method Breakdown) and reduce sections 10-11 to 1-2 sentences each. Keep sections 1-6, 8-9, 12.
6. **frontend-design skill not installed for HTML:** Use embedded defaults (brand colors, clean typography, responsive layout). Note to user that installing frontend-design skill would improve the output.
