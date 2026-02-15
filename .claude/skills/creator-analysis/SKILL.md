---
name: creator-analysis
description: Analyze 3 creators you admire, extract their style patterns, and generate sample scripts blending their voice with yours.
argument-hint: [creator 1 URL or name] [creator 2 URL or name] [creator 3 URL or name] — or just run /creator-analysis and it will guide you.
disable-model-invocation: false
user-invocable: true
allowed-tools: Read, Write, Edit, Bash, Glob, Grep, WebFetch, WebSearch
---

# Creator Analysis & Style Extraction

You analyze 3 creators the user admires, extract their content patterns and style DNA, create a reusable style profile, and generate sample scripts that blend those styles with the user's own voice.

This is the most powerful skill in the system. The style profile it creates makes every other skill's output dramatically better.

## CRITICAL RULES

1. **ANALYZE SPECIFIC PATTERNS, NOT VIBES** — Bad: "Creator A uses strong hooks." Good: "Creator A opens with a contrarian reframe in 8/10 videos, using the pattern 'Everyone says [X] but [shocking alternative].' Their hooks average 12 words and always include a specific number."
2. **AUTO-FETCH WITH GRACEFUL FALLBACK** — Always TRY to pull content automatically. But if fetching fails, smoothly ask for manual paste without making the user feel like something broke.
3. **BLEND, DON'T COPY** — The style profile should combine the BEST elements of all 3 creators with the user's own voice. Not a clone of any single creator.
4. **FEEDBACK ROUND IS MANDATORY** — Always present sample scripts and ask for feedback before finalizing the style profile.

## PROCESS

### Step 1: Load User's Foundation (If It Exists)

Check if `my-content/content-strategy.md` exists.
- If yes: Read it. You'll use their voice, audience, and proof points when generating sample scripts.
- If no: That's okay. Let the user know: "I notice you haven't run `/content-foundation` yet. I can still analyze creators and build a style profile, but the sample scripts will be more generic without your content strategy. Want to continue, or run `/content-foundation` first?"

### Step 2: Get Creator Inputs

If the user provided creator names/URLs in the arguments, use those. Otherwise ask:

"Give me 3 creators whose content style you admire. For each, provide ONE of:
- A YouTube channel URL or video URL
- An Instagram handle (e.g., @garyvee)
- A TikTok handle
- Or just paste 3-5 of their best posts/scripts directly

**What specifically do you admire about each?** (e.g., 'their hooks are insane,' 'their storytelling,' 'their energy,' 'how they explain complex things simply')"

### Step 3: Fetch Content (Auto-Fetch with Fallback Cascade)

For each creator, attempt to gather content using this priority order:

**If YouTube URL provided:**
1. Check if `yt-dlp` is installed: Run `which yt-dlp`
2. If installed — extract auto-generated subtitles from their recent videos:
   ```
   yt-dlp --write-auto-sub --sub-lang en --skip-download --write-sub -o "my-content/creator-analysis/%(uploader)s/%(title)s" [CHANNEL_URL]
   ```
   For a single video URL, pull that video's subtitles.
3. If yt-dlp is NOT installed — tell the user:
   "I can automatically pull transcripts from YouTube if you install yt-dlp. It's a one-time setup:
   - Mac: `brew install yt-dlp`
   - Other: `pip install yt-dlp`

   Want to install it now, or would you prefer to paste the content manually?"
4. FALLBACK: Use WebSearch to search for "[creator name] best content" or "[creator name] transcript" and WebFetch to read what's available.
5. FINAL FALLBACK: Ask user to paste 5-10 of their best posts, scripts, or video transcripts.

**If Instagram/TikTok handle provided:**
1. Use WebSearch: search for `[handle] instagram content [niche]` or `[handle] best posts`
2. Use WebFetch on any public pages found
3. FALLBACK: "I wasn't able to pull their content automatically from [platform]. Could you paste 5-10 of their best posts or video scripts? The more you paste, the better the style extraction will be."

**If content pasted directly:**
- Process immediately. This is the most reliable path.

**IMPORTANT:** Always tell the user what you're trying to do. "Let me try to pull some of @hormozi's recent content..." If it fails, be straightforward: "Instagram blocked my access. No worries — could you paste some of their content instead?"

### Step 4: Analyze Each Creator

For each creator, analyze their content across these 7 dimensions. Be SPECIFIC — use actual patterns, counts, and examples from their content.

**4.1 Hook Patterns**
- How do they open? (Question? Bold claim? Story? Contrarian statement?)
- Average hook length (in words)
- Do they use text overlays, sound effects, or visual hooks?
- What pattern appears most frequently?

**4.2 Content Structure**
- How do they build? (Story arc? Framework? List? Build to a reveal?)
- How long are their typical pieces?
- Do they use sections/chapters or continuous flow?
- Where do they place their strongest point?

**4.3 Energy & Pacing**
- Fast and intense? Slow and deliberate? Conversational and casual?
- Do they speed up or slow down at key moments?
- Camera distance / movement patterns (close-up = intensity, wide = casual)
- Pauses — do they use silence for emphasis?

**4.4 Language Patterns**
- Vocabulary level (simple/complex/mixed)
- Signature phrases or catchphrases
- Do they use profanity? How?
- Sentence length patterns (short punchy? Long flowing? Mixed?)
- Do they use analogies or metaphors? What kind?

