# diegocampos.co — Quarto Academic Site

## Project structure

```
_quarto.yml          ← Site config: navbar, theme, output settings
index.qmd            ← Homepage (bio, research interests, news)
publications.qmd     ← Journal articles, book chapters, thesis
projects.qmd         ← Research projects & methodological expertise
presentations.qmd    ← Conference papers & invited talks
teaching.qmd         ← University courses & workshops
supervision.qmd      ← Master thesis supervision
grants.qmd           ← Awards, grants, scholarships
service.qmd          ← Editorial & reviewing service
styles.css           ← Custom CSS (colors, layout, typography)
assets/              ← Images (add profile.jpg here)
.github/workflows/
  publish.yml        ← GitHub Actions: auto-publish on push to main
```

## Setup

### Prerequisites

- [Quarto](https://quarto.org/docs/get-started/) ≥ 1.4
- R (only needed if you add R code chunks)

### Local preview

```bash
quarto preview
```

### Build site

```bash
quarto render
```

Output goes to `_site/`.

## Deployment to GitHub Pages

### Option A — GitHub Actions (recommended, automatic)

1. Push this project to a GitHub repository.
2. In the repo settings → **Pages**, set source to **GitHub Actions**.
3. Every push to `main` triggers `.github/workflows/publish.yml`, which renders and deploys automatically.

### Option B — Manual publish

```bash
quarto publish gh-pages
```

This renders the site and pushes `_site/` to the `gh-pages` branch. Run once to set up; after that, prefer the Actions workflow.

## Connecting your custom domain

1. In your GitHub repo → **Settings → Pages → Custom domain**, enter `diegocampos.co`.
2. At your DNS provider, add:
   - `A` records pointing to GitHub Pages IPs (185.199.108.153, .109, .110, .111)
   - Or a `CNAME` record: `www` → `<yourgithubusername>.github.io`
3. Enable "Enforce HTTPS" once DNS propagates.

## Adding your profile photo

Place your photo at `assets/images/profile.jpg`. It is referenced in `index.qmd`. Recommended size: 400×400 px, square crop.

## Updating content

Each section is a self-contained `.qmd` file — plain Markdown with a short YAML header. Edit any file and re-render. No special Quarto knowledge needed beyond basic Markdown.
