---
name: flex-slim
description: Turn a project directory or a website URL into a short, shareable launch video with music, motion, and share copy. Built entirely by the model with tools on the machine. Stack-agnostic. Supports multi-format, A/B tones, brand kit, batch, voice lang auto-detect, and post-hooks.
---

# /flex-slim

You built it. Now flex. You make the whole video yourself — story, visuals, audio, render — with whatever tools are on the machine.

**Status messages (required):** `Flex starting — inspecting…` → `Planning…` → `Building…` → `Rendering…` → `Done.`

**Hard rule:** Never create extra source files inside the user's project. All output under `flex-output/` (or timestamped variant) only.

## Options

| Option | Default |
|---|---|
| `--tone` | inferred |
| `--format` | landscape (or vertical if `--vertical-first`) |
| `--formats` | single format; e.g. `landscape,vertical` |
| `--duration` | ~20s |
| `--voice` | off |
| `--lang` | `auto` when voice on |
| `--brand` | none |
| `--batch` | single input |
| `--ab` | single tone |
| `--post-hook` | none |
| `--vertical-first` | off |

If user runs doctor: check Node 22+, FFmpeg, write access; print pass/fail table.

## 1. Inspect

| Input | Source |
|---|---|
| Project | Code — whatever language/framework is present |
| Website | Live deep scan (headless, dismiss overlays, scroll sections) |

Stack-agnostic. Detect content language for voice (`--lang auto`). Apply `--brand` kit if provided.

Answer: what it is, who for, differentiator, strongest claim, visual hook, real UI, tone, share caption.

## 2. Plan

Write `flex-plan.md` (15–25s storyboard). If `--ab`, one plan per tone. If `--formats`, note each format.

## 3. Build & render

Build with tools on the machine. Prefer real UI/assets. Intermediate files in `work/`.

Per variant: `flex.mp4` + `flex.jpg` (bake frame 0).

## 4. Deliver

- `share-copy.txt` + `share-copy-x.txt` + `share-copy-linkedin.txt` + `share-copy-instagram.txt`
- Run `--post-hook <outdir>` if set
- Batch → subfolder per input; A/B → subfolder per tone; formats → subfolder per format

Tell user paths + one-sentence angle + offer re-roll.

## Creative laws

Short. Clear to a stranger. Hook first. Show the real thing. Specific. Readable. Alive motion. Funny only when earned. Stack-agnostic. No extra source files. Voice matches content language when enabled.
