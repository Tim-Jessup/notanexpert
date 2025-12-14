# notanexpert.fyi - My Experimental Site

A simple, clean portfolio site for sharing experiments, tools, and learning notes.

## Quick Start if you want to make the same thing

### 1. Install Hugo

**macOS:**
```bash
brew install hugo
```

**Windows:**
```bash
choco install hugo-extended
```

**Linux:**
```bash
sudo snap install hugo
```

Or download from: https://gohugo.io/installation/

### 2. Preview locally

```bash
cd notanexpert-site
hugo server -D
```

Open http://localhost:1313 in your browser.

### 3. Create new content

**New project:**
```bash
hugo new projects/my-project.md
```

**New tool:**
```bash
hugo new tools/my-tool.md
```

**New note:**
```bash
hugo new notes/my-note.md
```

Edit the markdown files in the `content/` directory.

## Deploying to GitHub Pages

### 1. Create GitHub repository

```bash
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/notanexpert-site.git
git push -u origin main
```

### 2. Enable GitHub Pages

1. Go to your repository settings
2. Navigate to "Pages" in the left sidebar
3. Under "Build and deployment":
   - Source: GitHub Actions
4. Create `.github/workflows/hugo.yml`:

```yaml
name: Deploy Hugo site to Pages

on:
  push:
    branches:
      - main
  workflow_dispatch:

permissions:
  contents: read
  pages: write
  id-token: write

concurrency:
  group: "pages"
  cancel-in-progress: false

defaults:
  run:
    shell: bash

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout
        uses: actions/checkout@v4
        with:
          submodules: recursive
          fetch-depth: 0
      - name: Setup Hugo
        uses: peaceiris/actions-hugo@v2
        with:
          hugo-version: 'latest'
          extended: true
      - name: Build
        run: hugo --minify
      - name: Upload artifact
        uses: actions/upload-pages-artifact@v2
        with:
          path: ./public
  deploy:
    environment:
      name: github-pages
      url: ${{ steps.deployment.outputs.page_url }}
    runs-on: ubuntu-latest
    needs: build
    steps:
      - name: Deploy to GitHub Pages
        id: deployment
        uses: actions/deploy-pages@v2
```

### 3. Configure custom domain

1. In repository settings → Pages → Custom domain
2. Enter: `notanexpert.fyi`
3. In your domain registrar (where you bought notanexpert.fyi):
   - Add A records pointing to GitHub Pages:
     - `185.199.108.153`
     - `185.199.109.153`
     - `185.199.110.153`
     - `185.199.111.153`
   - Add CNAME record: `www` → `YOUR-USERNAME.github.io`

Wait a few minutes for DNS to propagate, then your site will be live at notanexpert.fyi!

## Customization

### Change site title/description

Edit `hugo.toml`:
```toml
title = 'Your Title'
[params]
  description = 'Your description'
```

### Modify styling

Edit `themes/simple-portfolio/static/css/style.css`

### Add navigation items

Edit the `[[menu.main]]` sections in `hugo.toml`

## File Structure

```
notanexpert-site/
├── content/              # Your markdown content
│   ├── about.md
│   ├── projects/
│   ├── tools/
│   └── notes/
├── themes/
│   └── simple-portfolio/ # The theme
│       ├── layouts/      # HTML templates
│       └── static/       # CSS, JS, images
└── hugo.toml            # Site configuration
```

## Writing Content

All content uses markdown with front matter:

```markdown
---
title: "My Project"
date: 2024-12-14
github: "https://github.com/user/repo"  # optional
---

Your content here in markdown format.

## Headers work

- Lists work
- Code blocks work

etc.
```

## Tips

- Run `hugo server -D` while editing to see changes live
- The `-D` flag shows draft posts
- Remove `draft: true` from front matter when ready to publish
- Commit and push to GitHub to deploy changes

## Need Help?

- Hugo docs: https://gohugo.io/documentation/
- Markdown guide: https://www.markdownguide.org/
- GitHub Pages docs: https://docs.github.com/en/pages
