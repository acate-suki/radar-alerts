# api

Go API — serves the collected data to the `ui` (vanilla JS pages) and handles the queue/notify pipeline.

- `crawler` feed: stores collected data in MongoDB, caches page-related views in Redis.
- REST endpoints for the static pages (markets movers, news summaries).
