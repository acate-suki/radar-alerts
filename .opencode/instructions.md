# Radar-alerts conventions

A listener for things you care about. Three pillars:

- **Markets** — B3 stocks past thresholds (below/above 3% today, 5% week, 10% two weeks).
- **Brazil news** — crimes · politics · health tabs, summarized.
- **Tech news** — new AI companies/models · new hardware.

## Rules

- Content lives under `src/` as curated watchlists + rules (data), one area per folder.
- Each area keeps its own readme (the entry point) listing sources + keywords + rules.
- Implementation (fetchers, analysis, notifications) is tracked as issues — no deployment for now.
- Theme: `GitHub Dark Default`.

## CI

- `test.yml` — PR gate (`cli repo lint`).
- `release.yml` — main: validate + timestamp tag + GitHub release. No deployments.
