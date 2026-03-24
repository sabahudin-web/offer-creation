---
name: offer-onboarding
description: Interactive offer creation framework combining Saba's Complete Offer Framework with Hormozi's Grand Slam Offer (Value Equation). Walks the user through building a comprehensive Offer Doc step by step. Use when creating a new offer or refining an existing one.
tools:
  - Read
  - Write
  - AskUserQuestion
---

# Offer Onboarding

You are building an Offer Doc with the user. This is the foundation for everything downstream — pitch deck, VSL, landing page, DM openers. Every answer matters. Do not rush.

Walk through each step **one at a time**. Ask one question, wait for the answer, then move on. Never dump multiple questions.

---

## Step 0 — Read settings and check for existing Offer Doc

1. Read `.claude/offer-creation.local.md` for user profile, brand, and ICP context.
2. **If settings file is missing:** Do NOT tell the user to run a separate command. Instead, say:
   > "No brand settings found yet. Let me set those up first — it takes about 5 minutes, then we'll jump straight into building your Offer Doc."
   Then read and follow the Brand Setup steps (Steps 1-8) from `commands/onboard.md` inline. Once settings are saved, continue to sub-step 3 below.
3. Read `{output_dir}/offer-doc.md` (output_dir from settings, default: `05_Attachments/output/offer-creation/`).
4. If Offer Doc exists, show a 5-line summary and ask:
   > "You already have an Offer Doc. Do you want to (A) refine specific sections, (B) start fresh, or (C) view the full doc?"
5. If refining: ask which section, update only that section, rewrite the file. Done.
6. If no file exists or starting fresh: proceed to Step 1.

---

## Step 1 — Offer awareness diagnostic

Ask:
> "Before we build your offer, where are you starting from?
>
> A) I have an existing offer I want to sharpen
> B) I know what I do but haven't packaged it as an offer yet
> C) I'm not sure what my offer should be"

- If A: ask them to describe their current offer in 2-3 sentences. Use as foundation for the remaining steps — pre-fill what you can and confirm.
- If B: proceed to Step 3 (skip Superpowers, they know their skill).
- If C: proceed to Step 2 (Superpowers Exercise).

---

## Step 2 — Superpowers Exercise

Only run this if user selected C in Step 1. Ask each question one at a time:

**2a:**
> "What do people always come to you for help with? Think about what friends, colleagues, or clients ask you about repeatedly."

**2b:**
> "What do you do better than most people in your field?"

**2c:**
> "What result do clients or people get when they work with you or follow your advice?"

**2d:**
> "What do you wish people knew you for?"

After all 4 answers, synthesize into a working hypothesis:
> "Based on what you've shared, here's my read on your core offering: [synthesis]. Does this feel right, or should we adjust?"

Iterate until they confirm, then proceed.

---

## Step 3 — Dream Outcome (Hormozi Value Equation)

Ask:
> "What does your customer REALLY want? Not the deliverable — the end state. What transformation are they dreaming about?
>
> Bad example: 'A social media strategy'
> Good example: 'A consistent flow of qualified leads without spending hours on LinkedIn every day'"

Follow up:
> "How would your ideal client describe this outcome in their own words — the way they'd say it to a friend?"

---

## Step 4 — Signature Transformation

Ask:
> "Let's create your Signature Transformation statement. Fill in the blanks:
>
> I help [WHO] go from [CURRENT STATE] to [DESIRED OUTCOME] in [TIMEFRAME]"

Present the draft back. Iterate until it's specific and compelling.

Rules:
- WHO must be specific (not "businesses" — which businesses?)
- CURRENT STATE must be a real pain they feel
- DESIRED OUTCOME must be measurable or vivid
- TIMEFRAME must be realistic and specific

---

## Step 5 — One Outcome Statement

Ask:
> "What is the ONE measurable outcome your client gets? If they could only point to one thing and say 'this is what I got' — what is it?
>
> Example: '12 qualified sales calls per month' or 'a fully automated client acquisition system'"

Push for specificity. If the answer is vague ("better results", "more clients"), ask:
> "Can you put a number or a concrete milestone on that?"

---

## Step 6 — Core Problems (3)

Ask each one separately:

**6a — Immediate Pain:**
> "Problem 1: What urgent, right-now problem does your ideal client feel? The thing that makes them Google solutions at 11 PM?
>
> Include: what they struggle with, what it costs them, and how it affects their business or life."

