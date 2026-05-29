# South Sudan Administrative Divisions / South Sudan



## Overview

| Item | Details |
|------|---------|
| State | 10 |
| County | 79 |
| Payam | 512 |
| Coordinates | ✅ Included (all levels) |
| Formats | JSON, NDJSON, CSV |
| License | CC-BY-4.0 |
| Last Updated | 2026-05-29 |
| Website | [openadmindata.org/ss](https://openadmindata.org/ss/) |
| API | [openadmindata.org/api/ss](https://openadmindata.org/api/ss/) |

## Browse by State

| # | State | Countys | Payams | Link |
|---|----|----|----|------|
| 1 | Central Equatoria | 6 | 46 | [Browse](divisions/central-equatoria/) |
| 2 | Eastern Equatoria | 8 | 53 | [Browse](divisions/eastern-equatoria/) |
| 3 | Jonglei | 11 | 72 | [Browse](divisions/jonglei/) |
| 4 | Lakes | 8 | 50 | [Browse](divisions/lakes/) |
| 5 | Northern Bahr el Ghazal | 5 | 39 | [Browse](divisions/northern-bahr-el-ghazal/) |
| 6 | Unity | 9 | 73 | [Browse](divisions/unity/) |
| 7 | Upper Nile | 12 | 69 | [Browse](divisions/upper-nile/) |
| 8 | Warrap | 6 | 47 | [Browse](divisions/warrap/) |
| 9 | Western Bahr el Ghazal | 3 | 15 | [Browse](divisions/western-bahr-el-ghazal/) |
| 10 | Western Equatoria | 10 | 47 | [Browse](divisions/western-equatoria/) |

## Data Files

| File | Format | Description |
|------|--------|-------------|
| [all-state.json](data/all-state.json) | JSON | All 10 state records |
| [all-county.json](data/all-county.json) | JSON | All 79 county records |
| [all-payam.json](data/all-payam.json) | JSON | All 512 payam records |
| [all-flat.json](data/all-flat.json) | JSON | Levels 1-2 flat array |
| [all-flat.ndjson](data/all-flat.ndjson) | NDJSON | Streaming format |
| [all-flat.csv](data/all-flat.csv) | CSV | Spreadsheet format |
| [hierarchy.json](data/hierarchy.json) | JSON | Nested tree |
| [schema.json](data/schema.json) | JSON Schema | Data schema |

## Quick Start

### Python

```python
import json

with open("data/all-state.json", "r", encoding="utf-8") as f:
    data = json.load(f)

for r in data:
    print(f"{r['name']['local']} ({r['name']['en']}) — {r['children_count']['county']} countys")
```

### JavaScript

```javascript
import { readFileSync } from "fs";

const data = JSON.parse(readFileSync("data/all-state.json", "utf-8"));
console.log(`Total: ${data.length} states`);
```

## Schema

| Field | Type | Description |
|-------|------|-------------|
| `id` | string | Unique identifier |
| `level` | integer | 1=state, 2=county, 3=payam |
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
divisions/{state-slug}/
divisions/{state-slug}/{county-slug}/
```

Payams are listed inline in each county's README.

## AI Integration

- [llms.txt](docs/llms.txt) — Quick reference for AI agents
- [llms-full.txt](docs/llms-full.txt) — Summary with per-state links
- [Per-state data](docs/llms-full/) — Full data by state

## Citation

```
South Sudan Administrative Divisions Dataset (CC-BY-4.0)
URL: https://github.com/open-admin-data/south-sudan-administrative-divisions
```

See [CITATION.cff](CITATION.cff) for machine-readable citation.

## License

- **Data**: [CC-BY-4.0](LICENSE)

## Related

- [Open Admin Data](https://openadmindata.org) — Browse, search and explore administrative divisions for every country
- [open-admin-data](https://github.com/open-admin-data) — GitHub organization with all country repos
- [ListBase](https://www.listbase.org) — Structured reference data for every country
