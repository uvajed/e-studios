# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

e·studios is a static website for an app development company focused on ethical, ad-free, privacy-first educational apps for children and families. The site is hosted on GitHub Pages with a custom domain (e-studios.net).

## Architecture

This is a single-page static website with no build system:
- **index.html** - The entire site in one file containing HTML, CSS (embedded in `<style>`), and content
- **CNAME** - GitHub Pages custom domain configuration

## Development

To preview locally, open `index.html` directly in a browser or use any static file server:
```bash
python3 -m http.server 8000
```

No build step, bundling, or dependencies required. Deploy by pushing to the `main` branch.

## Design System

CSS custom properties defined in `:root`:
- `--bg`, `--bg-subtle` - Background colors (dark theme)
- `--text`, `--text-muted`, `--text-subtle` - Text hierarchy
- `--accent` - Brand color (#f43f5e rose)
- `--border` - Border color

The brand element is a pulsing rose-colored dot (`.dot`) used throughout as a visual motif.

## Key Sections

The page has four main sections: hero, about (with values cards), projects (card grid), and contact. Navigation is fixed with smooth scrolling. Mobile responsive at 768px breakpoint.
