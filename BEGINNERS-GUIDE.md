# Beginner's Guide

Never used Claude Code before? This walks you through everything from scratch. Takes about 10 minutes.

## Step 1: Install VS Code

1. Go to [code.visualstudio.com](https://code.visualstudio.com/)
2. Download for your operating system (Mac, Windows, or Linux)
3. Run the installer
4. Launch VS Code

Already have VS Code? Skip to Step 2.

## Step 2: Install the Claude Code Extension

1. Open VS Code
2. Click the **Extensions** icon in the left sidebar (or press `Cmd+Shift+X` on Mac / `Ctrl+Shift+X` on Windows)
3. Search for **"Claude Code"**
4. Find the one by **Anthropic** and click **Install**
5. A Claude Code icon will appear in your left sidebar

## Step 3: Authenticate

Click the Claude Code icon in the sidebar to open it. You have two options:

**Option A: Claude Subscription (Recommended)**
If you have a Claude Pro ($20/month) or Max subscription, click "Log in" and sign in with your Claude account. That's it — no API key needed.

**Option B: Anthropic API Key**
If you don't have a subscription:
1. Go to [console.anthropic.com](https://console.anthropic.com/) and create an account
2. Generate an API key
3. Open the terminal in VS Code (`` Ctrl+` `` or `` Cmd+` ``)
4. Run:
```bash
export ANTHROPIC_API_KEY=your-key-here
```

To make this permanent, add that line to your `~/.zshrc` (Mac) or `~/.bashrc` (Linux).

## Step 4: Clone the Content Marketing Skills

Open the terminal in VS Code (`` Ctrl+` `` or `` Cmd+` ``) and run:

```bash
git clone https://github.com/benchuayz/contentmarketingskills.git
```

Then open that folder in VS Code:
1. **File** → **Open Folder**
2. Navigate to `contentmarketingskills`
3. Click **Open**

## Step 5: Verify Skills Are Loaded

Open the Claude Code panel (click the icon in the sidebar) and type `/`. You should see 6 skills:

- `/content-foundation`
- `/creator-analysis`
- `/short-form-script`
- `/youtube-script`
- `/linkedin-writer`
- `/content-repurpose`

If you see them, you're ready.

**Not seeing skills?** Make sure you opened the `contentmarketingskills` folder (not a parent folder). Claude Code discovers skills from the `.claude/skills/` directory in your current workspace.

## Step 6: Run Your First Skill

Type `/content-foundation` in the Claude Code panel.

This is a 10-minute interactive questionnaire that builds your content strategy. It'll ask about your identity, audience, proof points, voice, and content pillars. Every other skill references this document, so start here.

## Optional: YouTube Transcription (yt-dlp)

Some skills can automatically pull transcripts from YouTube videos. Open your terminal and run:

```bash
# macOS
brew install yt-dlp

# Windows/Linux
pip install yt-dlp
```

## Optional: Instagram/TikTok Transcription (Supadata)

To pull transcripts from Instagram Reels and TikTok videos:

1. Go to [supadata.ai](https://supadata.ai/) and create a free account (30 seconds)
2. Copy your API key from the dashboard
3. Set it in your terminal:
```bash
export SUPADATA_API_KEY=your-key-here
```

Free tier gives you 100 credits/month.

## What to Do Next

1. `/content-foundation` — Build your strategy (do this first)
2. `/creator-analysis` — Analyze 3 creators you admire, build your style profile
3. Pick any skill based on what you need:
   - Short-form videos → `/short-form-script`
   - YouTube videos → `/youtube-script`
   - LinkedIn posts → `/linkedin-writer`
   - Repurpose existing content → `/content-repurpose`

Each skill automatically loads your strategy and style profile for personalized output.
