# Using /flex with other AI coding agents

Agents like **Cursor**, **Aider**, or any LLM with custom instructions don't always have native `SKILL.md` discovery. Use one of these methods:

## Option 1: Paste into custom instructions

Open your agent's custom instructions or system prompt settings and paste the full contents of `skills/flex/SKILL.md`.

## Option 2: Reference as a file path

If your agent supports loading instructions from a file, point it at:

```
path/to/skills/flex/SKILL.md
```

## Option 3: Copy the skill folder

```bash
cp -r skills/flex/ ~/.your-agent/skills/flex/
```

## Google Antigravity

Antigravity natively discovers skills from:
- Project-level: `.agents/skills/flex/`
- Global: `~/.gemini/config/skills/flex/`

## Prerequisites

- Node.js 22+
- FFmpeg on PATH
- For full Hyperframes mode: `npx hyperframes doctor`
