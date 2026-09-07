# Clone Hero Score Exporter

Parses Clone Hero's `scoredata.bin`, `scoresext.bin`, and `songcache.bin` into
`scores.json` and `scores.xlsx`.

**Requires openpyxl** for excel output

## Setup / run

Open `main.py` and edit `DEFAULT_CH_DIR` with your install loc (username edit is enough for most windows installs):

`DEFAULT_CH_DIR` = `r"C:\Users\[user]\AppData\LocalLow\srylain Inc_\Clone Hero"`

Save the file and run!

## Output

**scores.xlsx** - two tabs:

- **Clone Hero Scores** - one row per song/instrument/difficulty you've
  scored, for songs actively in your library.
- **Playtime** - every played song, including those no longer in your
  library (shown as `(Unknown - checksum)`), since those still count
  toward total time played.

**scores.json** - the same combined data as a raw dict, keyed by song
checksum.

## Notes

- **Percentage** shows `FC` for a full-combo value (`356`)
- **Time Played** is a cumulative stat from `scoresext.bin`; 
- **Avg Duration** divides Time PLayed by Plays as a rough per-run estimate - it
  can run short if some plays were quit early/restarted.
