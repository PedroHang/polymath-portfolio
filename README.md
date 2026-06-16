# Polymath AI Studio — Website

Landing site for Polymath AI Studio. Pure static HTML/CSS/JS — no build step, no
framework, no runtime dependencies. Loads instantly and deploys anywhere.

## Structure

```
index.html                      # The live site (self-contained: HTML + inline CSS + vanilla JS)
assets/                         # Logo marks used by the site
  mark-ink.png                  #   dark mark (nav, favicon)
  mark-cream.png                #   light mark (cards, footer)
  mark-olive.png
  logo-src.png
Polymath AI Studio.dc.html      # Original Claude Design export (source of truth)
support.js                      # Claude Design runtime (only used by the .dc.html export)
uploads/                        # Original uploaded logo
```

`index.html` is the production page. The `.dc.html` + `support.js` are kept only as
the original design source — they are **not** what gets served.

## Run locally

Any static server works:

```bash
python -m http.server 8000
# then open http://localhost:8000
```

## Deploy

Static — drop it on any static host.

**Vercel (recommended):**
1. Push this repo to GitHub.
2. Import the repo at [vercel.com](https://vercel.com) → Deploy (no settings needed).
3. Add a custom domain under Project → Settings → Domains.

No framework preset, build command, or output directory required — Vercel serves
`index.html` directly.

## Editing content

Real content replaces the `[ ... ]` placeholders directly in `index.html`:

- **Projects** — the three `.proj-card` blocks under `<section id="work">`.
- **Clients / testimonials** — under `<section id="clients">`.
- **Services** — the four `.svc-card` blocks under `<section id="services">`.

Links to update (search `index.html`):

- Calendly: `https://calendly.com/hangpedroo/30min`
- Instagram / LinkedIn: currently placeholder root URLs.

Brand colors live in one place — the `:root` block at the top:

```css
:root { --accent: #556B2F; --accent2: #B25E3F; }
```
