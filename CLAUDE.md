# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Marketing website for **AI Automation Southampton** — an AI automation agency in Southampton, Hampshire, UK. Part of the broader Antek Automation network with related regional sites (Portsmouth, Basingstoke, Winchester, Farnborough).

**Live site:** https://aiautomationsouthampton.co.uk

## Tech Stack & Build

- **Zero-dependency static site** — no frameworks, no package.json, no build step
- Single `index.html` (~2,990 lines) containing all HTML, inline CSS (`<style>`), and inline JS (`<script>`)
- Separate legal pages: `privacy-policy.html`, `terms.html`
- Google Fonts via CDN (Sora for headings, DM Sans for body)
- Deploy by pushing the root directory to any static host (GitHub Pages, Netlify, Vercel)

## Architecture

**Single-page layout** with hash-based anchor navigation (`#services`, `#demo`, `#how-it-works`, `#industries`, `#why-us`, `#faq`, `#contact`). Fixed navbar with mobile hamburger menu.

**CSS:** All in a single `<style>` block using CSS custom properties (`:root` variables) as a design system. Dark theme (`--bg-primary: #0a0f1c`) with blue/cyan accent gradients. BEM naming convention. Responsive breakpoints at 768px (mobile hamburger) with 320px minimum width.

**JavaScript:** Wrapped in an IIFE with `'use strict'`. Key systems:
- **IntersectionObserver** for scroll-reveal animations (`.reveal` → `.visible`) and lazy-loading the Cal.com widget
- **FAQ accordion** — single-open behavior with ARIA attributes and max-height animation
- **Stat counter** — animated count-up using requestAnimationFrame with eased timing
- **Contact form** — honeypot spam prevention, POSTs JSON to n8n webhook, toast notifications for feedback
- **Waveform bars** — dynamically generated animated bars in the hero section

## External Integrations

| Service | Purpose | Details |
|---------|---------|---------|
| **n8n** | Contact form backend | POST to `antekauto.app.n8n.cloud` webhook |
| **Cal.com** | Booking widget | Embedded calendar (`antek-automation/30min`), lazy-loaded |
| **Retell AI** | AI voice agent partner | Partner badge in footer, demo phone numbers in content |

## SEO

Heavily SEO-optimized for local search:
- JSON-LD structured data: LocalBusiness, Organization, FAQPage schemas
- Geo meta tags and ICBM coordinates (50.9097, -1.4044)
- Open Graph + Twitter Card meta tags
- `robots.txt` and `sitemap.xml` included
- Content targets Southampton/Hampshire-specific AI automation keywords

## Key Conventions

- All code lives inline in HTML files — no external CSS/JS files
- CSS variables in `:root` control the entire design system; change colors/fonts there
- Interactive elements use IntersectionObserver (not scroll event listeners)
- Form submissions go through n8n webhooks, not a traditional backend
