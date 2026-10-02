# Marketplace & discovery

## Install channels

| Channel | Command / action |
|---|---|
| skills CLI | `npx skills add https://github.com/Jmaity434/flex --skill flex` |
| Claude Code plugin | `/plugin marketplace add Jmaity434/flex` then `/plugin install flex@flex` |
| Codex | `codex plugin marketplace add Jmaity434/flex` then `codex plugin add flex@flex` |
| Manual | Copy `skills/flex/` into the agent's skills directory |

## skills.sh / public registries

To list on public skill registries that accept GitHub URLs:

1. Ensure `skills/flex/SKILL.md` has clear `name` and `description` frontmatter (done).
2. Keep the repo public.
3. Submit the repo URL to the registry's submission form or CLI if available.
4. Prefer the canonical path `https://github.com/Jmaity434/flex` with skill id `flex`.

## Versioning

Bump `version` in `plugin.json`, `.claude-plugin/plugin.json`, and `.codex-plugin/plugin.json` together with `CHANGELOG.md` on each release.
