# Examples gallery

This folder holds demo projects and their flex outputs so visitors can see what `/flex` produces.

## Layout

```
examples/
  <slug>/
    index.html          # or link to the source site
    flex.mp4            # rendered video
    flex.jpg            # poster
    site.jpg            # optional thumbnail of the site
    notes.md            # optional: tone used, duration, notes
```

## Adding an example

1. Run `/flex` on a project or URL.
2. Copy `flex.mp4` and `flex.jpg` into `examples/<slug>/`.
3. Optionally add a short `notes.md` with tone and duration.
4. Link the example from the docs site (`docs/index.html`).

## Suggested starter examples

- A playful consumer app (`default` tone)
- A premium/polished product (`polished` tone)
- An absurd product (`yc-parody` tone)

Placeholders can be added until real renders are committed.
