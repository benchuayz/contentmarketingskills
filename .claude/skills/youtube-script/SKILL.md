---
name: youtube-script
description: Create full YouTube video scripts with retention hooks, title options, thumbnail concepts, and optimized structure.
argument-hint: [topic] [target length: 8-12min or 15-25min] — or just run /youtube-script and it will guide you.
disable-model-invocation: false
user-invocable: true
allowed-tools: Read, Write, Edit, Bash, Glob, Grep, WebFetch, WebSearch
---

# YouTube Script Generator

You create complete YouTube video scripts optimized for watch time, retention, and conversion. Every script includes title options, thumbnail concepts, retention hooks, and a full spoken-word script.

## CRITICAL RULES

1. **SPOKEN WORD, NOT WRITTEN PROSE** — The script must sound like someone talking to camera, not reading a blog post. Contractions, incomplete sentences, and conversational flow are good.
2. **RETENTION HOOKS EVERY 2-3 MINUTES** — Viewers drop off constantly. Every few minutes needs a re-engagement trigger that gives them a reason to keep watching.
3. **THE FIRST 30 SECONDS DETERMINE EVERYTHING** — If your opening doesn't hook, nothing else matters. Spend disproportionate effort on the cold open.
4. **SPECIFIC > GENERIC** — Use real numbers, real examples, real stories. "I made $47k last month" beats "I had a great month."

## PROCESS

### Step 1: Load Context

Read these files if they exist:

1. `my-content/content-strategy.md` — Voice, audience, proof points
2. `my-content/style-profile.md` — Blended voice style
3. `references/youtube-structures.md` — Retention patterns and structures
4. `references/hook-formulas.md` — Opening hooks (adapted for long-form)
5. `references/interest-peaks.md` — Mid-video re-engagement
6. `references/persuasion-frameworks.md` — For authority inserts and CTAs

### Step 2: Gather Requirements

If the user provided a topic and length in arguments, confirm and proceed. Otherwise ask:

1. **Topic:** What's the video about? (Or "suggest 5 video ideas from my content pillars")
2. **Target length:** 8-12 minutes (standard) or 15-25 minutes (deep dive)?
3. **Goal:** Educational, authority-building, lead generation, or product/service pitch?
4. **Key proof points:** What specific results, stories, or examples should be woven in?
5. **CTA:** What should the viewer do? (Subscribe, download something, book a call, visit a link)

### Step 2b: YouTube Transcription (Optional)

If the user wants to base the script on existing content (a competitor video, their own podcast, etc.):

1. Ask for the YouTube URL
2. Check if `yt-dlp` is installed: `which yt-dlp`
3. If installed: `yt-dlp --write-auto-sub --sub-lang en --skip-download --write-sub -o "/tmp/yt-transcript" [URL]`
4. Read the generated `.vtt` or `.srt` file, clean it up (remove timestamps, formatting artifacts, duplicate lines)
5. Use the cleaned transcript as source material
6. If yt-dlp is NOT installed: Provide install instructions and offer manual paste as fallback

### Step 3: Choose Script Structure

Based on the topic and goal, select the best structure. Reference `references/youtube-structures.md`.

**The Framework Video** — Best for teaching a method or system
- Problem setup (why this matters)
- Framework intro (name it, explain it)
- Steps 1-3/5 with real examples for each
- Recap + how everything connects

**The Story Video** — Best for case studies, personal journeys, transformations
- Cold open with the ending (show the result first)
- Rewind to the beginning
- Build tension through the middle
- Lessons along the way
- Payoff + what the viewer can take from it

**The Listicle Video** — Best for tips, tools, mistakes
- Ranked list (worst to best or least to most important)
- "But the last one is the one nobody talks about" — retention hook
- Each item gets: the tip + the why + a real example

**The Case Study Video** — Best for proving results
- Before state (the problem)
- What changed (the catalyst)
- Exactly what was done (specifics, not vague)
- Results (with numbers)
- What the viewer can replicate tomorrow

**The Tutorial Video** — Best for how-to content
- Show the end result first (motivate them to watch)
- Prerequisites (what they need before starting)
- Step-by-step walkthrough
- Common mistakes to avoid
- Pro tips that most tutorials skip

### Step 4: Write the Script

#### 4A: Title Options (3)

Each title should:
- Create a curiosity gap or promise a specific outcome
- Include search terms the target audience would use
- Be under 60 characters for mobile display
- Avoid clickbait that can't be delivered

Format:
```
TITLE OPTION 1: [Title]
TITLE OPTION 2: [Title]
TITLE OPTION 3: [Title]
```

#### 4B: Thumbnail Concepts (3)

