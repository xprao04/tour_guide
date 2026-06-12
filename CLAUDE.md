# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project

A simple presentation (single-page marketing) website for **Jana**, a tour guide in Prague. The site introduces Jana, describes her tours, and provides contact details. Content is currently **English only**; a **Portuguese** translation is planned for the future, so keep all user-facing copy easy to extract and translate (avoid hardcoding strings in awkward places, keep text in clear content blocks).

## Tech Stack

Pure static website — **HTML5 + CSS3**, no build step, no framework, no dependencies. Vanilla JavaScript only if interactivity is genuinely needed (mobile nav toggle, smooth scroll). Mirrors the sister project `../avecutis_html`, which is the reference for structure and conventions.

Expected file layout (create as the site is built):

```
index.html      # Single page, all content sections
styles.css      # All styling, driven by CSS custom properties
script.js       # Optional vanilla JS (nav toggle, scroll behavior)
```

## Running locally

No build process. Either open the file directly or serve it:

```bash
open index.html
# or
python -m http.server 8000
```

## Deployment

Static site targeting **GitHub Pages** on the `main` branch. Push to GitHub and enable Pages; no build step. Workflow used on the sister project:

```bash
git add -A
git commit -m "message"
git push origin main   # auto-deploy is wired up on push to main
```

## Conventions (follow the sister project `../avecutis_html`)

- **Mobile-first** responsive CSS with media queries for tablet/desktop.
- **CSS custom properties** in `:root` for the full design system: color palette, spacing scale, typography, radius, shadows, transitions. Theme by editing variables, not scattered values.
- **Semantic HTML** with ARIA labels, keyboard navigation, and `prefers-reduced-motion` support.
- **Google Fonts** loaded via `<link>` with `preconnect` (sister site uses Inter).
- Keep it lightweight and dependency-free — no frameworks or bundlers.
- For the future Portuguese version, keep copy organized so a parallel translated page (or language toggle) can be added without restructuring.

## Notes

- `prompt.md` holds the original brief and any incoming content/context from the project owner.
- Internationalization (PT) is a known upcoming requirement — design with it in mind, don't implement it yet.
