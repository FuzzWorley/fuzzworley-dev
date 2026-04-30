# fuzzworley.dev

Personal contractor marketing site for Fuzz Worley — senior Rails engineer based in St. Pete, FL.

## Stack

- **Astro** — static site generator, outputs pure HTML/CSS, zero JS by default
- **Vanilla CSS** — all styles in `src/styles/global.css`, no framework
- **Google Fonts** — DM Serif Display (headings) + DM Mono (labels/tags)
- **Cloudflare Pages** — recommended for free hosting + CDN

## Getting started

```bash
npm install
npm run dev       # http://localhost:4321
npm run build     # outputs to ./dist/
npm run preview   # preview the build locally
```

## Project structure

```
fuzzworley-site/
├── public/
│   └── favicon.svg
├── src/
│   ├── pages/
│   │   └── index.astro       ← main one-pager (all content lives here)
│   └── styles/
│       └── global.css        ← all styles + dark mode + responsive
├── astro.config.mjs
└── package.json
```

## Content to update

All content is in `src/pages/index.astro` in the frontmatter arrays at the top:

- **`stats[]`** — the three metric cards below the hero
- **`work[]`** — selected work history items
- **`services[]`** — the 2×2 services grid

Edit those arrays to change content without touching layout code.

### Things still TODO

- [ ] Replace `mailto:hello@fuzzworley.dev` with your real email or a Formspree form
- [ ] Update GitHub link to your real GitHub username
- [ ] Add Signalfire to the work section once you're ready to showcase it
- [ ] Consider adding an `/uses` or `/blog` page for technical content (great for SEO)
- [ ] Set up Cloudflare Pages: connect GitHub repo → auto-deploys on push

## Contact form with Formspree (no backend needed)

Replace the mailto link in `index.astro` with:

```html
<form action="https://formspree.io/f/YOUR_FORM_ID" method="POST" style="display:flex;flex-direction:column;gap:1rem;max-width:400px;margin:0 auto;">
  <input type="email" name="email" placeholder="your@email.com" required />
  <textarea name="message" placeholder="What are you working on?" rows="4" required></textarea>
  <button type="submit" class="btn-primary">Send message</button>
</form>
```

Sign up free at formspree.io to get your form ID.

## Deploying to Cloudflare Pages

1. Push this repo to GitHub
2. Go to Cloudflare Pages → Create a project → Connect to Git
3. Framework preset: **Astro**
4. Build command: `npm run build`
5. Output directory: `dist`
6. Done — every push to main auto-deploys

## Design decisions

- **No JS framework** — Astro outputs static HTML. No React, no bundle, ~zero JS sent to browser.
- **No Tailwind** — the site is simple enough that vanilla CSS is cleaner and faster to customize.
- **Dark mode** — handled via `@media (prefers-color-scheme: dark)` on CSS variables. Automatic, no toggle needed.
- **Fonts loaded from Google** — swap to self-hosted if you want full offline/privacy control.

## Context for AI assistance

This is a one-page contractor marketing site. The owner is a senior Rails/PostgreSQL engineer
with 7+ years of experience, previously at MasterClass, Emeritus, and Secureframe.
Niches: Rails/SaaS modernization, payments systems, compliance automation, fintech/crypto.
Rate: $115–$135/hr. Location: St. Pete, FL.

When making changes, keep the aesthetic minimal and editorial — DM Serif Display for headings,
DM Mono for labels, generous whitespace, 0.5px borders. No gradients, no shadows, no bright colors.
The design should feel like a thoughtful engineer made it, not a marketing team.
