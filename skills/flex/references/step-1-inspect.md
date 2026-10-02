# Step 1: Inspect the project or website

Read the project directory or deeply scan the live website to understand what you're flexing about.

**Core principle:** Completely stack-agnostic. Do not assume any programming language or framework. Read only what is present. Never create extra source files inside the user's project.

## Project mode

Priority order:
1. Main entry / page files (any name/extension)
2. Styles (CSS, SCSS, Tailwind, CSS-in-JS, etc.)
3. README / project description
4. Manifest files only for name/description (do not assume they exist)
5. Routes / screens / components if present
6. User flow: entry → key action → result
7. Assets (logos, images)

Skip: build artifacts, lock files, tests, .git, secrets, anything gitignored for security.

## Website mode (URL)

1. Fetch; if empty shell, use headless browser
2. Dismiss overlays, scroll section-by-section
3. Extract copy, exact colors/fonts, logo, hero, UI, product flow
4. Prefer reusing real markup/CSS/assets over flat screenshots

## Language detection (for `--voice`)

When voice is enabled and `--lang` is `auto` (default):
- Detect the primary language of visible marketing/UI copy
- Set narration language to that language
- Do not force English
- If detection is uncertain, ask the user or default to the dominant script on the page

`--lang <code>` overrides auto detection.

## Brand kit

If `--brand path/to/brand.json` is set, load it (see `brand-kit.md`) and use provided logo/colors/fonts as overrides over extracted values.

## Planning rubric (answer all)

1. What is the app/site? (one sentence)
2. Funniest or most impressive claim?
3. Visual hook?
4. What actual UI should be shown?
5. Shortest satisfying duration?
6. Best tone (preset + direction)?
7. Audio feel?
8. Share caption?
9. User flow worth showing?
10. (If voice) Detected or requested narration language?

**Gate:** All relevant rubric questions answered.

## Color and font extraction

Record exact values: background, primary text, accent, gradients, display font, body font.

## Rule: nothing secret leaves this step

Never carry secrets, API keys, tokens, internal hostnames, or personal data into plan, composition, video, or share copy.
