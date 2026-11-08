# CLAUDE.md

This file provides guidance for AI assistants working with this repository.

## Repository Overview

Personal landing page for [staniec.eu](https://staniec.eu), hosted via GitHub Pages with a custom domain. Plain static HTML — no build system, no frameworks. The blog lives at [pawel.staniec.eu](https://pawel.staniec.eu); this site's styling follows it.

## Repository Structure

```
staniec.eu/
├── CLAUDE.md                  # This file
├── CNAME                      # GitHub Pages custom domain (staniec.eu)
├── style.css                  # Shared stylesheet (all pages link to this)
├── index.html                 # Home — animated boot console
└── about.html                 # About page
```

## Tech Stack

- **Type:** Static HTML website
- **Hosting:** GitHub Pages
- **Domain:** staniec.eu (configured via CNAME)
- **CSS:** Single shared `style.css`, no preprocessor
- **JS:** Minimal inline only (current year in footer, command prompt on the home page)
- **No build system, frameworks, or dependencies**

## Development Workflow

1. Edit HTML/CSS files directly — no build step
2. Commit and push to `main`/`master` — GitHub Pages deploys automatically

## Key Conventions

- **No package manager** — do not add `package.json` or `node_modules`
- **No framework** — keep it plain HTML/CSS
- **CNAME must not be deleted** — always keep it containing `staniec.eu`
- **All pages link to `/style.css`** — keep styles in this single file
- **No external fonts or CDN dependencies** — use system font stack for fast loading
- **No tracking scripts** — keep it clean

## Boot Console

The home page animation is CSS only. Each line in `.console` uses class `a` and an inline `--t` (start time in seconds). Lines reserve their space, so nothing shifts while the log plays.

The final prompt accepts commands through the inline script in `index.html`. To add one, extend `routes` (for navigation) and the `help` text.

## Adding a New Page

Create a new `.html` file at the root (e.g., `projects.html` → `staniec.eu/projects`). Copy the header/footer structure from an existing page and add a nav link in all pages.

## CSS Notes

`style.css` is structured in order: reset → tokens → layout → header → theme toggle → terminal primitives → boot console → prose → footer → reduced motion. Colors are tokens on `:root`: dark by default (the pawel.staniec.eu palette), overridden automatically via `@media (prefers-color-scheme: light)`. Keep styles minimal.

The theme follows the system until a visitor chooses one, either with the header toggle or the `theme` command; the choice is stored in `localStorage` and applied by `data-theme` on `<html>`. New pages need the head script, the toggle button and the theme script from `about.html`.

## Git Branches

| Branch | Purpose |
|--------|---------|
| `main` / `master` | Production — deployed to staniec.eu |
| `claude/*` | AI-assisted feature branches |