**6b — Growth Blocker:**
> "Problem 2: What's preventing them from reaching the next level? The thing they've tried to fix but can't seem to crack?
>
> Include: what they've tried, why it didn't work, and what it's costing them to stay stuck."

**6c — Scaling Limit:**
> "Problem 3: What breaks when they try to grow? The ceiling they keep hitting?
>
> Include: what opportunity they're missing, what's limiting them, and what happens if they don't fix it."

---

## Step 7 — Likelihood of Success (Hormozi Value Equation)

Ask:
> "Why will YOUR approach work for them? What's your unique mechanism — the specific method, system, or process that makes your solution different from everything else they've tried?
>
> This is the 'secret sauce'. Not just what you do, but WHY it works when other things haven't."

If the answer is generic ("I provide personalized service"), push:
> "What specifically do you do differently that produces the result? Can you name the method or system?"

---

## Step 8 — Time Delay (Hormozi Value Equation)

Ask:
> "How fast do they see results? Be specific:
>
> - What's the first quick win they experience? (days/weeks)
> - When do they hit the main milestone? (weeks/months)
> - When is the full transformation complete?"

---

## Step 9 — Effort and Sacrifice (Hormozi Value Equation)

Ask:
> "How easy is this for them? Be honest:
>
> - What do YOU handle vs. what do THEY have to do?
> - How much of their time does it require per week?
> - What do they have to give up or change?"

---

## Step 10 — Proven Path (3 Phases)

Ask for each phase one at a time:

**10a:**
> "Phase 1 — Quick Win: What happens first? What's the name of this phase, what do you do, and what milestone do they hit?
>
> Example: 'Phase 1: Foundation (Week 1-2) — We audit their current system, build the strategy, and they get their first optimized profile.'"

**10b:**
> "Phase 2 — Growth: What happens in the middle? Name, actions, and milestone."

**10c:**
> "Phase 3 — Scale: What's the final phase? Name, actions, and the ultimate result."

---

## Step 11 — Top 3 Objections (Hormozi)

Ask:
> "What are the top 3 reasons someone would NOT buy this? Be honest — what stops people?
>
> Common patterns: 'I can't afford it', 'I've tried something similar', 'I don't have time', 'I'm not sure it'll work for me'"

For each objection, ask:
> "How do you counter that? What's the honest answer?"

---

## Step 12 — Value Stack (Hormozi)

Ask:
> "Let's build your value stack. Start with the core — what's the main thing they get?
>
> Then we'll add 3-5 components that either speed things up, reduce effort, or increase their certainty of success."

For each component, ask:
- Name
- What it does for them (1 sentence)
- Perceived value in $ (what would someone pay for this alone?)

Build the stack:
```
Core Offer: [name] — $[perceived value]
Component 1: [name] — $[perceived value]
Component 2: [name] — $[perceived value]
Component 3: [name] — $[perceived value]
(optional) Component 4-5
```

Show the total perceived value vs. actual price.

---

## Step 13 — Bonus Stack

Ask:
> "What bonuses can you add? These should be things that cost you little but have high perceived value for the buyer.
>
> Examples: templates, checklists, a bonus call, access to a community, a recorded workshop"

For each bonus: name, description, perceived value.

---

## Step 14 — Guarantee / Risk Reversal

Ask:
> "What guarantee can you offer? Options:
>
> A) Money-back guarantee (X days, no questions asked)
> B) Performance guarantee (specific result or money back)
> C) Conditional guarantee (if they do X and don't get Y, refund)
> D) No formal guarantee (explain why)
>
> Which fits your offer, and what's the specific promise?"

---

## Step 15 — Ideal Client / Not For You

**15a:**
> "Describe your ideal client in 3 bullets — the person who gets the BEST results from this offer."

**15b:**
> "Who is this NOT for? 3 bullets — who should NOT buy this?"

---

## Step 16 — Investment and Pricing

Ask:
> "What's the price? And how is it structured?
>
> Examples: one-time payment, monthly subscription, setup fee + monthly, tiered pricing"

Then show:
> "Your total perceived value stack is $[total]. Your price is $[price]. That's a [X]x value-to-price ratio."

If ratio is less than 3x, flag it:
> "Hormozi recommends at least a 3x value-to-price ratio. Consider adding more to the stack or adjusting the price."

---

## Step 17 — Offer Name (Hormozi)

Generate 3 name options based on everything collected:
> "Your offer name should communicate the RESULT, not the process. Here are 3 options:
>
> 1. [Name option 1]
> 2. [Name option 2]
> 3. [Name option 3]
>
> Which do you prefer, or create your own?"

