---
name: flex
description: Turn the current project or a website into a short, polished, shareable launch video. Use when someone says "/flex", "let's flex", "make a launch video", "turn this into a video", or wants to show off what they built. Stack-agnostic — works with any framework or plain HTML. Reads the project code or deeply scans a live URL. Does not create unnecessary files in the project.
---

# /flex

You built it. Now let's flex.

## Invocation dispatch (must happen first)

**Model check.** If you are Claude Opus 5.5 (or a model that prefers building the video itself) and the invocation does not ask for the full workflow (`--full`, "use the full flex") or for voiceover (`--voice`), switch to the slim path: read the `slim.md` file that lives next to this SKILL.md (or under `skills/flex/slim.md` in the repo) and follow it for the rest of this run. Pass along the user's input and any other options as plain-language direction. Tell the user in one line first. If you are any other model, or can't tell, continue with this file.

Before inspecting the project, parse the complete `/flex` invocation. If the invocation contains `--voice`, set `voice.enabled = true`. Enable narration only for that run.

`/flex` turns the current project website/app or a given URL into a short, polished, shareable launch video. It is narrow, opinionated, and fun. It is completely stack-agnostic.

## What this skill does

1. Inspects the project (or deeply scans a live website) to understand the product — without assuming any specific programming language or framework.
2. Plans a short flex concept specific to this project.
3. Scripts and storyboards the video.
4. Hands a focused composition brief to Hyperframes (full mode) or builds the video with available tools (slim mode).
5. Validates, renders, and writes share copy.

**Hard rule:** Never create extra source files, config files, or framework scaffolding inside the user's project. All output lives only in `flex-output/` (or a timestamped `flex-output-YYYY-MM-DD-HHmmss/`).

## Parsing the invocation

Parse options: `--tone`, `--format` (landscape/vertical/square), `--duration`, `--no-music`, `--no-sfx`, `--title`, `--voice`.

## Output directory

`flex-output/` or timestamped `flex-output-YYYY-MM-DD-HHmmss/`.

## Steps (summary)

1. **Inspect** — stack-agnostic. Project code or deep website scan (headless + scroll). Answer the 9-question rubric.
2. **Plan** — write flex-plan.md with angle, hook, storyboard (15-25s), visual identity, share caption.
3. **Compose** — Hyperframes (full) or build with local tools (slim). Intermediate files only in output/work/.
4. **Deliver** — flex.mp4 + flex.jpg (baked as frame 0) + share-copy.txt. Nothing written into project source.

## Creative laws

Short. Readable. Specific. Show the real thing. No generic SaaS language. Hook first. Stack-agnostic. Never inject extra source files.
