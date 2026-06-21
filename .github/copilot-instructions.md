# Copilot Instructions — cs-path

## What this repo is

A static Jekyll site deployed to `https://ionut-ml.github.io/cs-path/` via GitHub Actions. It is a **public-facing** CS self-study curriculum targeting working professionals. Content must remain generic — no personal references, watch history, tab counts, or "your X" framing.

## Build & deploy

```bash
# Local build (requires Ruby + Bundler)
bundle install
bundle exec jekyll serve --baseurl "/cs-path"
# Site available at http://localhost:4000/cs-path/

# Production build (matches CI)
bundle exec jekyll build --baseurl "/cs-path"
```

Deployment is automatic: push to `main` → GitHub Actions runs `.github/workflows/pages.yml` → site goes live. There is no test suite or linter.

## Architecture

```
_config.yml              Jekyll config — theme, baseurl, plugin list, exclude list
Gemfile                  just-the-docs ~> 0.10, github-pages
_includes/
  head_custom.html       Injected into <head>: early theme swap to avoid FOUC
  nav_footer_custom.html Injected into sidebar nav footer: dark mode toggle button
curriculum/
  index.md               Overview table + dependency map for all phases
  phase-0.md … phase-10.md, phase-s.md   One file per phase
plans/                   Study schedule pages (daily reading, weekend projects)
progress.md              Checkbox tracker (one section per phase)
index.md                 Home page
start-here.md            Entry point for new visitors
```

The theme is [Just the Docs v0.10](https://just-the-docs.com/) loaded via `remote_theme`. Jekyll builds two CSS files: `just-the-docs-default.css` (light) and `just-the-docs-dark.css` (dark).

## Front matter conventions

Every page needs these three fields:

```yaml
---
title: Phase N — Topic Name
parent: Curriculum        # omit on top-level pages
nav_order: N              # controls sidebar order
---
```

`nav_order` sequence for existing pages:

| nav_order | File |
|-----------|------|
| 1 | index.md |
| 2 | start-here.md |
| 3 | curriculum/index.md (has `has_children: true`) |
| 4–14 | phase-0 through phase-10, phase-s |
| 15 | plans/index.md (has `has_children: true`) |
| 20 | progress.md |

## Phase file structure

Each `curriculum/phase-N.md` follows this template:

```markdown
## Why This Phase?
(1–3 sentences: context and time estimate)

---

## 📱 Phone Reading
(Markdown table: Resource | Why | Link)

## 🏗 Weekend Project
(Hands-on build project with table of sub-tasks)

## 🎥 Key Videos
(Bullet list with markdown links)

---

## Done when...
(Single completion criterion in plain English)
```

Not every section is required for every phase, but this is the established pattern.

## Dark mode implementation

The theme toggle works by directly swapping the CSS `<link>` href — **not** via data attributes or `jtd.setTheme()`.

- `head_custom.html` runs before first paint; reads `localStorage.getItem('jtd-theme')` and sets the href
- `nav_footer_custom.html` defines `csToggleTheme(btn)` as a **global named function** called via `onclick` attribute (not `addEventListener`); this was required because addEventListener silently failed inside the nav element
- Theme name values are `'dark'` and `'default'` (not `'light'`)
- CSS href pattern: `/cs-path/assets/css/just-the-docs-{theme}.css`
- localStorage key: `'jtd-theme'`

## Key constraints

- `vendor/` must stay in `_config.yml` `exclude:` list — Jekyll will try to parse gem source files inside it and fail the build
- `TECH_NOTES.md` and `README.md` are also excluded from the build
- `baseurl` is `/cs-path` everywhere — hardcoded in the theme toggle JS as well
- The site is **public**: never add personal references, analysis results, file paths like `~/watch-later/`, or language like "your tabs" / "your watch list"
- Private analysis files live in `~/watch-later/` (never committed)
