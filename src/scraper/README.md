# scraper

Python crawler — ingests publicly available data (markets, Brazil news, tech news) and writes JSON snapshots consumed by the static GitHub Pages site.

- Markets: B3 quotes/thresholds.
- News: Brazilian crime/politics/health sources + tech (AI/hardware).
- Output: `src/data/snapshots/<category>/...json` (committed by `collect.yml`).

Run locally:

```bash
python src/scraper/crawler.py --out src/data/snapshots
```
