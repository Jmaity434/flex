# Assets (optional)

Place royalty-free music and SFX here for full-mode compositions.

## Suggested layout

```
assets/
  music/
    happy-beats.mp3
    calm-bed.mp3
  sfx/
    whoosh.wav
    click.wav
    logo-hit.wav
```

## Rules

- Only include assets you have rights to distribute.
- Slim mode does not require these files; the model can use whatever is available on the machine.
- Reference tracks by relative path from the skill directory when writing composition briefs.

Until real files are added, compositions should still work by using system-available audio or silent beds when `--no-music` is set.
