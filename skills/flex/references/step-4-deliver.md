# Step 4: Validate, render, and deliver

## Per variant

1. Render the final video to `<output-dir>/flex.mp4`.
2. Pick the strongest *settled* frame (text fully visible, not mid-transition) and save it as `<output-dir>/flex.jpg`.
3. Bake that poster as frame 0 of `flex.mp4` so every platform shows a good thumbnail.
4. Write share copy (see below).
5. If `--post-hook` was set, run it with the output directory as the first argument. Report exit code; do not fail the whole skill if the hook fails.

## Share copy (multi-platform)

Write:

- `share-copy.txt` — primary caption (1–3 sentences, specific, matching tone). No "excited to share".
- `share-copy-x.txt` — short, punchy, X/Twitter style (can include a line break + link placeholder).
- `share-copy-linkedin.txt` — slightly longer, professional tone.
- `share-copy-instagram.txt` — caption + 3–8 relevant hashtags.

## Multiple formats (`--formats`)

If the user requested multiple formats, produce a subfolder per format and complete steps 1–4 in each.

## A/B tones (`--ab`)

Produce a subfolder per tone (e.g. `ab-default/`, `ab-yc-parody/`) each with its own plan, video, poster, and share copy.

## Batch (`--batch`)

For each input URL or path, produce a subfolder named after a short slug of that input.

## Final user message

Tell the user:
- Where the files are (list variants if more than one)
- One sentence on the creative angle(s)
- Offer to re-roll a scene, try another tone, or run `/flex doctor` if something failed

Nothing else is written into the user's project source tree.