For each:
- **Text overlay:** 3-5 words max (what text should appear on the thumbnail)
- **Expression/emotion:** What the face should convey
- **Visual element:** What else should be in the frame
- **Color notes:** High contrast, readable on mobile

#### 4C: Cold Open (First 30 Seconds)

This is the most critical part. Structure:

1. **Hook** (first 5-8 seconds) — Adapted from hook formulas. For YouTube, you have slightly more room but the hook must be IMMEDIATE. Promise something specific.

2. **Proof/credibility** (next 5-8 seconds) — "And I'm not just saying this — [proof point]." Establishes why they should listen to you.

3. **Preview** (next 8-10 seconds) — Curiosity stack: briefly preview 2-3 things they'll learn. "In this video, I'm going to show you [X], then [Y], and by the end you'll know exactly how to [Z]."

4. **"Stay because" moment** (final 5 seconds) — Why THIS video specifically. "And I'm going to share [something you can't get elsewhere] that most people miss."

#### 4D: Body

Write the full body following the chosen structure. Include:

- **Retention hooks every 2-3 minutes** — Pull from `references/interest-peaks.md` adapted for long form. Examples:
  - "But here's where it gets interesting..."
  - "Now, most people skip this part. Don't."
  - "This next point is the one that changed everything for me."
  - "Stay with me here because this is where it all comes together."

- **Authority inserts** — Spread proof points throughout, not dumped at the beginning. Use the user's credibility from content-strategy.md.

- **Transition bridges** — Each section should create curiosity about what's next. Never just say "okay, moving on to point two."

- **Real examples** — Every concept needs a concrete example. "Here's what this looks like in practice..."

Mark retention hooks in the script with `[RETENTION HOOK]` so the editor knows to add visual emphasis.

#### 4E: Mid-Video CTA (at ~1/3 mark)

Soft and natural. It should NOT break the flow. Pattern:

"Quick thing — if you're getting value from this, hit subscribe. I put out [frequency] videos on [topic]. Okay, back to [what we were talking about]..."

Keep it under 15 seconds. The viewer should barely notice it was a CTA.

Mark with `[MID-VIDEO CTA]` in the script.

#### 4F: Closing (Final 60 Seconds)

1. **Recap** — One sentence summarizing the key insight: "So remember — [core takeaway]."
2. **Loop back** — Reference the opening promise: "At the start I told you [X]. Now you know exactly how to [Y]."
3. **CTA** — Clear and direct: "If you want [related thing], I made a [free resource / next video] that goes deeper. Link in the description."
4. **Optional chain** — "And if you want to learn [related topic], watch this video next." (Point to suggested video)

### Step 5: Voice Check

Run these checks before presenting:

- [ ] Does it sound like someone TALKING, not reading?
- [ ] Are retention hooks placed every 2-3 minutes?
- [ ] Does the cold open hook in the first 5 seconds?
- [ ] Are proof points spread throughout (not front-loaded)?
- [ ] Is every concept backed by a specific example?
- [ ] Does the mid-CTA feel natural and brief?
- [ ] Does the closing loop back to the opening?
- [ ] Is it the right length? (~150 words per minute of target video length)

### Step 6: Present and Save

Present the full script with all sections clearly marked. Then ask:

"Here's your full script. A few things to check:
- Do the title options feel right for your audience?
- Does the cold open hook you in the first 5 seconds?
- Any sections that feel too long or too short?
- Does the CTA feel natural?"

Save to `my-content/youtube-scripts/[topic-slug].md` if the user approves.

## ANTI-PATTERNS (Never Do These)

- NO blog-post prose — write how people talk, not how people write
- NO "Hey guys, welcome back to my channel" — cold open with value immediately
- NO retention dead zones — if more than 3 minutes pass without a hook, add one
- NO vague claims — always pair advice with specific examples or numbers
- NO walls of text — YouTube scripts need varied pacing (short lines, longer explanations, questions, pauses)
- NO hard-sell mid-video CTA — keep it under 15 seconds and natural
- NO generic titles — titles must create a specific curiosity gap
- NO scripts that could be about anyone — weave in the user's actual story, numbers, and examples

## LENGTH GUIDE

| Target Video Length | Script Word Count | Retention Hooks |
|---|---|---|
| 8 minutes | ~1,200 words | 3-4 |
| 10 minutes | ~1,500 words | 4-5 |
| 12 minutes | ~1,800 words | 5-6 |
| 15 minutes | ~2,250 words | 6-7 |
| 20 minutes | ~3,000 words | 8-10 |
| 25 minutes | ~3,750 words | 10-12 |

$ARGUMENTS
