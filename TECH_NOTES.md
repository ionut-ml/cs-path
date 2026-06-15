# 🛠 Tech Notes — How This Site Works

> Written for someone who doesn't know web dev yet.  
> Read this once. You won't need to touch most of this again.

---

## The Big Picture

You write **Markdown files** (`.md`) — the same format used in this project.  
GitHub converts them into a real website automatically.  
You never write HTML, CSS, or JavaScript unless you want to.

```
You write:  page.md  →  GitHub builds it  →  ionut-ml.github.io/cs-path/page
```

---

## Technology Stack (in plain English)

### Git
**What it is:** A tool that tracks changes to files — like "track changes" in Word but for code.  
**Why we use it:** It's how we send files from your laptop to GitHub.  
**Commands you'll use:**
```bash
git add .              # stage all changed files
git commit -m "note"   # save a snapshot with a message
git push               # send to GitHub (triggers the website rebuild)
```

---

### GitHub
**What it is:** A website that hosts Git repositories (folders of files with history).  
**Why we use it:** Free hosting, free CI/CD, free Pages. Industry standard.  
**Your repo will live at:** `github.com/ionut-ml/cs-path`

---

### GitHub Pages
**What it is:** A free feature of GitHub that turns a repo into a public website.  
**How it works:** Every time you `git push`, GitHub automatically rebuilds the site.  
**Your site will be at:** `ionut-ml.github.io/cs-path`  
**Cost:** Free for public repos. Always.

---

### Jekyll
**What it is:** A static site generator — a program that converts Markdown files into HTML pages.  
**Why we use it:** GitHub Pages has built-in support for it. No server needed.  
**You don't run it yourself** — GitHub runs it for you when you push.  
**Config file:** `_config.yml` (the settings file for the whole site)

---

### Just the Docs (Jekyll Theme)
**What it is:** A pre-built visual design ("theme") for Jekyll documentation sites.  
**Why we chose it:** Looks professional, has sidebar navigation and search, free, requires zero design knowledge.  
**What it gives you:**
- Left sidebar with all pages listed
- Search bar at the top
- Clean readable typography
- Mobile-friendly layout

**You never edit the theme files** — it's applied automatically via `_config.yml`:
```yaml
remote_theme: just-the-docs/just-the-docs@v0.10.0
```

---

### Gemfile
**What it is:** A list of Ruby packages ("gems") that Jekyll needs to build the site.  
**Ruby** is a programming language. Jekyll is written in Ruby.  
**You don't need to know Ruby** — the Gemfile just tells GitHub which packages to install.  
**Think of it like** `requirements.txt` in Python.

```ruby
gem "just-the-docs"     # the theme
gem "github-pages"      # GitHub's own Jekyll package bundle
gem "jekyll-seo-tag"    # auto-generates SEO meta tags (good for Google)
gem "jekyll-remote-theme"  # allows using themes hosted on GitHub
```

**You never need to edit the Gemfile** unless you want to add a new plugin.

---

### GitHub Actions (`.github/workflows/pages.yml`)
**What it is:** Automated tasks that run every time you push to GitHub.  
**What our workflow does:**
1. Installs Ruby + Jekyll on a GitHub server
2. Runs Jekyll to build the site from your Markdown files
3. Deploys the result to GitHub Pages

**You never trigger this manually** — it runs automatically on every `git push`.

---

### Front Matter (the `---` block at the top of each `.md` file)
**What it is:** Metadata for a page — tells Jekyll how to display it.  
**Example:**
```yaml
---
title: Phase 1 — Computer Architecture
parent: Curriculum
nav_order: 1
---
```
- `title` — what shows in the browser tab and sidebar
- `parent` — which section it belongs to (creates nested navigation)
- `nav_order` — its position in the sidebar (lower number = higher up)

**You'll add this to the top of every page you create.** That's all you need to know.

---

## File Structure Explained

```
cs-path-site/
├── _config.yml          ← Site-wide settings (title, theme, URL)
├── Gemfile              ← Ruby package list (don't touch)
├── index.md             ← Your home page
├── start-here.md        ← Ground zero — first steps
├── progress.md          ← Your progress tracker (checkboxes)
├── curriculum/
│   ├── index.md         ← Curriculum overview page
│   ├── phase-1.md       ← Phase 1: Architecture
│   ├── phase-2.md       ← Phase 2: Systems/C
│   └── ...
├── plans/
│   ├── daily-reading.md ← 30-min phone sessions
│   └── weekend-projects.md ← Weekend build projects
└── .github/
    └── workflows/
        └── pages.yml    ← The automation script (don't touch)
```

---

## How to Add or Update a Page

1. Open the `.md` file in any text editor (or directly on github.com)
2. Edit the Markdown content
3. Save, then run:
```bash
cd ~/cs-path-site
git add .
git commit -m "update phase 2 notes"
git push
```
4. Wait ~60 seconds → visit `ionut-ml.github.io/cs-path` → it's live.

---

## How to Update Your Progress

Open `progress.md` and change `- [ ]` to `- [x]`:
```markdown
- [x] Read cpu.land Level 1    ← done
- [ ] Read cpu.land Level 2    ← not yet
```
Then `git push`. That's it.

---

## Things You Will NEVER Need to Do
- Write HTML or CSS
- Configure a server
- Manage deployments
- Pay for hosting
- Install Ruby locally (GitHub handles it)

---

*This file is for your reference. It will not appear on the website (it's excluded in `_config.yml`).*
