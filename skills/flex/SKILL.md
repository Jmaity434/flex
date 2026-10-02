---
name: flex
description: Turn the current project or a website into a short, polished, shareable launch video. Use when someone says "/flex", "let's flex", "make a launch video", "turn this into a video", or wants to show off what they built. Stack-agnostic. Supports voice language auto-detect, multi-format, batch, brand kit, A/B tones, and post-render hooks.
---

# /flex

You built it. Now let's flex.

## Invocation dispatch (must happen first)

**Status:** Tell the user you are starting: `Flex starting — inspecting…`

**Model check.** If you are Claude Opus 5.5 (or a model that prefers building the video itself) and the invocation does not ask for the full workflow (`--full`) or for voiceover (`--voice`), switch to the slim path: read `<skill-dir>/slim.md` and follow it. Pass options as plain-language direction. Tell the user in one line first.

Before inspecting, parse the complete `/flex` invocation and set flags below.

## What this skill does

1. Inspects the project or deeply scans a live website (stack-agnostic).
2. Plans a short flex concept specific to this project.
3. Scripts and storyboards the video.
4. Composes (Hyperframes full mode, or local tools in slim mode).
5. Renders, writes multi-platform share copy, and optionally runs post-render hooks.

**Hard rule:** Never create extra source files or framework scaffolding inside the user's project. All output lives only in `flex-output/` (or timestamped `flex-output-YYYY-MM-DD-HHmmss/`).

## Parsing the invocation

```
/flex
/flex --tone chaotic
/flex --tone polished --format vertical
/flex --formats landscape,vertical
/flex --voice
/flex --brand ./brand.json
/flex --batch url1 url2
/flex --ab default,yc-parody
/flex --post-hook ./hooks/post.sh
/flex https://example.com
```

| Option | Values | Default |
|---|---|---|
| `--tone` | preset or freeform | inferred |
| `--format` | `landscape`, `vertical`, `square` | `landscape` |
| `--formats` | comma list e.g. `landscape,vertical` | single format |
| `--duration` | seconds | auto (15-25s) |
| `--no-music` | flag | music on |
| `--no-sfx` | flag | sfx on |
| `--title` | string | inferred |
| `--voice` | flag | narration off |
| `--lang` | `auto` or language code (e.g. `bn`, `en`, `hi`) | `auto` when `--voice` |
| `--brand` | path to brand kit JSON | none |
| `--batch` | space-separated URLs or paths | single input |
| `--ab` | comma list of tones | single tone |
| `--post-hook` | path to script to run after render | none |
| `--vertical-first` | flag | off (sets default format to vertical) |

### Tone presets (when to use)

| Tone | Use when | Energy |
|---|---|---|
| `default` | Most consumer apps, playful products | Playful, clean, postable |
| `polished` | Premium, serious, elegant products | Restrained, elegant |
| `yc-parody` | Absurd products that benefit from deadpan startup energy | Deadpan, serious delivery of silly claims |
| `chaotic` | Loud, meme-y, high-energy launches | Fast, aggressive |
| `deadpan` | Dry humor, understated confidence | Calm, minimal |
| `cinematic` | Trailer-scale, dramatic reveals | Big motion, epic claims |
| `app-store` | Feature-card clean, benefit-focused | Smooth, corporate-but-not-boring |

Full definitions: [references/tones.md](references/tones.md)

## Output directory

Default: `flex-output/`. If it already exists, use timestamped `flex-output-YYYY-MM-DD-HHmmss/`.

When `--formats` or `--ab` is used, create subfolders per variant, e.g.:
- `flex-output/landscape/`
- `flex-output/vertical/`
- `flex-output/ab-default/`
- `flex-output/ab-yc-parody/`

## Status messages (required)

Emit short progress lines so the user knows what is happening:

1. `Flex starting — inspecting…`
2. `Planning storyboard…`
3. `Composing…`
4. `Rendering…`
5. `Writing share copy…`
6. `Done. Output in <path>`

## Doctor / environment check

If the user runs `/flex doctor` or environment looks broken, run this check and report clearly:

- Node.js 22+ available?
- FFmpeg on PATH?
- (Full mode) Hyperframes CLI available? (`npx hyperframes doctor`)
- Write permission in current directory?

Print a short pass/fail table. Do not proceed with render if critical tools are missing; tell the user exactly what to install.

---

## Step 1: Inspect

**Read:** [references/step-1-inspect.md](references/step-1-inspect.md)

Stack-agnostic. Project code or deep website scan.

When `--voice` is on and `--lang auto` (default):
- Detect the primary language of the site's/project's visible copy.
- Set narration language to that language. Do not force English.

When `--brand` is provided, load the brand kit (see [references/brand-kit.md](references/brand-kit.md)) and apply logo, colors, fonts as overrides.

**Gate:** All planning rubric questions answered.

---

## Step 2: Plan and storyboard

**Read:** [references/step-2-plan.md](references/step-2-plan.md)

Write `<output-dir>/flex-plan.md`.

If `--ab` is set, produce one plan per tone (or one plan with clear per-tone branches).

**Gate:** Storyboard exists; durations sum to 15–25s.

---

## Step 3: Compose

**Read:** [references/step-3-compose.md](references/step-3-compose.md)

Full mode → Hyperframes. Slim mode → local tools.

If `--formats` lists multiple formats, compose once per format.

**Gate:** Composition validated.

---

## Step 4: Validate, render, deliver

**Read:** [references/step-4-deliver.md](references/step-4-deliver.md)

For each variant:
1. Render `flex.mp4`
2. Best settled frame → `flex.jpg` (bake as frame 0)
3. Write share copy files (see below)
4. If `--post-hook` is set, run the script with the output directory as argument

### Share copy (multi-platform)

Write three files (or one file with clear sections):
- `share-copy-x.txt` — short, punchy, X/Twitter style
- `share-copy-linkedin.txt` — slightly longer, professional
- `share-copy-instagram.txt` — caption + suggested hashtags

Also keep `share-copy.txt` as the primary/default caption.

### Batch mode

When `--batch` is used, repeat the full pipeline for each input. Put each result under `<output-dir>/<slug>/` where slug is derived from the URL or folder name.

### A/B tone testing

When `--ab tone1,tone2` is used, produce separate videos and plans per tone so the user can compare.

**Gate:** All requested variants have `flex.mp4` + poster + share copy. Nothing written into project source tree.

---

## Creative laws

- **Short.** 15–25 seconds.
- **Readable.** Hold text long enough to read.
- **Specific.** Made for this exact project.
- **Show the thing.** Real UI/copy, no abstract filler.
- **No generic SaaS language.**
- **Hook is everything.** First 2 seconds.
- **Funny earns its place.**
- **Pattern:** Hook → Reveal → 2–3 highlights → Punchline/outro
- **Stack rule.** Never assume language/framework. Never inject extra source files.
- **Language rule.** When voice is on, match the content language (auto-detect unless `--lang` overrides).
