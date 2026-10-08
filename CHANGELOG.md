# Changelog

All notable changes to this project are documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/), and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

The `1.0.0` date is left as TODO until the day the tag is created. This file does not create that tag.

## [1.0.0] - TODO

First public listing of the template that is on `master` today.

### Added

- White-label link-in-bio. Each person is a JSON file in `content/bios/`. The brand, domain, and copy come from `content/site.json`.
- Static build with `vite-ssg`: one HTML page per profile, with its own title, Open Graph image, and favicon. The app uses Vue 3, Vite 8, Tailwind CSS 4, Pug, SCSS, and i18next. The package manager is Bun.
- Scoped admin at `/admin`. Each user is locked to one slug. Passwords are stored as hashes produced by `bun worker/hash-password.ts`.
- Admin API in `server/core/`, with adapters for Cloudflare Workers (default), Vercel, Netlify, AWS Lambda, and Azure Functions. GitHub Pages hosts the static site. Fork deploy workflows are `deploy-site.yml` and `deploy-worker.yml`. Upstream docs publish to openbio.page.
- Cookie banner, then PostHog visitor events. The admin Stats tab reads visits, unique visitors, views per day, clicks by link, sources, and countries for the signed-in slug.
- Build scripts write `sitemap.xml`, `robots.txt`, `llms.txt`, and `llms-full.txt`.
- Avatar export at `/:slug/export`.
- Blank fork starter in `template/` (`site.json`, one profile, `CNAME` placeholder).
- Four example instances built under `/examples/<id>/`: Northvale, Ferraresi, Ottobre, and Pietra. Demo mode drops the cookie banner and analytics, marks pages `noindex, nofollow`, and does not open made-up links.
- Identicon brand assets and the docs screenshot script `bun run docs:screens`.

[1.0.0]: https://github.com/open-bio-page/open-bio-page/releases/tag/v1.0.0
