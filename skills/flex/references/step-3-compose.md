# Step 3: Compose

## Full mode (Hyperframes)

Write a focused composition brief that contains:
- Product angle and storyboard
- Exact visual identity (colors, fonts)
- Tone and pacing notes
- Audio selection / cue guidance
- Format and duration

Hand the brief to Hyperframes. `/flex` owns the story and creative direction; Hyperframes owns concrete timing, animation mechanics, and render workflow.

Validate with `npx hyperframes check` (or equivalent) before render.

## Slim mode

Build the video yourself with the tools available on the machine. Prefer reusing real UI, markup, styles and assets from the source when possible.

Make every frame a pure function of time if rendering from a browser. Check stills from every scene and mid-transition before the full render.

All intermediate files stay inside `<output-dir>/work/`.
