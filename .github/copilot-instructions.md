# Copilot code review instructions

Context for reviewing pull requests in this repository.

## About this repo

Single-page static website for [amatama.net](https://amatama.net). The whole
site is `index.html` with inline CSS and an inline `tomachi` SVG, plus
`egg.png`. There is no build system, no package manager, and no test/lint
tooling.

## What to focus on in review

- **Self-containment**: flag anything that adds a build step, framework, or
  external CSS/JS/font dependency. The site is intentionally a single
  self-contained HTML file.
- **HTML/CSS correctness**: check that the hover interaction still works —
  `main:hover` fading `::before` (the egg) out and the SVG in. Watch for
  broken selectors, unclosed tags, or invalid CSS properties.
- **Asset references**: `egg.png` is referenced by relative path; verify such
  paths stay correct if files move.
- **Attribution**: the footer credit line (いらすとや egg image, Hiratake
  icon) must not be removed. Flag PRs that drop it.
- **Accessibility**: prefer keeping meaningful `lang`, `title`, and `alt`/SVG
  `<title>` attributes; note regressions.

## What NOT to flag

- Absence of tests, linters, or a build pipeline — that is by design.
- Inline CSS and inline SVG — intentional for this single-file site.