**4.5 Value Delivery**
- How do they make the viewer feel smart?
- Teaching style (diagnose first? Example first? Framework first? Story first?)
- Do they use specific numbers or stay general?
- Do they reference authorities, studies, or just personal experience?

**4.6 Engagement Triggers**
- How do they keep attention mid-content? (Interest peaks, pattern interrupts, open loops)
- Do they use CTAs? Where and how?
- Do they reference the viewer directly? ("You're probably thinking...")

**4.7 Closing Patterns**
- How do they end? (Hard CTA? Soft loop? Question? Cliffhanger? Call to action?)
- Do they loop back to the opening?
- Average closing length

### Step 5: Create Individual Creator Analysis Docs

For each creator, save an analysis to `my-content/creator-analysis/[creator-name].md`:

```markdown
# Creator Analysis: [Creator Name]

## Platform & Niche
[Platform, follower count if known, niche/topic]

## What Makes Them Work
[2-3 sentence summary of their secret sauce]

## Hook Approach
[Specific patterns with examples from their content]

## Content Structure
[How they build their pieces]

## Energy & Pacing
[Their speed, intensity, and rhythm]

## Language DNA
- Signature phrases: [list]
- Vocabulary level: [simple/complex/mixed]
- Profanity: [yes/no/sometimes]
- Sentence patterns: [short/long/mixed]

## Teaching Style
[How they deliver value]

## Engagement Triggers
[How they keep attention]

## Closing Style
[How they end]

## Key Takeaways
[3-5 specific, actionable patterns to borrow]
```

### Step 6: Synthesize the Style Profile

Now blend the best elements of all 3 creators with the user's own voice (from content-strategy.md if available).

The style profile should NOT be a Frankenstein. It should feel like a coherent voice that borrows the STRONGEST element from each creator.

Save to `my-content/style-profile.md`:

```markdown
# Your Content Style Profile

Created: [date]
Based on: [Creator 1], [Creator 2], [Creator 3]

## Voice Summary
[2-3 sentence description of the blended style. Should feel like a coherent creative direction, not a mix-and-match list.]

## Hook Approach
[What types of openings to use, with 3-5 specific examples tailored to the user's niche]

## Content Structure
[How to build a piece of content, step by step]

## Energy & Pacing
[Speed, intensity, when to accelerate, when to pause]

## Language & Vocabulary
**Use:** [Words, phrases, sentence patterns to adopt]
**Avoid:** [Words, phrases, styles to stay away from]
**Profanity level:** [None / Occasional for emphasis / Regular]
**Humor level:** [None / Dry / Self-deprecating / Playful / Bold]

## Interest Peaks
[How to re-engage mid-content, with 3-5 examples tailored to user's niche]

## Closing Style
[How to end pieces, CTA approach]

## Style Influences
- From [Creator 1]: [specific elements borrowed — e.g., "their contrarian opening style"]
- From [Creator 2]: [specific elements borrowed — e.g., "their story-based value delivery"]
- From [Creator 3]: [specific elements borrowed — e.g., "their high-energy pacing and direct language"]
- Your own: [elements that are uniquely the user's — from content-strategy.md or from their answers]
```

### Step 7: Generate 3 Sample Scripts

Generate 3 short-form scripts (150-250 words each) that demonstrate the blended style. These should be flowing spoken-word — NO labeled sections (HOOK/BODY/CTA).

Each script should showcase different elements:
- **Script 1:** Creator A's hook style + Creator B's structure + user's content pillar
- **Script 2:** Creator C's energy + Creator A's value delivery + user's proof points
- **Script 3:** The most dominant combined pattern + user's contrarian position

If content-strategy.md exists, use their actual audience, proof points, and content pillars.
If not, ask: "What's one topic you'd want to make a video about?" and use that.

Read `references/hook-formulas.md` to inform hook selection.

### Step 8: Feedback Round

Present all 3 scripts and the style profile summary. Ask:

"Here are 3 sample scripts in your new blended style. Read them and tell me:
1. Which script feels MOST like you?
2. What would you change about the others?
3. Is there too much or too little of any creator's influence?
4. Any phrases or patterns that feel off?"

### Step 9: Refine

Based on feedback:
- Update the style profile with adjustments
- Regenerate any scripts that need work
- Save the final style profile to `my-content/style-profile.md`

### Step 10: Next Steps

Tell the user:

"Your style profile is saved. Now every content skill will reference it:
- `/short-form-script` — generate scripts in this style
- `/youtube-script` — full YouTube scripts matching your voice
- `/linkedin-writer` — LinkedIn posts in your style
- `/content-repurpose` — repurpose content with consistent voice

The more you use these skills and give feedback, the better the style profile gets. You can always re-run `/creator-analysis` to update it."

## ANTI-PATTERNS (Never Do These)

- DON'T analyze at the surface level — "they use good hooks" is useless. WHAT kind of hooks? HOW often? WHAT pattern?
- DON'T create a Frankenstein voice — the blend should feel coherent, not like 3 people talking at once
- DON'T skip the feedback round — always ask before finalizing
- DON'T write sample scripts with labeled sections (HOOK/BODY/CTA) — flowing spoken-word only
- DON'T give up on auto-fetching too quickly — try WebSearch before falling back to manual paste
- DON'T produce generic analysis that could apply to any creator — every insight should be specific to THAT creator's actual content
- DON'T ignore the user's own voice — the style profile should enhance their natural patterns, not replace them

$ARGUMENTS
