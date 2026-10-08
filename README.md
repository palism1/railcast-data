# railcast-data

Raw and normalized GTFS-realtime snapshots for [railcast](https://github.com/palism1/railcast), committed every 5 minutes by `.github/workflows/collect.yml`.

| Path | Contents |
|---|---|
| `raw/YYYY-MM-DD/HHMM_<feed>.pb.gz` | Exact bytes received from each feed (UTC) |
| `parquet/YYYY-MM-DD/HHMM.parquet` | One row per (trip, stop) across all feeds, schema in `railcast.collect.normalize` |
| `logs/uptime/YYYY-MM-DD.csv` | One row per feed per run, failures included |
| `static/<agency>/<sha>.zip` + `static/manifest.csv` | Daily static GTFS checks, stored only when the content changes |

**Secrets:** `NJT_USERNAME` and `NJT_PASSWORD` enable NJ Transit. Without them the collector runs MTA-only.

**Terms:** MTA data is used under the MTA's developer terms. NJ Transit data is used under NJ Transit's developer agreement, stored and served from this repository, not from NJ Transit's servers. This project is not affiliated with or endorsed by either agency. Data may not be real time, accurate, or complete.
