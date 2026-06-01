# Central African Republic Administrative Divisions / République centrafricaine



## Overview

| Item | Details |
|------|---------|
| Prefecture | 20 |
| Sub-prefecture | 85 |
| Commune | 170 |
| Coordinates | ✅ Included (all levels) |
| Formats | JSON, NDJSON, CSV |
| License | CC-BY-4.0 |
| Last Updated | 2026-06-01 |
| Website | [openadmindata.org/cf](https://openadmindata.org/cf/) |
| API | [openadmindata.org/api/cf](https://openadmindata.org/api/cf/) |

## Browse by Prefecture

| # | Prefecture | Sub-prefectures | Communes | Link |
|---|----|----|----|------|
| 1 | Lobaye | 6 | 14 | [Browse](divisions/lobaye-cf12/) |
| 2 | Nana-Mambéré | 4 | 17 | [Browse](divisions/nana-mambr-cf22/) |
| 3 | Ouham | 4 | 6 | [Browse](divisions/ouham-cf32/) |
| 4 | Ouham-Fafa | 4 | 12 | [Browse](divisions/ouham-fafa-cf33/) |
| 5 | Kémo | 4 | 6 | [Browse](divisions/kmo-cf41/) |
| 6 | Lim-pendé | 5 | 14 | [Browse](divisions/lim-pend-cf34/) |
| 7 | Ouham Pendé | 4 | 9 | [Browse](divisions/ouham-pend-cf31/) |
| 8 | Sangha-Mbaéré | 3 | 7 | [Browse](divisions/sangha-mbar-cf23/) |
| 9 | Vakaga | 4 | 2 | [Browse](divisions/vakaga-cf53/) |
| 10 | Bamingui-Bangoran | 2 | 4 | [Browse](divisions/bamingui-bangoran-cf51/) |
| 11 | Mbomou | 5 | 10 | [Browse](divisions/mbomou-cf62/) |
| 12 | Ombella M&#39;Poko | 5 | 5 | [Browse](divisions/ombella-mpoko-cf11/) |
| 13 | Basse-Kotto | 6 | 15 | [Browse](divisions/basse-kotto-cf61/) |
| 14 | Haute-Kotto | 4 | 10 | [Browse](divisions/haute-kotto-cf52/) |
| 15 | Mambéré-Kadéï | 4 | 6 | [Browse](divisions/mambr-kad-cf21/) |
| 16 | Mambéré | 4 | 4 | [Browse](divisions/mambr-cf24/) |
| 17 | Haut-Mbomou | 5 | 5 | [Browse](divisions/haut-mbomou-cf63/) |
| 18 | Nana-Gribizi | 3 | 3 | [Browse](divisions/nana-gribizi-cf42/) |
| 19 | Ouaka | 5 | 13 | [Browse](divisions/ouaka-cf43/) |
| 20 | Bangui | 4 | 8 | [Browse](divisions/bangui-cf71/) |

## Data Files

| File | Format | Description |
|------|--------|-------------|
| [all-prefecture.json](data/all-prefecture.json) | JSON | All 20 prefecture records |
| [all-sub_prefecture.json](data/all-sub_prefecture.json) | JSON | All 85 sub-prefecture records |
| [all-commune.json](data/all-commune.json) | JSON | All 170 commune records |
| [all-flat.json](data/all-flat.json) | JSON | Levels 1-2 flat array |
| [all-flat.ndjson](data/all-flat.ndjson) | NDJSON | Streaming format |
| [all-flat.csv](data/all-flat.csv) | CSV | Spreadsheet format |
| [hierarchy.json](data/hierarchy.json) | JSON | Nested tree |
| [schema.json](data/schema.json) | JSON Schema | Data schema |

## Quick Start

### Python

```python
import json

with open("data/all-prefecture.json", "r", encoding="utf-8") as f:
    data = json.load(f)

for r in data:
    print(f"{r['name']['local']} ({r['name']['en']}) — {r['children_count']['sub_prefecture']} sub-prefectures")
```

### JavaScript

```javascript
import { readFileSync } from "fs";

const data = JSON.parse(readFileSync("data/all-prefecture.json", "utf-8"));
console.log(`Total: ${data.length} prefectures`);
```

## Schema

| Field | Type | Description |
|-------|------|-------------|
| `id` | string | Unique identifier |
| `level` | integer | 1=prefecture, 2=sub-prefecture, 3=commune |
| `level_name` | object | Level label (local + English) |
| `name.local` | string | Name in local script |
| `name.en` | string | English name |
| `name.slug` | string | URL-safe slug |
| `parent` | object/null | Parent division reference |
| `ancestors` | array | Full ancestor chain |
| `children_count` | object | Count of children per level |
| `zip_codes` | array | Postal codes (where available) |
| `geo.lat` | string | Latitude (WGS84) |
| `geo.lon` | string | Longitude (WGS84) |

Full schema: [data/schema.json](data/schema.json)

## Hierarchy Browse

```
divisions/{prefecture-slug}/
divisions/{prefecture-slug}/{sub_prefecture-slug}/
```

Communes are listed inline in each sub-prefecture's README.

## AI Integration

- [llms.txt](docs/llms.txt) — Quick reference for AI agents
- [llms-full.txt](docs/llms-full.txt) — Summary with per-prefecture links
- [Per-prefecture data](docs/llms-full/) — Full data by prefecture

## Citation

```
Central African Republic Administrative Divisions Dataset (CC-BY-4.0)
URL: https://github.com/open-admin-data/central-african-republic-administrative-divisions
```

See [CITATION.cff](CITATION.cff) for machine-readable citation.

## License

- **Data**: [CC-BY-4.0](LICENSE)

## Related

- [Open Admin Data](https://openadmindata.org) — Browse, search and explore administrative divisions for every country
- [open-admin-data](https://github.com/open-admin-data) — GitHub organization with all country repos
- [ListBase](https://www.listbase.org) — Structured reference data for every country
