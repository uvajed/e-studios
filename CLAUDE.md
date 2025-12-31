# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

e·studios is a static website for an app development company focused on ethical, ad-free, privacy-first educational apps for children and families. Hosted on GitHub Pages with custom domain (www.e-studios.net).

## Architecture

Single-page static website with no build system:
- **index.html** - Complete site: HTML, embedded CSS (`<style>`), and JavaScript for i18n
- **og-image.png** - Open Graph image for social link previews (1200x630)
- **CNAME** - GitHub Pages custom domain (www.e-studios.net)

## Development

Preview locally:
```bash
python3 -m http.server 8000
```

Deploy by pushing to `main` branch. No build step required.

## Design System

Elegant editorial aesthetic with light theme:

**Typography:**
- `--serif`: Cormorant Garamond (headings, titles)
- `--sans`: Inter (body text, navigation)

**Colors (CSS custom properties in `:root`):**
- `--bg`: #faf9f7 (warm cream background)
- `--bg-warm`: #f5f3ef (section backgrounds)
- `--accent`: #c9a87c (gold/champagne)
- `--text`: #1a1a1a, `--text-light`: #666, `--text-lighter`: #999

**Brand element:** Gold dot (`.dot`) used in logo and throughout.

**Color accents:**
- Philosophy icons: sage green (#7eb8a2), dusty blue (#8fa3bf), dusty rose (#d4a5a5)
- Project icons: subtle gradient backgrounds (lavender, mint, peach, terracotta, blue, sage)

## Animations

**Scroll reveal:** Elements with `.reveal` and `.reveal-item` classes fade in and slide up when scrolling into view (Intersection Observer). Staggered delays applied via `nth-child`.

**Sticky sections:** Philosophy and Contact sections use `position: sticky` to overlap previous sections as you scroll (Apple-style effect). Work section scrolls normally due to tall content.

## Multilingual Support

Three languages with JavaScript-based switching:
- **EN** (English), **DE** (German), **SQ** (Albanian)

Translations stored in `translations` object in `<script>`. Elements marked with `data-i18n` attribute get translated. Language preference saved to localStorage and auto-detects browser language.

To add/edit translations, modify the `translations` object. Keys use dot notation (e.g., `philosophy.adFree.title`).

## Page Structure

- **Hero**: Large serif title, italic subtitle, scroll indicator
- **Philosophy** (id="philosophy"): Three value cards with decorative symbols (✦ ◈ ❋)
- **Work** (id="work"): Project list with roman numerals, status badges (Live/In Development)
- **Contact** (id="contact"): CTA with animated underline email link
- **Footer**: Logo and copyright

## Projects

Live apps link to Vercel deployments. Project names are not translated (brand names).
