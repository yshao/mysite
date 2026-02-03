# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a **pre-built Quarto static website** deployed to GitHub Pages on the `gh-pages` branch. It is the personal academic/professional site of Yuping Shao, a PhD student at VISLab, Worcester Polytechnic Institute, with research interests in Healthcare AI, Data Science, Computer Vision, and Biomedical Informatics.

**Important**: This directory contains the **rendered HTML output** from Quarto, not the source files. The source Quarto project (with .qmd files, _quarto.yml, etc.) is maintained elsewhere.

## Technology Stack

- **Generator**: Quarto 1.2.269 (scientific/technical publishing system)
- **Styling**: Bootstrap 5 with custom styles.css
- **Search**: Fuse.js with Quarto Search
- **Deployment**: GitHub Pages (gh-pages branch)

## Architecture

### File Structure

```
mysite/
├── index.html              # Homepage
├── about.html              # About/CV page
├── publications.html/pdf   # Publications list and PDF
├── reswork.html            # Research/work experience
├── research.html           # Research overview
├── blog.html               # Blog listing page
├── posts/                  # Individual blog posts (organized by category)
│   ├── neuroscience/
│   ├── quarto-website/
│   ├── association-correlation-causation/
│   └── ...
├── blog/                   # Blog category index pages
├── site_libs/              # Quarto dependency libraries (Bootstrap, search, etc.)
├── search.json             # Search index for site search
└── styles.css              # Custom styles
```

### Navigation Structure

The main navigation (defined in each HTML file) includes:
- **Home** (index.html)
- **About/CV** (about.html)
- **Publications** (publications.pdf)
- **Experience** (reswork.html)
- **Research** (research.html)
- **Blog** (blog.html)

### Blog Post Pattern

Each blog post follows this structure:
```
posts/category-name/
└── index.html    # The full post content
```

The `blog/` directory contains category index pages that list posts within that category.

## Working with This Site

### Editing Content

Since this is pre-rendered HTML, edits are made directly to HTML files:

1. **Simple content edits**: Edit the HTML directly in the relevant file
2. **Navigation changes**: Update the navbar section in each HTML file (navigation is duplicated across pages)
3. **New blog posts**: Create a new directory under `posts/` with an `index.html` file following existing patterns

### Site-Wide Components

- **Navbar**: Defined in each page's `<header>` section with id="quarto-header"
- **Footer**: Defined in each page's `<footer>` section
- **Search**: Configured via the `#quarto-search-options` script tag in each page

### Styles

- Custom styles are in `styles.css`
- Bootstrap 5 classes are used throughout
- Academicons (academic social icons) are loaded from CDN

### Search Functionality

The site uses Quarto's built-in search:
- Search index: `search.json`
- Search UI: `#quarto-search-results` div and navbar search button
- Do not manually edit `search.json` - it should be regenerated from the source Quarto project

## Deployment

- Current branch: `gh-pages`
- Main branch: `main` (typically used for the source Quarto project)
- Deployment: Static files are served directly by GitHub Pages
- The `.nojekyll` file ensures GitHub Pages doesn't process with Jekyll

## Important Notes

1. **No build process here**: This repository contains the final output. There are no build commands, npm scripts, or Quarto configuration files.

2. **Consistency across pages**: Since navigation and headers are duplicated in each HTML file, changes affecting multiple pages require editing each file.

3. **Relative paths**: All links use relative paths (`./index.html`, `./about.html`, etc.) to work correctly when deployed.

4. **External assets**: Some assets are loaded from CDNs (Bootstrap, Academicons). Ensure internet connectivity for full functionality.

5. **For source edits**: If you need to edit the source Quarto files (.qmd), work in the source Quarto project directory (likely `source/mysite/` or the `main` branch) and re-render with `quarto render`.
