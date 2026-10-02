# /flex

**You built it. Now flex.**

Turn any project or website into a short, polished, shareable launch video — music, motion, and share copy included. One command.

Stack-agnostic. Works with plain HTML, React, Next.js, Vue, Svelte, Astro, or whatever the project uses. No forced frameworks. No extra junk files in your project.

**Launch site:** enable GitHub Pages on the `docs/` folder, or open `docs/index.html` locally.

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

Add `-g` for global install. Also works with public skill registries that accept GitHub skill URLs (see `docs/marketplace.md`).

## Use it

```
let's /flex
/flex --tone polished
/flex --tone "fake Series A launch"
/flex --format vertical
/flex --vertical-first
/flex --formats landscape,vertical
/flex --voice
/flex --lang bn
/flex --brand ./brand.json
/flex --batch https://a.com https://b.com
/flex --ab default,yc-parody
/flex --post-hook ./hooks/upload.sh
/flex doctor
```

You get a `flex-output/` folder with the plan, video, poster, and multi-platform share copy.

## What makes flex different

- **Stack-agnostic** — no fixed language or framework. No extra files in your project.
- **Deep website scan** — live render, overlays dismissed, section-by-section capture.
- **Voice language auto-detect** — narration matches the content language when `--voice` is on.
- **Multi-format & A/B** — landscape / vertical / square; compare tones in one run.
- **Multi-platform share copy** — X, LinkedIn, Instagram captions included.
- **Brand kit, batch mode, post-hooks** — optional power features for real workflows.
- **Doctor command** — clear environment checks before you burn time rendering.
- **Works with every major agent** — Claude, Codex, Antigravity, opencode, Cursor, and more.

## Requirements

- An agent that supports Agent Skills
- Node.js 22+
- FFmpeg on PATH
- For full mode: Hyperframes CLI (`npx hyperframes doctor`)

Run `/flex doctor` to verify.

## What's in this repo

- `skills/flex/` — main skill, slim mode, references, optional assets
- `examples/` — gallery structure for demo videos
- `docs/` — launch page + marketplace notes (GitHub Pages ready)
- Discovery paths for Claude, Codex, Antigravity, opencode
- `CHANGELOG.md` — version history
- MIT licensed

## Credits

Inspired by the open-source agent skill pattern. Built for practical use.
