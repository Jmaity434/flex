# Step 1: Inspect the project or website

Read the project directory or deeply scan the live website to understand what you're flexing about.

**Core principle:** This skill is completely stack-agnostic. Do not assume the project is written in JavaScript, TypeScript, Python, Go, or any other language. Do not assume React, Next.js, Vue, Svelte, Astro, or any other framework. Read only what is actually present. Never create extra source files, config files, or scaffolding inside the user's project.

## Project mode (current directory)

### What to look for (priority order)

1. **Main entry / page files** — whatever they are called and whatever extension they use (`index.html`, `page.tsx`, `App.vue`, `+page.svelte`, `main.go` templates, etc.). Extract: page title, hero headline, tagline, section headings, CTA text, testimonial copy, nav items.

2. **Styles** — CSS files, SCSS, Tailwind classes in markup, CSS-in-JS, styled-components, theme files, design tokens. Extract exact color palette, font families, background, accents.

3. **README / project description** — if present, extract project name and one-line description.

4. **Manifest files** (optional, only for name/description) — `package.json`, `cargo.toml`, `go.mod`, `pyproject.toml`, `composer.json`, etc. Do not assume any of them exist.

5. **Routes / screens / components** — if this is a multi-page or multi-screen app, scan the actual route or screen files that exist. Extract key feature names and screen descriptions.

6. **The user flow / happy path** — the strongest material is usually the product *in use*, not the marketing page. Identify the 2–3 beats: **entry → key action → result**.

7. **Assets** — note any images, logos, icons that can be referenced.

### What to skip

- Generated build artifacts (`dist/`, `.next/`, `build/`, `target/`, etc.)
- Lock files
- Test files
- `.git/`
- Environment and secret files (`.env*`, keys, credentials)
- Anything the project's `.gitignore` already excludes for security reasons

### Rule: nothing secret leaves this step

Never carry secrets, API keys, tokens, internal hostnames, real customer data, or personal data into the plan, composition, video, or share copy. Substitute plausible fictional stand-ins if the real UI contains such data, and note it in the plan.

## Website mode (URL given)

Get the site as a visitor sees it.

1. Attempt a normal fetch first.
2. If the result is mostly empty (common with JS-rendered sites), load the page in a headless browser.
3. Dismiss cookie banners, newsletter popups, and other overlays.
4. Scroll section by section so content that animates in on scroll is captured.
5. Extract:
   - Copy (headline, tagline, features, CTAs, testimonials, meta tags)
   - Exact colors and fonts from computed styles
   - Logo, hero images, product screenshots, demo videos
   - Layout screenshots at the target video aspect ratio
   - Product flow if visible (how-it-works, demo, docs links)

Prefer reusing real markup, CSS and assets in the video rather than only panning over flat screenshots.

## The planning rubric (answer all before moving on)

```
1. What is the app / site?
   One sentence. What does it actually do (or claim to do)?

2. What is the funniest or most impressive claim?
   The one line that earns a reaction.

3. What is the visual hook?
   Strongest color, UI element, diagram, or card.

4. What should be shown from the actual UI?
   Which section or screen is most video-worthy?

5. What is the shortest satisfying video?
   15s? 20s? Minimum to land the claim.

6. What tone fits best?
   Preset + short creative direction if needed.

7. What should the audio feel like?
   Music + SFX direction (unless disabled).

8. What should the share caption say?
   One strong sentence.

9. What's the user flow worth showing?
   entry → key action → result (or "none — landing-page only").
```

## Color and font extraction

Record exact values:
- Background color
- Primary text color
- Accent / brand color
- Any gradient or special treatment
- Display font (headings) and body font

These carry into the composition brief.
