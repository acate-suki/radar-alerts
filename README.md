# radar-alerts

A listener for things you care about — surface the interesting bits without subscribing to everything.

Three focus pillars:

- **Markets** — stocks currently moving past thresholds: below/above **3% today**, **5% last week**, **10% last two weeks** (Brazil, B3).
- **Brazil news** — a summary of the most relevant stuff, per tab: **crimes** · **politics** · **health**.
- **Tech news** — what's new: **AI companies/models** · **new hardware**.

## How it works

Data + rules live under `src/` — each area is a curated watchlist + a set of rules (what counts as "relevant"). The future backend service (scheduled fetchers → analysis → API/notifications) is tracked as issues; no deployment for now.

## Layout

```text
src/
  markets/   B3 watchlist + threshold rules
  news/
    brazil/  crimes · politics · health tabs
    tech/    ai · hardware
```

See `docs/` and the issue backlog for the roadmap.
