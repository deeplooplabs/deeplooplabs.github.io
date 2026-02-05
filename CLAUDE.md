# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a **Jekyll-based static website** for DeepLoop Labs (AI solutions & tech staffing). It's a port of the Kross HTML template, deployed to GitHub Pages at `deeploop.dev`.

## Development Commands

```bash
# Install dependencies
bundle install

# Start local development server
jekyll serve
# or with proper gem environment
bundle exec jekyll serve

# Build production site to _site/
jekyll build
bundle exec jekyll build
```

## Architecture

### Data-Driven Content
All site content is managed via YAML files in `_data/`:
- `_data/settings.yml` - Main content (hero, about, skills, services, contact, etc.)
- `_data/plugins.yml` - External CSS/JS assets (Bootstrap, jQuery, etc.)

**To modify content, edit YAML files—not HTML templates.**

### Component Structure
- `_includes/*.html` - Reusable section partials (hero, about, services, etc.)
- `_layouts/*.html` - Page templates with inheritance: `compress.html` → `default.html`
- `_pages/` - Static pages (about.md, blog.html, contact.html, etc.)
- `assets/scss/` - Modular SASS stylesheets

### Jekyll Configuration
- `_config.yml` - Jekyll settings (markdown processor, permalinks, Sass options)
- `Gemfile` - Ruby dependencies (jekyll, jekyll-sitemap, webrick)

## Deployment

The site auto-deploys to GitHub Pages from the `main` branch. Custom domain: `deeploop.dev` (configured in CNAME).

## Key Conventions

- Use Kramdown markdown in `_posts/` for blog entries
- SCSS files in `assets/scss/` are compiled during Jekyll build
- External libraries (Bootstrap, Themify Icons, Slick, Shuffle) are loaded via `_data/plugins.yml`
