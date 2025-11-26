# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Personal website built with Jekyll and hosted on GitHub Pages. The site features a blog section and technical presentations using Reveal.js. All content is written in Markdown and automatically deployed via GitHub Pages.

## Development Commands

### Local Development
```bash
# Start local development server with live reload
docker-compose up

# Site available at http://localhost:4000
# Live reload enabled on port 35729
```

### Content Creation

#### Blog Posts
- Create files in `docs/_posts/` with format: `YYYY-MM-DD-title.md`
- Required front matter:
  ```yaml
  ---
  layout: post
  title: "Post Title"
  date: YYYY-MM-DD HH:MM:SS +0000
  categories: category-name
  ---
  ```

#### Presentations
- HTML presentations go in `docs/_presentations/`
- Static assets (images, etc.) go in `docs/presentations/[presentation-name]/`
- Presentations use Reveal.js framework

## Architecture

### Directory Structure
```
docs/                    # Jekyll site root
├── _config.yml         # Jekyll configuration
├── _posts/             # Blog posts (Jekyll posts collection)
├── _presentations/     # HTML presentations (Jekyll collection)
├── presentations/      # Static assets for presentations
├── _site/             # Generated site (ignored in git)
└── vendor/            # Bundler dependencies (ignored in git)
```

### Jekyll Collections
- `_presentations`: Custom Jekyll collection with permalink `/presentations/:name/`
- `_posts`: Standard Jekyll posts collection

### Key Files
- `docs/_config.yml`: Jekyll configuration with Minima theme
- `docker-compose.yml`: Development environment using `jekyll/jekyll:4` image
- `docs/Gemfile`: Uses `github-pages` gem for compatibility

### Deployment
- Automatic deployment to GitHub Pages on push to `main` branch
- Site URL: https://chatzinikolakisk.github.io
- Uses GitHub Pages compatible gems only

### Theme and Layout
- Uses Minima theme with custom navigation
- Navigation includes: blog.md, presentations.md
- Home page displays recent posts and presentations using Jekyll liquid templates