Rules for naming:
- Outcome-driven, not feature-driven
- Creates curiosity or clarity
- Not generic ("coaching program", "consulting package")

---

## Step 18 — Urgency / Scarcity

Ask:
> "What creates urgency for this offer? Pick what applies:
>
> A) Limited spots (how many?)
> B) Deadline / launch window
> C) Founding price that increases later
> D) Bonuses that expire
> E) Natural scarcity (your time is limited)
> F) No artificial scarcity — the offer stands on its own"

---

## Step 19 — Next Steps / CTA

Ask:
> "What's the next step for someone who wants in?
>
> A) Book a call
> B) Fill out an application
> C) DM me on LinkedIn
> D) Click a link / buy now
> E) Something else"

---

## Step 20 — Compile and Write the Offer Doc

Assemble all answers into a structured markdown document. Use this exact format:

```markdown
# Offer Doc — [Offer Name]

**Created:** [date]
**Business:** [business_name from settings]

---

## Signature Transformation

[Statement from Step 4]

## One Outcome

[Statement from Step 5]

## Dream Outcome

[From Step 3 — what they REALLY want]

## Core Problems

### Problem 1: Immediate Pain
[From Step 6a — struggle, consequence, impact]

### Problem 2: Growth Blocker
[From Step 6b — challenge, what's not working, cost of inaction]

### Problem 3: Scaling Limit
[From Step 6c — missed opportunity, limitation, future impact]

## Unique Mechanism

[From Step 7 — why YOUR approach works]

## Time to Results

- Quick Win: [from Step 8]
- Main Milestone: [from Step 8]
- Full Transformation: [from Step 8]

## Effort Required

[From Step 9 — what you handle, what they do, time commitment]

## Proven Path

### Phase 1: [Name] ([Timeline])
[Actions and milestone from Step 10a]

### Phase 2: [Name] ([Timeline])
[Actions and milestone from Step 10b]

### Phase 3: [Name] ([Timeline])
[Actions and milestone from Step 10c]

## Objections and Counters

### Objection 1: [objection]
**Counter:** [counter from Step 11]

### Objection 2: [objection]
**Counter:** [counter]

### Objection 3: [objection]
**Counter:** [counter]

## Value Stack

| Component | Description | Perceived Value |
|-----------|-------------|-----------------|
| **Core: [name]** | [description] | $[value] |
| [Component 1] | [description] | $[value] |
| [Component 2] | [description] | $[value] |
| [Component 3] | [description] | $[value] |
| **Total Perceived Value** | | **$[total]** |

## Bonus Stack

| Bonus | Description | Perceived Value |
|-------|-------------|-----------------|
| [Bonus 1] | [description] | $[value] |
| [Bonus 2] | [description] | $[value] |
| [Bonus 3] | [description] | $[value] |

## Guarantee

[From Step 14 — type and specific promise]

## Ideal Client

- [Bullet 1]
- [Bullet 2]
- [Bullet 3]

## Not For You

- [Bullet 1]
- [Bullet 2]
- [Bullet 3]

## Investment

**Price:** [price and structure from Step 16]
**Value-to-Price Ratio:** [X]x

## Offer Name

[Final name from Step 17]

## Urgency / Scarcity

[From Step 18]

## Next Steps

[CTA from Step 19]
```

Write to `{output_dir}/offer-doc.md`.

Show the user a summary:
> "Your Offer Doc is complete. Here's the overview:
>
> **[Offer Name]**
> Transformation: [signature transformation]
> Price: [price] | Perceived Value: $[total] | Ratio: [X]x
> Guarantee: [guarantee type]
> CTA: [next step]
>
> Saved to: [path]
>
> Ready to move to the Pitch Deck?"

---

## Edge Cases

1. **User can't articulate their superpowers:** Use their bio from settings as a starting point. Suggest based on their ICP and industry.
2. **User doesn't have proof points yet:** Mark proof-dependent sections with "[TBD -- add proof when available]". The downstream skills will handle missing proof gracefully.
3. **User wants to skip a section:** Allow it. Mark as "[Skipped -- revisit later]". Note which sections were skipped at the end.
4. **User has an existing offer to sharpen:** Pre-fill the template with their description, then walk through each section asking "Is this accurate, or should we adjust?"
5. **User gives vague answers:** Push for specificity once. If still vague, accept it and note: "Consider making this more specific before generating downstream materials."
6. **Value-to-price ratio is below 3x:** Flag it but don't block progress. It's a recommendation, not a requirement.
