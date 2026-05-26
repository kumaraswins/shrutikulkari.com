# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Static single-page website for Shruti Kulkarni, an ICF PCC-credentialed executive coach. The site is deployed on Netlify and has no build step — `index.html` is the production artifact.

## Development

**Preview locally:**
```bash
npx netlify-cli dev
# or just open index.html directly in a browser
```

**Deploy to Netlify:**
```bash
npx netlify deploy --prod
```

There are no tests, linting, or compilation steps.

## Architecture

Everything lives in a single `index.html` file:

- **CSS** — inline `<style>` block. A design system is defined via CSS custom properties on `:root` (colors, typography, spacing, radii, shadows, transition easing). All component styles follow from these variables.
- **HTML** — eight sections in order: Navbar → Hero → Trust Strip → About → Approach → Visual Storytelling (parallax) → Testimonials → Services → FAQ → Final CTA → Footer.
- **JavaScript** — inline `<script>` at bottom of `<body>`. Three behaviors: navbar scroll-shrink (adds `.scrolled` on `window.scrollY > 50`), scroll-reveal via `IntersectionObserver` (adds `.active` to elements with class `.reveal`), and accordion toggle for the FAQ section.

## Design System

| Token | Value |
|---|---|
| `--bg-color` | `#FAF8F4` (off-white warm) |
| `--text-primary` | `#4A3B69` (deep purple) |
| `--accent-color` | `#598FA8` (muted teal-blue) |
| `--font-heading` | Cormorant Garamond (Google Fonts) |
| `--font-body` | DM Sans (Google Fonts) |

Responsive breakpoints: `1024px` (tablet — collapses multi-column grids) and `768px` (mobile — single column, hides nav links).

## Key External Links

- Booking: `https://calendly.com/shruti-kulkarni9/discovery-call`
- LinkedIn: `https://www.linkedin.com/in/shrutikulkarni405`
- Instagram: `https://www.instagram.com/shruti.coaches`
- Contact email: `hello@shrutikulkarni.com`

## Images

Local image assets used in the page: `1.jpeg` (hero portrait), `2.jpeg` (about section), `3.jpeg` (unused), `visual_storytelling_1779732166628.png` (parallax background). The `.netlify/netlify.toml` references a separate Astro project — it is a leftover and can be ignored.
