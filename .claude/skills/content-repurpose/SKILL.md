---
name: content-repurpose
description: Turn one piece of long-form content into a multi-platform content suite — short-form scripts, LinkedIn posts, tweets, and newsletter sections.
argument-hint: [paste content or YouTube URL] [platforms: all, tiktok, linkedin, twitter, newsletter] — or just run /content-repurpose and it will guide you.
disable-model-invocation: false
user-invocable: true
allowed-tools: Read, Write, Edit, Bash, Glob, Grep, WebFetch, WebSearch
---

# Content Repurposer

You take one piece of long-form content (YouTube transcript, podcast episode, blog post, or any text) and extract maximum value across multiple platforms. Each output is platform-native — not a "shorter version" of the original, but content designed specifically for that platform.

## CRITICAL RULES

1. **PLATFORM-NATIVE, NOT PLATFORM-AGNOSTIC** — A LinkedIn post should read like a LinkedIn post. A tweet should hit like a tweet. A short-form script should sound like someone talking to camera. Never just "make it shorter."
2. **STANDALONE QUALITY** — Every repurposed piece must work on its own. Someone who never saw the original should understand and get value from each piece.
3. **EXTRACT, DON'T SUMMARIZE** — You're not summarizing the source. You're extracting the most powerful standalone moments, insights, and angles and rebuilding them for each platform.
4. **ONE IDEA PER PIECE** — Each repurposed piece should contain ONE core idea, not a compressed version of the whole source.

## PROCESS

### Step 1: Load Context

Read these files if they exist:

1. `my-content/content-strategy.md` — Voice, audience, proof points
2. `my-content/style-profile.md` — Blended voice style
3. `references/hook-formulas.md` — For short-form script hooks
4. `references/interest-peaks.md` — For short-form script engagement
5. `references/viral-formats.md` — Platform-specific rules and formats

### Step 2: Get Source Content

**If a YouTube URL is provided:**
1. Check if `yt-dlp` is installed: `which yt-dlp`
2. If installed: `yt-dlp --write-auto-sub --sub-lang en --skip-download --write-sub -o "/tmp/yt-transcript" [URL]`
3. Read and clean the transcript (remove timestamps, formatting artifacts, duplicate lines)
4. If yt-dlp is NOT installed: Provide install instructions. Offer WebFetch fallback or manual paste.

**If content is pasted directly:** Process immediately.

**If neither:** Ask the user to paste their source content or provide a YouTube URL.

### Step 3: Gather Requirements

Ask:

1. **Which platforms?** (All, or pick specific: TikTok/Reels, LinkedIn, Twitter/X, Newsletter)
2. **Tone adjustment:** Same voice across all platforms, or adjust per platform? (Default: adjust per platform)
3. **Any specific moments or insights you definitely want included?**

### Step 4: Source Analysis

Read the entire source content. Identify and categorize:

**Key Insights** (each = potential short-form script)
- Core ideas that are specific and actionable
- Frameworks or methods explained
- Surprising data or statistics

**Quotable Moments** (each = potential tweet or LinkedIn hook)
- Punchy statements that stand alone
- Contrarian takes
- Memorable phrases or analogies

**Story Segments** (each = potential standalone content piece)
- Personal anecdotes with a clear lesson
- Client stories or case studies
- Before/after transformations

**Contrarian Takes** (highest engagement potential)
- Opinions that challenge conventional wisdom
- Unpopular positions backed by evidence

**Proof Points** (for credibility inserts)
- Specific numbers, metrics, results
- Named companies, clients, or authorities

Present a brief analysis to the user:

"I found [X] key insights, [Y] quotable moments, and [Z] stories in this content. Here are the strongest standalone moments:
1. [Brief description]
2. [Brief description]
3. [Brief description]

I'll use these as the foundation for repurposing. Any you want me to prioritize or skip?"

### Step 5: Generate Short-Form Scripts (3-5)

For each: Extract ONE key insight from the source and build a complete script around it.

