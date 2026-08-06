# Homework 3 — CS193

**Exploring Real Weather Data from the Command Line**

A short Week 3 command-line exercise. You'll answer questions about a real weather
dataset entirely from the terminal — no spreadsheets, no other languages, just bash.

## The data

The data comes from [WHIN](https://www.whin.org/weather) (the Wabash Heartland
Innovation Network), which runs a dense network of weather stations across a
10-county region of north-central Indiana. This repo contains a **fixed snapshot**
of readings from 24 stations.

- `data/whin_stations.csv` — one row per station. Columns: `station_id`,
  `station_name`, `county`, `latitude`, `longitude`, `temp_f`, `humidity_pct`,
  `wind_mph`, `rain_in`, `soil_moist_pct`, `observed_at`.
- `data/station_logs/` — one log file per station, with that station's hourly readings.

## What's here

```
Homework-3-CS193/
├── assignment/
│   ├── CS193_Week3_Assignment.pdf   <- the handout (read this first)
│   └── CS193_Week3_Assignment.tex   <- LaTeX source
├── data/
│   ├── whin_stations.csv
│   └── station_logs/                <- 24 per-station log files
├── answers.txt                      <- write your answers here
└── README.md
```

## How to do the assignment

1. Open a terminal and `cd` into this folder (or the `data/` folder where the files live).
2. Work through the questions in `assignment/CS193_Week3_Assignment.pdf`, Part A then Part B.
3. For each question, run the command, read the output, and fill in `answers.txt`
   with the command you used, its output, and your short answer.
4. Submit `answers.txt` (renamed `week3_lastname.txt`) per your section's instructions.

You'll use: `ls`, `find`, `wc`, `head`, `tail`, `cut`, `grep`, `sort`, `uniq`, and pipes (`|`).

## Note

The dataset is a fixed sample so every answer stays stable over time. The data is
representative of WHIN's public weather network but is not a live feed.
