# Radar-alerts conventions

A listener for things you care about. Static, public, no auth.

## Structure

- `src/scraper/` — Python crawler: ingests public data, writes JSON snapshots.
- `src/data/` — curated rules + watchlists, and `snapshots/` (crawler output).
- `src/ui/` — vanilla JS static pages → GitHub Pages.

## Rules

- Pipeline: scheduled `collect.yml` → crawler → commit snapshots → `pages.yml` rebuilds the static site.
- No deployed backend/API/database — async collection only.
- Store curated rules as static data; crawler output goes to `src/data/snapshots/`.
- The site is a dashboard with reports — little interaction.
- Theme: `GitHub Dark Default`.

## CI

- `test.yml` — PR gate: `cli repo lint`.
- `collect.yml` — scheduled snapshot refresh (async collection).
- `pages.yml` — deploy `src/ui/` + `src/data/` to GitHub Pages.
- `release.yml` — main: validate + timestamp tag + GitHub release.
