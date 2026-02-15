# Setup Guide

Step-by-step instructions to get the Content Engine running. Takes about 5 minutes.

## Prerequisites

- A computer (Mac, Windows, or Linux)
- Node.js 18+ installed ([download here](https://nodejs.org/))
- An Anthropic API key ([sign up here](https://console.anthropic.com/))

**Cost:** The Anthropic API charges per usage. Typical content creation costs $5-20/month depending on how much you generate. Running `/content-foundation` once costs roughly $0.10-0.30.

## Step 1: Install Claude Code

Open your terminal and run:

```bash
npm install -g @anthropic-ai/claude-code
```

If you're on macOS, you can also use Homebrew:
```bash
brew install claude-code
```

Verify the installation:
```bash
claude --version
```

## Step 2: Set Your API Key

If this is your first time using Claude Code, it will prompt you for your Anthropic API key when you first run it. You can also set it manually:

```bash
export ANTHROPIC_API_KEY=your-key-here
```

To make this permanent, add the line above to your `~/.bashrc`, `~/.zshrc`, or equivalent shell config file.

## Step 3: Clone This Repo

```bash
git clone https://github.com/benchuayz/contentmarketingskills.git
cd contentmarketingskills
```

## Step 4: Open Claude Code

From inside the repo directory:

```bash
claude
```

Claude Code will automatically discover the skills in `.claude/skills/`. You should see them available when you type `/`.

## Step 5: Run Your First Skill

Start with the foundation:

```
/content-foundation
```

This will walk you through an interactive questionnaire (about 10 minutes) and create your content strategy document. Every other skill references this.

## Step 6 (Optional): Install yt-dlp

Some skills can automatically pull transcripts from YouTube videos. To enable this:

```bash
# macOS
brew install yt-dlp

# Other systems
pip install yt-dlp
```

This is completely optional. If yt-dlp isn't installed, skills will ask you to paste content manually instead.

## Troubleshooting

**Skills not showing up?**
Make sure you're inside the `content-engine-claude-code` directory when you run `claude`. Skills are discovered from the `.claude/skills/` folder in your current directory.

**API key issues?**
Visit [console.anthropic.com](https://console.anthropic.com/) to verify your key is active and has credits.

**yt-dlp not downloading subtitles?**
Some videos don't have auto-generated captions. Try a different video, or paste the transcript manually.

**Getting rate limited?**
The Anthropic API has rate limits on free-tier plans. If you're generating a lot of content, you may need to upgrade your plan.

## Recommended Workflow

1. `/content-foundation` — Set up once, reference forever
2. `/creator-analysis` — Analyze 3 creators you admire, build your style profile
3. Pick your skill based on what you need:
   - Creating short-form videos? `/short-form-script`
   - Planning a YouTube video? `/youtube-script`
   - Building LinkedIn presence? `/linkedin-writer`
   - Got existing content to repurpose? `/content-repurpose`

Each skill will automatically load your content strategy and style profile for personalized output.
