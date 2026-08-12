# database

Storage layer.

- `mongo/` — MongoDB: raw collected data (document store).
- `redis/` — Redis: page-related caches / query reduction over MongoDB.
- `seed/` — curated data + rules (watchlists, keywords) seeded into the store.
