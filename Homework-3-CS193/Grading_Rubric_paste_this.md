# CS193 — Week 3 Grading Rubric (100 pts, +5 bonus)

**How to grade each item:** *full* credit = correct command **and** correct result; *half* credit = right approach with a minor error (wrong flag, off-by-one, header not skipped); *zero* = missing or unrelated. All answers come from the fixed data files, so they do not change over time.

### Part A — Finding your way around (40 pts)

| Item | What it tests | Full-credit answer | Pts |
|------|---------------|--------------------|-----|
| A1 | `ls \| wc -l` | 24 log files | 10 |
| A2 | `find` searches sub-folders | 25 CSV files total | 10 |
| A3 | `find` with name pattern `TIP*` | 3 files: TIP01, TIP02, TIP03 | 10 |
| A4 | `find` with name pattern `WHI*` | 3 files: WHI01, WHI02, WHI03 | 10 |

### Part B — Pipes & filters (50 pts)

| Item | What it tests | Full-credit answer | Pts |
|------|---------------|--------------------|-----|
| B1 | `head`; spotting the header | First line is the header row | 8 |
| B2 | `tail -n +2 \| wc -l` | 24 stations | 8 |
| B3 | `cut -d, -f2` | Station-name column printed | 8 |
| B4 | `grep -c` | 3 in Tippecanoe County | 8 |
| B5 | `cut \| sort \| uniq -c` | Per-county counts (Cass/Clinton/Tippecanoe/White = 3; rest = 2) | 10 |
| B6 | `sort -t, -k6 -n \| head -1` | Covington (Fountain), 80.0°F | 8 |

### Submission quality & reflection (10 pts)

| What it tests | Full-credit answer | Pts |
|---------------|--------------------|-----|
| Commands + outputs pasted, file named right | Readable `week3_lastname.txt` with each command and its output | 5 |
| Reflection with reasoning | Names a top county (tie of 3 is fine) and cites `sort \| uniq -c` as the method | 5 |

### Bonus (+5)

| What it tests | Full-credit answer | Pts |
|---------------|--------------------|-----|
| Single command line: `grep \| cut` | `grep White whin_stations.csv \| cut -d, -f2` → Monticello, Brookston, Reynolds | +5 |

**Total: 100 points (+5 bonus)**

Letter bands: A 90–100 · B 80–89 · C 70–79 · D 60–69 · F < 60
