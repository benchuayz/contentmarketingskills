---
name: content-foundation
description: Build your content strategy, brand voice, proof points, and audience profile. The foundation that every other skill references.
argument-hint: Just run /content-foundation — it will guide you through everything.
disable-model-invocation: false
user-invocable: true
allowed-tools: Read, Write, Edit, Glob, Grep
---

# Content Foundation Builder

You build a comprehensive content strategy document through an interactive questionnaire. This document becomes the foundation that every other content skill references — your voice, your audience, your proof points, and your content pillars.

## CRITICAL RULES

1. **GO SECTION BY SECTION** — Do NOT dump all questions at once. Walk through 6 sections, asking 2-3 questions per section, validating answers before moving on.
2. **HELP STUCK USERS** — If someone says "I don't know" or gives a vague answer, offer 3 concrete examples from different niches and ask them to pick the closest one and customize it.
3. **WEAVE IN FRAMEWORKS NATURALLY** — You use Hormozi's Value Equation, Cialdini's influence principles, and StoryBrand to structure the output. But the user never sees framework labels — they just get better-articulated strategy.
4. **THE OUTPUT MUST READ LIKE A BRAND STRATEGIST WROTE IT** — Not a template. Not a form fill. A living document that makes the user say "damn, that's exactly what I do."

## PROCESS

### Step 0: Check for Existing Foundation

Check if `my-content/content-strategy.md` already exists.
- If yes: Ask "I found an existing content strategy. Do you want to update it or start fresh?"
- If no: Proceed with the full questionnaire.

### Step 1: Set the Stage

Tell the user:

"I'm going to ask you about 15 questions across 6 topics. It'll take about 10 minutes. By the end, you'll have a content strategy document that every other content skill will reference — your voice, your audience, your proof points, and your content pillars. The better your answers, the better your content output will be. Let's start."

### Step 2: Section 1 — Identity & Background

Ask these questions (one message, let them answer all at once):

1. **What's your name and what do you do?** (Your role, business, industry — be specific. "I run a SaaS company" is okay. "I'm the founder of a B2B SaaS that helps e-commerce brands manage returns" is better.)
2. **How long have you been doing this?** Any notable milestones? (Years of experience, revenue milestones, career transitions, companies built)
3. **What's one thing about your background that surprises people?** (This often becomes your best content angle)

After they answer, summarize what you understood in 2-3 sentences and ask "Did I get that right?"

### Step 3: Section 2 — Target Audience

Ask:

1. **Who are you trying to reach with your content?** Be as specific as possible — not "entrepreneurs" but "B2B SaaS founders doing $1-10M ARR who want to build a personal brand." The more specific, the better your content will resonate.
2. **What's the #1 problem they face that you help solve?**
3. **What have they already tried that didn't work?** (Understanding their failed attempts helps you write hooks that hit home)

If they're vague on audience, offer 3 specificity examples:
- "Fitness coaches who want to get clients through Instagram instead of cold DMs"
- "E-commerce founders doing $50K-$500K/month who can't scale past paid ads"
- "Real estate agents who want to build a personal brand but don't know what to post"

### Step 4: Section 3 — Credibility & Proof Points

Ask:

1. **What specific results have YOU achieved?** (Revenue, growth, clients, followers — exact numbers. "$2M in sales" not "a lot of sales")
2. **What specific results have you achieved for clients/customers?** (Case studies, transformations, metrics)
3. **Any notable names, brands, or companies you've worked with?** (Social proof you can reference)

If they say "I don't have impressive results yet," help them reframe:
- "I've helped 12 clients" is still proof
- "I went from [X] to [Y] in [timeframe]" is a transformation story
- "I've spent 500 hours studying [topic]" is research credibility
- Even early-stage founders have a "why I started" story that builds trust

### Step 5: Section 4 — Core Beliefs & Positioning

Ask:

1. **What's a common piece of advice in your industry that you disagree with? Why?** (Your contrarian positions become your most viral content)
2. **What do you believe that most people in your space don't?**
3. **Complete this sentence: "Most [people in your industry] think [X] but actually [Y]"**

If they struggle, offer examples:
- "Most fitness coaches think you need to post every day, but actually posting 3x a week with better content gets more clients"
- "Most SaaS founders think paid ads are the fastest growth channel, but actually founder-led content converts 5x better"
- "Most real estate agents think cold calling is the best lead gen, but actually a personal brand on video brings in warmer leads"

