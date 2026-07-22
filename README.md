# Palmarum

The marketing site for **Palmarum LLC** — an independent Catholic software
studio — served at [palmarum.com](https://palmarum.com).

Palmarum is the parent brand for two iOS apps:

- **Sebastian** — an AI running coach.
- **Palma** — a faith & fitness ledger.

This repository contains only the public website. The apps live in their own
repositories and are not affected by anything here.

## What's here

A small, dependency-free static site — plain HTML and CSS, no build step.

| File | Purpose |
| ---- | ------- |
| `index.html` | The single-page site: hero, credo, apps, studio, and the full brand sheet. |
| `styles.css` | All styling (design tokens, layout, components, motion). |
| `favicon.svg` | The Palmarum palm mark, used as the site icon. |
| `404.html` | Branded not-found page. |
| `CNAME` | Custom domain for GitHub Pages (`palmarum.com`). |
| `robots.txt`, `sitemap.xml` | Basic SEO. |
| `.github/workflows/deploy.yml` | Deploys the site to GitHub Pages on push to `master`. |

Fonts (Fraunces, Hanken Grotesk, Archivo, Cinzel) load from Google Fonts. The
palm marks are inline SVG, so there are no image assets to manage.

## Developing

There is no toolchain — open `index.html` in a browser, or serve the folder:

```bash
python3 -m http.server 8000   # then visit http://localhost:8000
```

Edit `index.html` for content and `styles.css` for design. The `:root` block at
the top of `styles.css` holds the brand colour tokens.

## Deploying

The site deploys automatically to GitHub Pages via GitHub Actions on every push
to `master`.

**One-time setup:** in the repo, go to **Settings → Pages → Build and
deployment → Source** and choose **GitHub Actions**. Point the `palmarum.com`
DNS at GitHub Pages (an `ALIAS`/`ANAME` or the four `A` records for the apex
domain, plus a `CNAME` on `www` → `kiddeke.github.io`), and Pages will pick up
the domain from the `CNAME` file. Enable "Enforce HTTPS" once the certificate
is issued.

## Contact

`hello@palmarum.com` — update the address in `index.html` (footer) if a
different inbox is preferred.
