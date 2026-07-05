# LaneyLabs Website

Single-page static site for LaneyLabs, Inc. Plain HTML/CSS, no build step, no dependencies.

## Preview locally

Open `index.html` directly in a browser, or serve it:

```bash
python3 -m http.server 8000
```

Then visit `http://localhost:8000`.

## Deploy

Hosted on GitHub Pages from the `main` branch root of this repo. Live at:

https://mrklaney.github.io/laneylabs

To publish changes, commit and push to `main` — GitHub Pages redeploys automatically within a minute or two.

## Editing content

All content lives directly in `index.html` (no templating). Styling is in `styles.css`. See `docs/superpowers/specs/2026-07-05-laneylabs-website-design.md` for the design spec.
