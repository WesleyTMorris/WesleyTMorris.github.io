# CLAUDE.md — Instructions for Working on This Site

## About the Site Owner

Wesley T. Morris is an education policy researcher and Postdoctoral Research Fellow at the University of Maryland, College Park. His research focuses on:
- Early career teacher pipelines
- Teacher labor markets
- Market-based reforms in education (particularly how well-intentioned reforms create unintended consequences)
- Rural schools
- Bridging research, policy, and practice

Contact: wtmorris@umd.edu | [Google Scholar](https://scholar.google.com/citations?user=ktYcC8MAAAAJ)

---

## Site Overview

- **Framework:** [Quarto](https://quarto.org/) website
- **Hosting:** GitHub Pages at `WesleyTMorris.github.io`
- **Theme:** Lux (Bootstrap), with `styles.css` for custom CSS
- **Output directory:** `docs/` (rendered locally, pushed to GitHub)
- **Analytics:** Google Analytics (`G-4S82ZPX7QZ`)

---

## File Structure

```
/
├── CLAUDE.md                        # This file
├── _quarto.yml                      # Site config, navbar, theme, render list
├── index.qmd                        # Homepage / About Me (Trestles template)
├── research.qmd                     # Research page with auto-generated listings
├── cv.qmd                           # CV page (embeds Morris_CV.pdf)
├── research_statement.qmd           # Embeds Research_Statement.pdf
├── teaching_statement.qmd           # Embeds Teaching_Statement.pdf
├── S&A.qmd                          # Service & Awards page
├── Morris_CV.pdf                    # Current CV (PDF)
├── Research_Statement.pdf           # Research statement (PDF)
├── Teaching_Statement.pdf           # Teaching statement (PDF)
├── headshot.png                     # Profile photo
├── CNAME                            # GitHub Pages custom domain config
├── _extensions/                     # Quarto extensions
├── docs/                            # Rendered output — DO NOT edit directly
└── publications/
    ├── journal_articles/            # One .qmd per journal article or working paper
    │   ├── TEACH_landing_page.qmd
    │   ├── Online_Education_landing_page.qmd
    │   └── Teacher_Satisfaction_landing_page.qmd
    └── briefs/                      # One .qmd per policy brief or general-audience piece
        ├── mentors_matter_landing_page.qmd
        ├── TN_Eval_Satisfaction_landing_page.qmd
        └── online_ed_brief_landing_page.qmd
```

---

## Publication Landing Page Format

Each publication has its own `.qmd` file. The YAML frontmatter follows this pattern:

```yaml
---
date: "Month DD YYYY"
date-format: "MMMM YYYY"
title: "Full Publication Title"
categories: "Journal Article"   # or "Working Paper", "Research Brief", etc.
author: "Wesley T. Morris"      # full author list if co-authored
image: image_file.png
resources: image_file.png
about:
  template: solana
  image-shape: rounded
  links:
    - icon: file-text
      text: Full Text
      href: https://link-to-paper
---
```

The body typically contains `## Abstract` (or `## Summary` for briefs) and `## Citation`.

The `research.qmd` page auto-lists publications by globbing `publications/journal_articles/*_landing_page.qmd` and `publications/briefs/*_landing_page.qmd` — so new files added with the naming convention `*_landing_page.qmd` will appear automatically after rendering.

---

## Navbar Structure

```
About Me (dropdown)
  └── Service & Awards  →  S&A.qmd
CV                       →  cv.qmd
Research                 →  research.qmd
```

Pages not in the navbar (but rendered): `research_statement.qmd`, `teaching_statement.qmd`, and all publication landing pages.

---

## Workflow

1. Edit `.qmd` files or `_quarto.yml` / `styles.css`
2. Run `quarto render` from the project root to build into `docs/`
3. Commit and push to GitHub — GitHub Pages serves from `docs/`

**Never edit files inside `docs/` directly** — they are overwritten on every render.

---

## Goals for Working Together

1. **Improve visual design and layout** — make the site look more polished and professional
2. **Add new publications** — create landing page `.qmd` files for new work
3. **Keep the site consistent** — changes should match the existing Quarto/Lux aesthetic

---

## Rules & Constraints

- All source files are `.qmd` (Quarto Markdown) — do not convert them to plain `.md` or `.html`
- Do not delete or move any existing files without asking first
- Do not edit anything inside `docs/` — it is auto-generated
- If a new publication page is added, also add it to the `render:` list in `_quarto.yml`
- Keep changes compatible with `quarto render` — test mentally before suggesting changes
- The theme is **Lux** (Bootstrap). Custom styles go in `styles.css`
- When suggesting design improvements, prefer CSS/SCSS changes over structural rewrites
