# Brand kit

Optional. Pass `--brand path/to/brand.json` to override visual identity.

## Expected JSON shape

```json
{
  "name": "Acme",
  "logo": "./assets/logo.svg",
  "colors": {
    "background": "#0a0a0a",
    "primary": "#f5f5f5",
    "accent": "#d4af37"
  },
  "fonts": {
    "display": "Inter",
    "body": "Inter"
  }
}
```

## Rules

- If a field is missing, fall back to values extracted from the project/site.
- Logo path is relative to the brand file or absolute.
- Colors should be used consistently in the composition.
- Do not invent brand assets. Only use what is provided or extracted.
