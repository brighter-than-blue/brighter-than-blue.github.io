# brighter-than-blue.github.io

The Brighter than Blue website — a single static page hosted on GitHub Pages, live at
<https://brighterthanblue.com>.

## Structure

- `index.html` — the whole site: logo lockup and a contact section.
- `assets/css/styles.css` + `assets/css/tokens/` — a vendored copy of the Brighter than Blue
  design system tokens (colours, type, spacing, elevation, motion, base reset), synced from the
  Brighter than Blue design system project.
- `assets/css/site.css` — page layout, built from those tokens only. The classes mirror the
  system's `Page`, `PageHeader`, `PageBody` and `Button` components.
- `assets/logo/` — the `b` mark in full colour, mono and reverse, plus a 240px PNG for
  `apple-touch-icon`.
- `.nojekyll` — files are served as-is, with no Jekyll build.
- `CNAME` — the custom domain. Do not delete it: removing the file un-sets the custom domain on
  the next build, and the site drops back to `brighter-than-blue.github.io`.

## Local preview

```
python3 -m http.server 8000
```

Then open <http://localhost:8000>.

## Publishing

GitHub Pages serves `main` from the repository root. Pushing to `main` publishes the site.

## Domain and DNS

The domain is registered with IONOS, and its DNS is hosted there. The web records point at
GitHub Pages:

| Type | Host | Value |
| --- | --- | --- |
| A | `@` | `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153` |
| AAAA | `@` | `2606:50c0:8000::153`, `2606:50c0:8001::153`, `2606:50c0:8002::153`, `2606:50c0:8003::153` |
| CNAME | `www` | `brighter-than-blue.github.io` |

`www` and `brighter-than-blue.github.io` both redirect to the apex. HTTPS is enforced, on a
Let's Encrypt certificate GitHub issues and renews for the apex and `www`.

**The MX and SPF records are separate and must stay with IONOS.** They route
`info@brighterthanblue.com`, the address the site publishes, and have nothing to do with the web
records above. Changing the A or AAAA records does not affect mail; deleting the MX records
does.
