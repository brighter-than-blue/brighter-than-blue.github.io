# brighter-than-blue.github.io

The Brighter than Blue website — a single static page hosted on GitHub Pages.

## Structure

- `index.html` — the whole site: logo lockup and a contact section.
- `assets/css/styles.css` + `assets/css/tokens/` — a vendored copy of the Brighter than Blue
  design system tokens (colours, type, spacing, elevation, motion, base reset), synced from the
  design system project `b16cae8f-0185-4662-ac4f-c8114e24f192`.
- `assets/css/site.css` — page layout, built from those tokens only. The classes mirror the
  system's `Page`, `PageHeader`, `PageBody` and `Button` components.
- `assets/logo/` — the `b` mark in full colour, mono and reverse, plus a 240px PNG for
  `apple-touch-icon`.
- `.nojekyll` — files are served as-is, with no Jekyll build.

## Local preview

```
python3 -m http.server 8000
```

Then open <http://localhost:8000>.

## Publishing

GitHub Pages serves `main` from the repository root. Pushing to `main` publishes the site.