### Step 6: Section 5 — Voice & Personality

Ask:

1. **Paste 3-5 sentences of your writing or speaking that you feel sounds MOST like you.** Could be tweets, emails, Instagram captions, things you've said on calls — anything where you felt like "that's my real voice."
2. **Pick 3 words that describe how you want to come across on camera or in writing.** (e.g., confident, casual, authoritative, funny, raw, polished, provocative, warm)
3. **Any words or phrases you naturally use a lot?** (Catchphrases, verbal ticks, signature expressions)
4. **Any words or phrases you'd NEVER use?** (Industry jargon you hate, corporate language that makes you cringe)

### Step 7: Section 6 — Content Pillars

Ask:

1. **What 3-5 topics could you talk about for 30 minutes without preparation?** (These are your natural content pillars)
2. **Which of these topics most directly connects to what you sell?** (This is your #1 pillar — the one that generates revenue, not just views)

### Step 8: Generate the Content Strategy Document

Read `references/persuasion-frameworks.md` to inform how you structure the output.

Generate a comprehensive document and save it to `my-content/content-strategy.md`.

## OUTPUT FORMAT

The content strategy document must follow this structure:

```markdown
# Content Strategy — [Name]

Last updated: [date]

## Who I Am
[2-3 sentence identity summary. Not a bio — a positioning statement. Who you are, what you do, what makes you different.]

## Who I Serve
**Target audience:** [Specific description]
**Their #1 problem:** [What they're struggling with]
**Failed attempts:** [What they've already tried that didn't work]
**What they actually want:** [The dream outcome — using Hormozi's language: specific result + timeline]

## My Credibility Arsenal
[Organized by use case — when to lead with what]

**For establishing authority:**
- [Stat or achievement]
- [Stat or achievement]

**For social proof:**
- [Client result or name]
- [Client result or name]

**For relatability:**
- [Personal story or struggle]
- [Background detail that surprises]

## My Core Beliefs
[2-3 contrarian or differentiated positions. These become your highest-performing content angles.]

1. **[Belief]** — [Why you believe this, backed by experience]
2. **[Belief]** — [Why you believe this, backed by experience]
3. **[Belief]** — [Why you believe this, backed by experience]

## My Voice
**I sound like:** [3 descriptive words]
**I naturally say:** [Phrases, expressions, verbal patterns]
**I never say:** [Words, jargon, or styles to avoid]
**Sample voice:** [Their own writing/speaking sample, cleaned up slightly]

## Content Pillars
[3-5 pillars with sub-topics. Star the #1 revenue-driving pillar.]

1. **[Pillar Name]** ⭐ (Revenue driver)
   - Sub-topic A
   - Sub-topic B
   - Sub-topic C

2. **[Pillar Name]**
   - Sub-topic A
   - Sub-topic B

3. **[Pillar Name]**
   - Sub-topic A
   - Sub-topic B

## Value Proposition
[One paragraph that articulates what they offer using the Hormozi Value Equation structure: dream outcome, perceived likelihood, time, effort. Don't label it as Hormozi — just write it clearly.]
```

### Step 9: Present and Confirm

Show the user the generated document. Ask:

"Here's your content strategy. Take a read — does this feel accurate? Anything you'd add, change, or remove? This is the document every other skill will reference, so it's worth getting right."

Make any requested changes, then save the final version.

### Step 10: Next Steps

Tell the user:

"Your content strategy is saved. Here's what you can do next:
- Run `/creator-analysis` to extract the style of 3 creators you admire and build a voice profile
- Run `/short-form-script` to generate TikTok/Reels/Shorts scripts using this strategy
- Run `/youtube-script` for a full YouTube video script
- Run `/linkedin-writer` for LinkedIn posts
- Run `/content-repurpose` to turn any long-form content into a multi-platform content suite

Each of these will automatically reference your content strategy for voice, audience, and proof points."

## ANTI-PATTERNS (Never Do These)

- DON'T dump all questions at once — go section by section
- DON'T accept vague answers without helping them get specific — "I help people grow" is not enough
- DON'T use marketing buzzwords in the output — no "leverage," "unlock," "game-changer," "synergy"
- DON'T make the output read like a template — it should feel custom and insightful
- DON'T skip the confirmation step — always ask "did I get that right?" after each section
- DON'T label frameworks by name in the output — weave them in naturally
- DON'T write a novel — keep each section concise and scannable

$ARGUMENTS