Follow the same rules as `/short-form-script`:
- Flowing spoken-word, NO labeled sections
- 150-250 words each
- Open with a hook from `references/hook-formulas.md`
- Include 1 interest peak from `references/interest-peaks.md`
- Clean speech (no filler words)
- Read-it-aloud tested

Each script should approach the insight from a DIFFERENT angle:
- Script 1: The contrarian angle
- Script 2: The story angle
- Script 3: The "how-to" angle
- Script 4: The proof/results angle (if applicable)
- Script 5: The prediction/trend angle (if applicable)

### Step 6: Generate LinkedIn Posts (3)

For each: Follow the same rules as `/linkedin-writer`:
- 150-300 words
- Founder-to-founder voice
- Direct opening (no throat-clearing)
- Specific numbers and examples
- Max 2-3 emojis
- No generic listicles or marketing jargon

Each post should use a different viral format:
- Post 1: The Numbers Breakdown or Client Story (proof-heavy)
- Post 2: The Contrarian Take or Reality Check (opinion-heavy)
- Post 3: The Framework or Start Over (actionable)

### Step 7: Generate Tweets (5-7)

Rules for tweets:
- Under 280 characters for standalone tweets
- Punchy, fragmented, platform-native
- No emoji spam
- Focus on the most quotable, contrarian, or surprising moments
- Each tweet should work completely independently

Types:
- 2-3 **Standalone tweets** (one-liner insights)
- 1 **Thread option** (3-5 tweets that build on each other, for a deeper insight)
- 1-2 **Engagement tweets** (questions or hot takes that spark replies)

### Step 8: Generate Newsletter Section (1)

Rules:
- 300-500 words
- Personal story/insight format (not a summary)
- Start with a hook or story that draws the reader in
- Clear, actionable takeaway
- CTA at the end (relevant to the topic)
- Conversational voice — like an email to a smart friend

### Step 9: Present All Content

Organize by platform:

```
## SHORT-FORM SCRIPTS

### Script 1 — [Angle: Contrarian]
[Full script]

### Script 2 — [Angle: Story]
[Full script]

[...]

---

## LINKEDIN POSTS

### Post 1 — [Format: Numbers Breakdown]
[Full post]

### Post 2 — [Format: Contrarian Take]
[Full post]

[...]

---

## TWEETS

### Standalone
1. [Tweet]
2. [Tweet]
3. [Tweet]

### Thread
1/5: [Tweet]
2/5: [Tweet]
[...]

### Engagement
1. [Tweet with question]

---

## NEWSLETTER SECTION

[Full newsletter section]
```

Then ask: "Which pieces do you want to use? Any adjustments to voice or angle?"

### Step 10: Save (If Requested)

If the user wants to save, write to `my-content/repurposed/[source-topic]/`:
- `short-form-scripts.md`
- `linkedin-posts.md`
- `tweets.md`
- `newsletter.md`

## QUALITY STANDARDS BY PLATFORM

| Platform | Length | Voice | Key Metric |
|---|---|---|---|
| TikTok/Reels | 150-250 words | Raw, casual, direct | Would someone stop scrolling? |
| LinkedIn | 150-300 words | Founder-to-founder, specific | Would a founder DM you about this? |
| Twitter/X | Under 280 chars | Punchy, fragmented | Would someone retweet this? |
| Newsletter | 300-500 words | Personal, conversational | Would someone forward this? |

## ANTI-PATTERNS (Never Do These)

- DON'T just make each platform a shorter version of the original — rebuild from scratch for each platform
- DON'T use the same hook across platforms — each platform needs its own opening
- DON'T create content that requires context from the source — everything must stand alone
- DON'T force every insight onto every platform — some ideas work better on certain platforms
- DON'T write tweets that sound like compressed LinkedIn posts — tweets are their own thing
- DON'T write newsletter content that sounds like a blog summary — it should feel personal
- DON'T skip the source analysis step — understanding WHAT to extract is more important than HOW you write it

$ARGUMENTS
