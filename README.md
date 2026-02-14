# AI Automation Southampton

Marketing website for **AI Automation Southampton** — an AI automation agency based in Southampton, Hampshire, UK, specialising in AI voice agents, chatbots, and workflow automation for local small businesses.

**Live site:** [aiautomationsouthampton.co.uk](https://aiautomationsouthampton.co.uk)

## Tech Stack

- Single `index.html` with inline CSS and JavaScript
- No build step, no frameworks, no dependencies
- Vanilla JS (IntersectionObserver for animations, accordion, contact form)
- Google Fonts (Sora + DM Sans)

## Features

- Dark premium theme with animated gradient orb hero
- Responsive design (320px to 1440px+)
- Interactive demo section with live chatbot and AI voice agent phone numbers
- Bolt Electrical case study strip
- Contact form (POST to n8n webhook)
- Cal.com embedded booking widget
- FAQ accordion (single-open-at-a-time)
- Animated stat counters
- Smooth scroll navigation

## SEO

- Semantic HTML5 with proper heading hierarchy
- JSON-LD structured data (LocalBusiness, Organization, FAQPage)
- Open Graph and Twitter Card meta tags
- `robots.txt`, `sitemap.xml`, and `logo.svg` included
- `privacy-policy.html` and `terms.html` for legal compliance
- Target keywords from Google Search Console data woven into copy

## Deployment

No build step required. Deploy the root directory to any static hosting provider:

- **GitHub Pages** — push to `main`, enable Pages in repo settings
- **Netlify** — connect the repo, publish directory: `/`
- **Vercel** — import the repo, framework preset: Other
- **Any web server** — upload `index.html`, `robots.txt`, `sitemap.xml`, `logo.svg`, legal pages, and the `images/` folder

## Project Structure

```
.
├── index.html                  # Complete single-page website
├── privacy-policy.html         # Privacy Policy page
├── terms.html                  # Terms of Business page
├── robots.txt                  # Search engine crawl rules
├── sitemap.xml                 # Sitemap for search engines
├── logo.svg                    # Vector logo created from data URI
├── images/
│   └── bolt.png                # Bolt Electrical case study screenshot
└── README.md                   # This file
```

## Contact

**Email:** hello@aiautomationsouthampton.co.uk
**Parent Agency:** [Antek Automation](https://antekautomation.com)
