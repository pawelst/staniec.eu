# CLAUDE.md

This file provides guidance for AI assistants working with this repository.

## Repository Overview

Personal blog for [staniec.eu](https://staniec.eu), hosted via GitHub Pages with a custom domain. Plain static HTML — no build system, no frameworks.

## Repository Structure

```
staniec.eu/
├── CLAUDE.md                  # This file
├── CNAME                      # GitHub Pages custom domain (staniec.eu)
├── style.css                  # Shared stylesheet (all pages link to this)
├── index.html                 # Blog home — article list
├── about.html                 # About page
└── posts/
    └── hello-world.html       # Sample post (template for new posts)
```

## Tech Stack

- **Type:** Static HTML website
- **Hosting:** GitHub Pages
- **Domain:** staniec.eu (configured via CNAME)
- **CSS:** Single shared `style.css`, no preprocessor
- **JS:** Minimal inline only (current year in footer)
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

## Adding a New Post

1. Copy `posts/hello-world.html` to `posts/your-post-slug.html`
2. Update `<title>`, `<meta name="description">`, the `<time>` element, `<h1>`, and the prose content
3. Add an entry to the `<ul class="post-list">` in `index.html` (newest first)

Post list item template:
```html
<li>
  <time datetime="YYYY-MM-DD">Month DD, YYYY</time>
  <a href="/posts/your-post-slug.html" class="post-title">Post Title</a>
  <p class="post-excerpt">One or two sentence excerpt.</p>
</li>
```

## Adding a New Page

Create a new `.html` file at the root (e.g., `projects.html` → `staniec.eu/projects`). Copy the header/footer structure from an existing page and add a nav link in all pages.

## CSS Notes

`style.css` is structured in order: reset → layout → header → post list → prose → footer → dark mode. Dark mode is automatic via `@media (prefers-color-scheme: dark)`. Keep styles minimal.

## Git Branches

| Branch | Purpose |
|--------|---------|
| `main` / `master` | Production — deployed to staniec.eu |
| `claude/*` | AI-assisted feature branches |
