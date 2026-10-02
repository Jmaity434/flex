# /flex

**You built it. Now flex.**

Turn any project or website into a short, polished, shareable launch video — music, motion, and share copy included. One command.

Stack-agnostic. Works with plain HTML, React, Next.js, Vue, Svelte, Astro, or whatever the project uses. No forced frameworks. No extra junk files in your project.

## Install

**Claude Code:**
```
/plugin marketplace add Jmaity434/flex
/plugin install flex@flex
```

**Codex:**
```
codex plugin marketplace add Jmaity434/flex
codex plugin add flex@flex
```

**Any other agent** (Cursor, Antigravity, opencode, Gemini CLI, etc.):
```
npx skills add https://github.com/Jmaity434/flex --skill flex
```

Add `-g` for global install.

## Use it

From any project directory:

```
let's /flex
```

Or with options:

```
/flex --tone polished
/flex --tone "fake Series A launch"
/flex --format vertical
/flex --voice
```

You get a `flex-output/` folder with the plan, composition, `flex.mp4`, poster, and share copy.

## What makes flex different

- **Stack-agnostic** — reads whatever the project is actually built with. No fixed language or framework assumptions. Does not create unnecessary files in your project.
- **Deep website scan** — when given a URL, renders the live site (including JS-heavy pages), dismisses overlays, scrolls section-by-section, extracts real colors, fonts, copy, UI, and product flow.
- **Works with every major agent** — Claude Code, Codex, Google Antigravity, opencode, Cursor, and more via standard skill discovery paths.
- **Clean output only** — everything goes into `flex-output/` (or a timestamped folder). Your source tree stays untouched.

## Requirements

- An agent that supports Agent Skills
- Node.js 22+
- FFmpeg on PATH
- For full mode: Hyperframes CLI (`npx hyperframes doctor`)

## What's in this repo

- `skills/flex/` — the main skill + references
- `skills/flex/slim.md` — lean version for models that prefer building the video themselves
- Discovery paths for Claude, Codex, Antigravity, opencode
- MIT licensed

## Credits

Inspired by the open-source agent skill pattern. Built for practical use.
