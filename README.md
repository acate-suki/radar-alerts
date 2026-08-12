# radar-alerts

A listener for things you care about — collect from many websites, store, process, and surface the interesting bits. Enterprise-style: **Go** pipeline + **MongoDB/Redis** + **vanilla JS** static site on GitHub Pages. Public, no auth.

Three focus pillars:

- **Markets** — B3 stocks past thresholds (below/above 3% today, 5% week, 10% two weeks).
- **Brazil news** — crimes · politics · health.
- **Tech news** — new AI companies/models · new hardware.

## Structure

```text
src/
  scraper/     Python web crawlers (markets · news · tech)
  api/         Go API — serves the ui + queue/workers/notify pipeline
  database/    mongo (raw collected data) + redis (page cache) + seed (curated rules)
  ui/          vanilla JS static pages → GitHub Pages
docker/        Dockerfile + docker-compose.yml (api + mongo + redis)
docs/
```

## How it works

Crawler → store raw in MongoDB → in-process queue → workers → notify; Redis caches page-related views (reduces Mongo queries). The static `ui/` is rebuilt/updated as data is collected. No deployment beyond GitHub Pages for the static site.

See the issue backlog for the roadmap.
