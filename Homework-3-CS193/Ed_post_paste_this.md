# CS193 — Week 3 Homework: Exploring Real Weather Data from the Command Line

**Time:** 15–20 minutes  **Reading:** *The Linux Command Line* (linuxcommand.org/tlcl.php) — the chapters on navigation and I/O redirection.

**Data source:** The WHIN (Wabash Heartland Innovation Network) weather network runs a dense set of weather stations across a 10-county region of north-central Indiana. The attached files hold a snapshot of readings from 24 of those stations.

**Skills:** finding files (`find`, `ls`) and pipes & filters (`head`, `cut`, `grep`, `sort`, `uniq`, `wc`).

## Setup

Download **cs193_week3.zip** (attached below) and unzip it. Inside you'll find:

- `whin_stations.csv` — one row per station (the current snapshot)
- `station_logs/` — one file per station, with hourly readings

Open a terminal and move into the folder before you start:

```bash
cd cs193_week3
```

## Part A — Finding your way around (~7 min)

Every station writes its own log file. Let's locate them.

**A1.** List the log files, then count them. How many stations logged data today?

```bash
ls station_logs
ls station_logs | wc -l
```

**A2.** Now count *every* CSV file in the folder, including the snapshot. `find` searches inside sub-folders for you.

```bash
find . -name "*.csv" | wc -l
```

**A3.** WHIN's Tippecanoe County stations all start with `TIP`. List just those log files.

```bash
find station_logs -name "TIP*"
```

**A4.** Print the full path of every **White County** log file (their IDs start with `WHI`).

```bash
find station_logs -name "WHI*"
```

## Part B — Reading the data with pipes & filters (~10 min)

Work with the snapshot file `whin_stations.csv`. The columns are: `station_id, station_name, county, latitude, longitude, temp_f, humidity_pct, wind_mph, rain_in, soil_moist_pct, observed_at`.

**B1.** Peek at the first 5 lines. What does the very first line contain?

```bash
head -5 whin_stations.csv
```

**B2.** How many stations are in the snapshot? The header row is not a station, so skip it with `tail -n +2` ("start at line 2").

```bash
tail -n +2 whin_stations.csv | wc -l
```

**B3.** Print just the station names (column 2). The file is comma-separated, so tell `cut` the delimiter is a comma.

```bash
cut -d, -f2 whin_stations.csv
```

**B4.** How many stations are in **Tippecanoe** County? `grep -c` counts matching lines.

```bash
grep -c Tippecanoe whin_stations.csv
```

**B5.** Count how many stations are in *each* county. Chain four tools: take the county column, sort it, then collapse duplicates with a count.

```bash
tail -n +2 whin_stations.csv | cut -d, -f3 | sort | uniq -c
```

**B6.** Which station is the **coolest** right now? Temperature is column 6. Sort the rows numerically by that column and take the first one.

```bash
tail -n +2 whin_stations.csv | sort -t, -k6 -n | head -1
```

## Challenge (optional)

Write a **single command line** that prints only the station names in **White** County. Hint: `grep` to pick the rows, then pipe into `cut` to keep the name column.

## What to submit

Reply to this thread (or submit the file, per your section's instructions) with a plain-text file `week3_lastname.txt` containing each command you ran and its output, plus one sentence answering: **"Which county has the most stations, and how did you find out?"**
