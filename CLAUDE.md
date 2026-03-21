# CLAUDE.md

This file provides guidance for AI assistants working with this repository.

## Repository Overview

This is a minimal static website for [staniec.eu](https://staniec.eu), hosted via GitHub Pages with a custom domain.

## Repository Structure

```
staniec.eu/
├── CLAUDE.md       # This file
├── CNAME           # GitHub Pages custom domain configuration (staniec.eu)
└── index.html      # Main landing page
```

## Tech Stack

- **Type:** Static HTML website
- **Hosting:** GitHub Pages
- **Domain:** staniec.eu (configured via CNAME)
- **No build system, frameworks, or dependencies**

## Development Workflow

Since this is a plain static site with no build system:

1. Edit HTML/CSS/JS files directly
2. Commit and push changes to `main`/`master` — GitHub Pages deploys automatically

There are no install steps, build commands, or test suites.

## Key Conventions

- **No package manager** — do not add `package.json` or `node_modules` unless intentionally adopting a build system
- **No framework** — keep it plain HTML unless there is an explicit reason to add one
- **CNAME must not be deleted** — removing `CNAME` disables the custom domain; always keep it pointing to `staniec.eu`
- **Deployment branch:** GitHub Pages serves from `main` (or `master`); feature branches are not deployed

## Git Branches

| Branch | Purpose |
|--------|---------|
| `main` / `master` | Production — deployed to staniec.eu |
| `claude/*` | AI-assisted feature branches |

## Common Tasks

### Update the landing page
Edit `index.html` directly. No build step is required.

### Add a new page
Create a new `.html` file at the desired path (e.g., `about.html` → `staniec.eu/about`).

### Preserve the custom domain
The `CNAME` file must always contain exactly:
```
staniec.eu
```
