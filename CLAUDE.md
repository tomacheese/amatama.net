# CLAUDE.md

## Overview

Source code for [amatama.net](https://amatama.net), a single-page static
website. It shows an egg image; on hover the egg fades out and a `tomachi`
icon (inline SVG) is revealed with a slide animation.

## Structure

- `index.html` — the entire site. HTML, CSS (in a `<style>` block), and the
  `tomachi` SVG are all inline in this one file. There is no build step and no
  external CSS/JS.
- `egg.png` — the egg image referenced as a CSS background in `index.html`.
- `README.md` — project description and asset credits.

## Development

There is no build, test, lint, or package manager (no `package.json`). To
verify a change, open `index.html` directly in a browser and confirm the
hover transition (egg fades out, SVG fades in and slides down).

## Conventions

- Keep everything self-contained in `index.html` (inline CSS/SVG). Do not
  introduce a build toolchain, framework, or external asset dependencies
  unless the scope of the site changes.
- `index.html` declares `lang="ja"`; user-facing text is Japanese.

## Attribution

The egg illustration (いらすとや) and the icon SVG (Hiratake) are
third-party assets. Keep the credit line in the page footer and in
`README.md` intact when editing.

## Documentation

When the file layout or the hover behavior changes, update both `README.md`
and this file so the description stays accurate.
