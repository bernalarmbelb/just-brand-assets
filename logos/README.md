# The Just Brand — Email Logo Assets

Vector masters (`.svg`) plus raster exports for email use.

## Use in email
Email clients do **not** reliably render SVG (Gmail and Outlook both fail).
Always reference a **PNG** in email HTML. Use the `@2x` file and set the
displayed size to half, so it stays sharp on retina screens.

```html
<img src="https://cdn.jsdelivr.net/gh/USER/REPO@main/justbrand-seagull-white@2x.png"
     alt="The Just Brand" width="60" height="46"
     style="display:block;margin:0 auto 18px;border:0;">
```

## Files
| File | Size | Use |
|---|---|---|
| `justbrand-seagull-white.svg` | vector | master — white bird, transparent |
| `justbrand-seagull-white.png` | 60x46 | 1x |
| `justbrand-seagull-white@2x.png` | 120x92 | **email header (navy bg)** |
| `justbrand-seagull-white@3x.png` | 180x137 | 3x |
| `justbrand-seagull-navy.svg` | vector | master — navy bird, transparent |
| `justbrand-seagull-navy@2x.png` | 120x92 | light backgrounds |
| `justbrand-lockup-navy.svg` | vector | master — full circular lockup |
| `justbrand-lockup-navy@2x.png` | 160x160 | footer / light backgrounds |

Navy used: `#1A3A63`. Email header navy: `#1A2E44`.

> Note: these were reconstructed by vector-tracing JPEGs. If the original
> vector artwork is available, prefer it over these files.
