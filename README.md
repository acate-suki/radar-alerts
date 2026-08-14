# radar-alerts

A listener for things you care about — **ingest public data → digest → static dashboard**. Async collection only, no backend deployed. The crawler runs on a schedule in GitHub Actions and commits JSON snapshots; the vanilla JS static site on GitHub Pages renders them as reports. Public, no auth, little interaction.

Three focus pillars:

- **Markets** — B3 stocks past thresholds (below/above 3% today, 5% week, 10% two weeks).
- **Brazil news** — crimes · politics · health.
- **Tech news** — new AI companies/models · new hardware.

## Structure

```text
src/
  scraper/     Python crawler — ingests public data, writes JSON snapshots
  data/        curated rules + watchlists (seed) and snapshots/ (crawler output)
  ui/          vanilla JS static pages → GitHub Pages
docs/
```

## How it works

`collect.yml` (scheduled GitHub Actions) runs the Python crawler → writes `src/data/snapshots/` → commits → `pages.yml` rebuilds the static site from `src/ui/` + `src/data/`. No API, no database, no long-running services — everything is batch and static.

## Quick start

```bash
python src/scraper/crawler.py --out src/data/snapshots
python -m http.server -d src/ui  # or open src/ui/index.html
```

See the issue backlog for the roadmap.
