# Post-render hooks

Optional. Pass `--post-hook path/to/script`.

After a successful render (all variants done), run:

```bash
<path-to-script> <output-dir>
```

## Expected behavior of the hook

- Receives the output directory as the first argument
- Can upload, post, notify, or copy files
- Should exit 0 on success
- Flex should report the exit code to the user but not crash the skill if the hook fails

## Example use cases

- Copy `flex.mp4` to a known folder
- Call a small script that posts to X/LinkedIn via API
- Trigger a Slack/Discord webhook

Do not embed API keys in the skill. The hook script is the user's responsibility.
