# oskar-slowik.github.io

Personal site of Oskar Słowik. Built with [Quarto](https://quarto.org), deployed to GitHub Pages.

## Quick start

### One-time setup

1. **Create the GitHub repo.**
   Name it `Feigenbaum4669.github.io` so it serves from the root URL.
   Make it public (private repos need GitHub Pro to use Pages).

2. **Replace placeholders.** Open `_quarto.yml` and `index.qmd` and search for:
   - `Feigenbaum4669` — your GitHub username
   - `YOUR-LINKEDIN` — your LinkedIn vanity slug
   Then update the email, Scholar ID, etc. if needed.

3. **Add your photo.** Drop a square image at `assets/profile.jpg`. See `assets/README.md`.

4. **Initialise Git and push.**
   ```bash
   git init -b main
   git add .
   git commit -m "Initial site"
   git remote add origin git@github.com:Feigenbaum4669/Feigenbaum4669.github.io.git
   git push -u origin main
   ```

5. **Enable Pages.** In the repo settings → Pages → Source, choose **GitHub Actions**. The deploy workflow already in `.github/workflows/publish.yml` will pick it up on the next push.

6. **Wait ~1 minute.** Site goes live at `https://feigenbaum4669.github.io`.

### Local preview

Install [Quarto](https://quarto.org/docs/get-started/), then from the repo root:

```bash
quarto preview
```

This opens a live-reloading preview at `http://localhost:port/`. Edits to `.qmd` files refresh automatically.

To render once without serving:

```bash
quarto render
```

Output goes to `_site/`.

## Structure

```
.
├── _quarto.yml            # site config (navbar, theme, footer)
├── index.qmd              # home + about (the trestles template)
├── research.qmd           # research overview
├── publications.qmd       # publications list (plain markdown)
├── cv.qmd                 # full CV
├── posts/                 # blog
│   ├── index.qmd          # listing page
│   └── welcome/index.qmd  # first post
├── assets/                # photo, favicon, eventual cv.pdf
├── styles.scss            # light theme overrides
├── styles-dark.scss       # dark theme overrides
└── .github/workflows/publish.yml  # CI deploy
```

## Adding a new blog post

```bash
mkdir posts/my-new-post
$EDITOR posts/my-new-post/index.qmd
```

Front matter template:

```yaml
---
title: "Post title"
description: "One-line description for the listing."
author: "Oskar Słowik"
date: "2026-06-01"
categories: [quantum, qiskit]
---
```

Then `quarto preview` to check, commit, push — the Action handles the rest.

## Custom domain (optional)

When you're ready to use your own domain:

1. Create `CNAME` in the repo root containing just your domain (e.g. `oskarslowik.com`).
2. Add a CNAME record at your DNS provider: `www` → `Feigenbaum4669.github.io`.
3. For apex domain, A records to GitHub's IPs (see [GitHub docs](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site#configuring-an-apex-domain)).
4. In repo settings → Pages, set the custom domain and enable HTTPS.

## License

Content (text, CV, posts) — all rights reserved.
Theme and code — MIT.
