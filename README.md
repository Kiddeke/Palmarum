# Palmarum

The marketing site for **Palmarum LLC** — an independent Catholic software
studio — served at [palmarum.dev](https://palmarum.dev).

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
| `CNAME` | Custom domain for GitHub Pages (`palmarum.dev`). |
| `robots.txt`, `sitemap.xml` | Basic SEO. |
| `assets/` | The two apps' real logos, copied from their repos — Palma's Stride Frond (`palma-icon.svg`/`.png`) and Sebastian's volley mark (`sebastian-volley-dark.png`, `-light.png`). |
| `.github/workflows/deploy.yml` | Deploys the site to GitHub Pages on push to `master`. |

Fonts (Fraunces, Hanken Grotesk, Archivo, Cinzel) load from Google Fonts. The
Palmarum parent mark and Palma's frond are inline SVG; Sebastian's logo is a PNG
in `assets/`. The app logos are the real ones shipped in the Palma app — update
them here if the app icons change.

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
deployment → Source** and choose **GitHub Actions**. Point the `palmarum.dev`
DNS at GitHub Pages (an `ALIAS`/`ANAME` or the four `A` records for the apex
domain, plus a `CNAME` on `www` → `kiddeke.github.io`), and Pages will pick up
the domain from the `CNAME` file. Enable "Enforce HTTPS" once the certificate
is issued.

## Contact

`hello@palmarum.dev` — update the address in `index.html` (footer) if a
different inbox is preferred.
