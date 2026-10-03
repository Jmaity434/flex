# flex — AI SaaS Launch Video Generator (Agent Skill)

**You built it. Now flex.**

**flex** is an open-source **AI agent skill** that turns any **SaaS product**, startup website, or app into a short, polished **product launch video** — with motion, music, and ready-to-post share copy — in one command.

Use it to create **SaaS launch videos**, **product demo videos**, **startup promo videos**, and **social-ready vertical reels** without opening a video editor.

> Stack-agnostic · Works with Claude Code, Codex, Cursor, Antigravity, opencode · MIT licensed

**Repo:** https://github.com/Jmaity434/flex  
**Docs / landing:** enable GitHub Pages on the `docs/` folder → `https://jmaity434.github.io/flex/`

---

## What is flex?

flex is a **product launch video generator for AI coding agents**. You run `/flex` inside a project (or point it at a URL), and the agent:

1. Reads your product (code or live website)
2. Plans a 15–25 second launch storyboard
3. Builds a shareable **SaaS marketing video**
4. Writes captions for X, LinkedIn, and Instagram

It is built for founders, indie hackers, and marketers who ship fast and need a **launch video for SaaS**, app, or website **without hiring an editor**.

### Keywords this project covers

AI launch video · SaaS launch video · product launch video generator · AI product demo video · startup promo video · website to video AI · Claude Code skill · agent skill video · automated SaaS marketing video · vertical product reel · open source launch video tool

---

## Who is it for?

| Audience | Use case |
|----------|----------|
| **SaaS founders** | Ship a launch video the same day you ship the product |
| **Indie hackers** | Turn a landing page into a LinkedIn / X / Reels clip |
| **Agencies** | Batch product videos for multiple client sites |
| **Developers using AI agents** | One command after `/build` — `/flex` |

---

## Install (AI agent skill)

### Claude Code
```bash
/plugin marketplace add Jmaity434/flex
/plugin install flex@flex
```

### Codex
```bash
codex plugin marketplace add Jmaity434/flex
codex plugin add flex@flex
```

### Any agent (Cursor, Antigravity, opencode, Gemini CLI, …)
```bash
npx skills add https://github.com/Jmaity434/flex --skill flex
```

Add `-g` for a global install.

---

## Quick start — generate a SaaS launch video

```text
let's /flex
```

Or with options:

```text
/flex --tone polished --format vertical
/flex --voice
/flex --formats landscape,vertical
/flex --ab default,yc-parody
/flex https://your-saas-landing-page.com
/flex doctor
```

**Output:** `flex-output/flex.mp4` + poster + multi-platform share copy.

---

## Features (SaaS & product video focused)

- **SaaS / product launch videos** in 15–25 seconds
- **Website → video**: deep scan of live landing pages (JS apps included)
- **Stack-agnostic**: React, Next.js, Vue, Svelte, plain HTML — any stack
- **Vertical + landscape + square** for Reels, Shorts, LinkedIn, X
- **Voiceover** with **language auto-detect** (not English-only)
- **Brand kit** support for consistent SaaS branding
- **A/B tones** and **batch mode** for multiple products or sites
- **Share copy** for X, LinkedIn, Instagram
- **Post-render hooks** for your upload/post workflow
- Works with **Claude Code**, **Codex**, **Cursor**, **Google Antigravity**, **opencode**

---

## Why flex instead of a generic video editor?

| Need | Traditional editor | flex |
|------|--------------------|------|
| Time to first SaaS launch video | Hours | Minutes (one agent command) |
| Uses real product UI & copy | Manual screenshots | Reads code / scans site |
| Multi-platform captions | Extra work | Included |
| Fits AI coding workflow | Separate tool | Native agent skill |

---

## Requirements

- AI agent that supports Agent Skills
- Node.js 22+
- FFmpeg on PATH
- Full mode: Hyperframes CLI (`npx hyperframes doctor`)

Run `/flex doctor` to verify your environment.

---

## Repository structure

- `skills/flex/` — main skill, slim mode, references, assets
- `examples/` — gallery for demo SaaS / product videos
- `docs/` — SEO landing page + marketplace notes (GitHub Pages)
- Discovery paths for Claude, Codex, Antigravity, opencode
- `CHANGELOG.md` — releases

---

## SEO & discovery topics

Suggested GitHub topics (add under repo **About → Topics**):

`saas-launch-video` `product-launch-video` `ai-video-generator` `agent-skills` `claude-code` `claude-skills` `launch-video` `product-demo` `saas-marketing` `startup-video` `website-to-video` `open-source`

---

## License

MIT — free to use for commercial SaaS launches and client work.

---

## Credits

Built for practical shipping. Inspired by the open agent-skills ecosystem.
