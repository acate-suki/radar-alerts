# Radar-alerts conventions

A listener for things you care about. Enterprise-style, public, no auth.

## Structure

- `src/scraper/` — Python web crawlers (markets · Brazil news · tech).
- `src/api/` — Go API: serves the ui + in-process queue → workers → notify.
- `src/database/` — `mongo/` (raw collected data) · `redis/` (page cache) · `seed/` (curated rules/watchlists).
- `src/ui/` — vanilla JS static pages → GitHub Pages.

## Rules

- Pipeline: crawler → Mongo (raw) → queue → workers → notify; Redis for page-related views.
- Store raw in Mongo; keep curated rules as seed data.
- No auth — the site is public.
- Theme: `GitHub Dark Default`.

## CI

- `test.yml` — PR gate: `cli repo lint`.
- `release.yml` — main: validate + timestamp tag + GitHub release. No deployments.
