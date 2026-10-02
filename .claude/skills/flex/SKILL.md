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

The user may invoke with natural language or flags:

```
/flex
/flex --tone chaotic
/flex --tone polished --format vertical
/flex this. Make it feel like a ridiculous startup launch.
/flex https://example.com
```

Parse these options:

| Option | Values | Default |
|---|---|---|
| `--tone` | preset or freeform description | inferred |
| `--format` | `landscape`, `vertical`, `square` | `landscape` |
| `--duration` | seconds | auto (15-25s) |
| `--no-music` | flag | music on |
| `--no-sfx` | flag | sfx on |
| `--title` | string | inferred from project |
| `--voice` | flag | narration off |

Tone can be a preset (`default`, `polished`, `yc-parody`, `chaotic`, `deadpan`, `cinematic`, `app-store`) or a creative direction such as "fake Series A launch from 2016".

## Output directory

By default, output goes to `flex-output/`. To avoid overwriting previous runs, use a timestamped directory when `flex-output/` already exists:

```
flex-output-2026-10-02-213000/
```

Generate the timestamp at the start of the run and use it consistently.

## Skill directory

`<skill-dir>` is the directory containing this `SKILL.md`. References live under `references/` relative to the canonical skill at `skills/flex/` in the repository. If references are not found locally, use the instructions embedded in this file and the planning rubric below.

---

## Step 1: Inspect the project or website

**Core principle:** Completely stack-agnostic. Do not assume JavaScript, TypeScript, Python, Go, React, Next.js, Vue, Svelte, or any other language/framework. Read only what is actually present. Never create extra source files inside the user's project.

### Project mode
1. Main entry / page files (any name/extension)
2. Styles (CSS, SCSS, Tailwind, CSS-in-JS, etc.)
3. README / project description
4. Manifest files only for name/description (package.json, cargo.toml, etc. — do not assume they exist)
5. Routes / screens / components if present
6. User flow: entry → key action → result
7. Assets (logos, images)

Skip: build artifacts, lock files, tests, .git, secrets, anything in .gitignore for security.

### Website mode (URL)
1. Fetch; if empty shell, use headless browser
2. Dismiss overlays, scroll section-by-section
3. Extract copy, exact colors/fonts, logo, hero, UI, product flow
4. Prefer reusing real markup/CSS/assets over flat screenshots

### Planning rubric (answer all)
1. What is the app/site? (one sentence)
2. Funniest or most impressive claim?
3. Visual hook?
4. What actual UI should be shown?
5. Shortest satisfying duration?
6. Best tone (preset + direction)?
7. Audio feel?
8. Share caption?
9. User flow worth showing?

**Gate:** All rubric questions answered.

---

## Step 2: Plan and storyboard

Write `<output-dir>/flex-plan.md` with: angle, hook, tone, visual identity (exact colors/fonts), beat-by-beat storyboard (duration, text, visual, transition, SFX), music direction, share caption draft.

Scene durations sum to 15–25 seconds. Use real project claims. Ban generic SaaS language.

**Gate:** flex-plan.md exists with full storyboard.

---

## Step 3: Compose

**Full mode:** Write composition brief → Hyperframes. Validate before render.

**Slim mode:** Build with tools on the machine. Prefer real UI/assets. Intermediate files only under `<output-dir>/work/`.

**Gate:** Composition ready and validated.

---

## Step 4: Validate, render, and deliver

1. Render `<output-dir>/flex.mp4`
2. Best settled frame → `<output-dir>/flex.jpg` (bake as frame 0)
3. Write `<output-dir>/share-copy.txt` (1–3 specific sentences, no "excited to share")
4. Tell user location + one-sentence angle + offer re-roll

**Gate:** flex.mp4 + poster + share-copy exist. Nothing written into project source tree.

---

## Tone system

| Tone | Energy |
|---|---|
| `default` | Playful, clean, postable |
| `polished` | Serious, elegant |
| `yc-parody` | Deadpan startup energy |
| `chaotic` | Fast, loud, aggressive |
| `deadpan` | Calm, dry, understated |
| `cinematic` | Dramatic, trailer-scale |
| `app-store` | Smooth, feature-card clean |

Freeform direction always allowed.

---

## Creative laws

- **Short.** 15–25s.
- **Readable.** Hold text long enough to read.
- **Specific.** Made for this exact project.
- **Show the thing.** Real UI/copy, no abstract filler.
- **No generic SaaS language.**
- **Hook is everything.** First 2 seconds.
- **Funny earns its place.**
- **Pattern:** Hook → Reveal → 2–3 highlights → Punchline/outro
- **Stack rule.** Never assume language/framework. Never inject extra source files.
