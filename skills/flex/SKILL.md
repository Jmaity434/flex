---
name: flex
description: Turn the current project or a website into a short, polished, shareable launch video. Use when someone says "/flex", "let's flex", "make a launch video", "turn this into a video", or wants to show off what they built. Stack-agnostic — works with any framework or plain HTML. Reads the project code or deeply scans a live URL. Does not create unnecessary files in the project.
---

# /flex

You built it. Now let's flex.

## Invocation dispatch (must happen first)

**Model check.** If you are Claude Opus 5.5 (or a model that prefers building the video itself) and the invocation does not ask for the full workflow (`--full`, "use the full flex") or for voiceover (`--voice`), switch to the slim path: read `<skill-dir>/slim.md` and follow it for the rest of this run. Pass along the user's input and any other options as plain-language direction. Tell the user in one line first. If you are any other model, or can't tell, continue with this file.

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

`<skill-dir>` is the directory containing this `SKILL.md`. Bundled assets (if any) are under `<skill-dir>/assets/` and scripts under `<skill-dir>/scripts/`.

---

## Step 1: Inspect the project or website

**Read:** [references/step-1-inspect.md](references/step-1-inspect.md)

This is the most important step. Be thorough. The skill must work regardless of the programming language or framework used to build the site.

**Gate:** You can answer all the planning rubric questions.

---

## Step 2: Plan and storyboard

**Read:** [references/step-2-plan.md](references/step-2-plan.md)

Write `<output-dir>/flex-plan.md`. Answer the planning rubric. Commit to a creative angle. Write the beat-by-beat storyboard including scenes, text, timing, transitions, and SFX cues.

**Gate:** `<output-dir>/flex-plan.md` exists with a full storyboard. Scene durations sum to 15–25 seconds.

---

## Step 3: Compose

**Read:** [references/step-3-compose.md](references/step-3-compose.md)

Write the composition brief and create the video implementation in `<output-dir>/composition/` (full mode) or build it directly with available tools (slim mode).

**Gate:** Composition is ready and validated.

---

## Step 4: Validate, render, and deliver

**Read:** [references/step-4-deliver.md](references/step-4-deliver.md)

Render to `<output-dir>/flex.mp4`, pick the best poster frame into `<output-dir>/flex.jpg`, bake that poster as frame 0, and write `<output-dir>/share-copy.txt`.

**Gate:** `<output-dir>/flex.mp4` exists. Poster is baked. Share copy is written.

---

## Tone system

| Tone | Energy | One-liner |
|---|---|---|
| `default` | Playful, clean, postable | The good-vibes default |
| `polished` | Serious, elegant | For projects that are not jokes |
| `yc-parody` | Deadpan startup energy | Fake seriousness applied to absurd projects |
| `chaotic` | Fast, loud, aggressive | Over-the-top and unhinged |
| `deadpan` | Calm, dry, understated | The joke is that nothing is a joke |
| `cinematic` | Dramatic, trailer-scale | Big motion, bigger claims |
| `app-store` | Smooth, feature-card clean | Corporate but not boring |

Always allow freeform creative direction to refine or override the preset.

---

## Creative laws

These apply to every flex video regardless of tone.

**Short.** 15–25 seconds. Not one second more without a reason.

**Readable.** Keep the pace high through motion and cuts, never by flashing text. Every line a viewer must read holds long enough to read it.

**Specific.** The video must feel like it was made for this exact project, not any project.

**Show the thing.** At least one scene must display actual UI, copy, or a key visual from the product. No abstract filler.

**No generic SaaS language.** "Streamline your workflow" is banned. Use the project's actual copy and claims.

**The hook is everything.** The first 2 seconds determine whether someone keeps watching.

**Funny earns its place.** Humor should come from the project's absurdity, not from trying to be funny.

**Pattern:**
```
Hook (2-3s) → Reveal (2-4s) → 2-3 sharp highlights (5-12s) → Punchline/outro (2-4s)
```

Adapt this. The pattern is a starting shape, not a template.

**Stack rule.** Never assume the project is written in a specific language or framework. Read what is actually there. Never inject extra source files into the project.
