# Flex doctor

When the user runs `/flex doctor` or a required tool is missing, print a clear check:

```
Flex doctor
-----------
Node.js 22+     OK / FAIL  (found: …)
FFmpeg          OK / FAIL  (found: …)
Hyperframes     OK / SKIP / FAIL  (only required for full mode)
Write access    OK / FAIL
```

## How to check

- Node: `node -v` — major version >= 22
- FFmpeg: `ffmpeg -version`
- Hyperframes: `npx hyperframes doctor` (or note that slim mode does not need it)
- Write access: try creating a temp file in the current directory and delete it

## On failure

Tell the user exactly what to install and the minimal command. Do not continue to render if Node or FFmpeg is missing.
