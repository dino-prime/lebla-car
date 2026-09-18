# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Static landing page for LeBla Car d.o.o., a rent-a-car business in Čakovec/Mihovljan, Croatia. Site content is in Croatian. Plain HTML/CSS/JS — no build system, no package manager, no tests.

## Deployment

Pushing to `main` deploys the **`www/` directory only** to GitHub Pages via `.github/workflows/static.yml`. Everything outside `www/` (root-level images, favicons, logo PDF) is source material that is not published — the live site is served entirely from `www/`.

## Structure

- `www/index.html` — the entire site: navbar, one hero section per car (with daily price), Google Maps embed ("Kako do nas"), contact section, footer. Several sections (fleet cards, services, testimonials) exist as commented-out HTML for possible future use.
- `www/css/styles.css` — custom styles on top of Bootstrap.
- `www/js/main.js` — AOS init, navbar scroll effect, smooth scrolling.
- `www/images/` — car photos and logo assets.

External dependencies (Bootstrap 5.3, Bootstrap Icons, AOS 2.3.1) are loaded from CDNs (jsdelivr, unpkg); Google Analytics (gtag, id G-D9YHQC78RY) is embedded in `index.html`.

## Development

No local server setup is required — open `www/index.html` in a browser, or serve it with `python -m http.server -d www`.

## Conventions

- Adding a new car to the fleet = adding another `hero-section` block in `index.html` following the existing Yaris/Peugeot pattern.
- User-facing text must be in Croatian.
