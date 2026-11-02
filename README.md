# RF4 Companion Data

Anonymised record data from Russian Fishing 4, collected for [RF4 Companion](https://github.com/Nalathan01/rf4-companion). Player names are never included; each entry only carries a short salted hash so duplicates can be told apart.

## Contents

### `archive/`

Weekly records of all 11 regions, refreshed several times a day, with extra runs in the hours after the Sunday reset.

| Table | Code |
|---|---|
| Records | `n` |
| Records light | `l` |
| Bottom light | `b` |
| Ultralight | `u` |
| Sea | `m` |
| Telescopic | `t` |

- `week_<Sunday>.json.gz`: one finished week.
- `delta_<Sunday>_<time>.json.gz`: new entries of the running week, merged into the week file once it is finished.
- `absolute_<year>.json.gz`: the official records of that year for every region and table, table codes in upper case.
- `state.json`: status of the last collector run.

Fields per entry: `f` fish, `w` weight in grams, `loc` waterbody, `b` bait (several parts separated by `;`), `d` date as shown in game, `r` region, `t` table, `fs` / `ls` first and last time the entry was seen (UTC), `k` unique key.

### `history/`

`baits_<YYYY-MM>.json.gz`: monthly bait summary per fish and waterbody, built from all files in `archive/`. Columns: fish, waterbody, bait, number of records, biggest weight in grams, tables. Used by an upcoming bait history feature.

### `shared/`

Fishing spots that RF4 Companion users chose to share.

## Sources

- Official record tables on [rf4game.com](https://rf4game.com)
- Telescopic records from [rf4.fish](https://rf4.fish)

All files are gzip compressed JSON. Please credit the sources above if you use the data.
