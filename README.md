# Lakeside City Council · 2026 Runoff Election — Turnout Dashboard


## Overview

An interactive early-voting turnout intelligence dashboard for the Lakeside City Council 2026 Runoff Election. The dashboard visualizes turnout patterns across 12 active precincts, with demographic breakdowns by gender, age group, and party affiliation, plus a daily voting pace trend and county-level comparison.

**Live Dashboard → [Open `lakeside_map.html`](lakeside_map.html)** *(no server required — fully self-contained)*

---

## Key Findings

| Metric | Value |
|---|---|
| Registered voters | 3,615 |
| Runoff voters (early, thru Jun 4) | 276 (7.63%) |
| May first-round turnout | 1,169 (32.3%) |
| Turnout drop vs. May | ↓ 76.4% |
| New runoff voters (skipped May) | 181 |
| May voters not yet back | 1,074 |

- **Highest-turnout precinct:** 880030 at 9.16% — Southfield county
- **Lowest-turnout precinct:** 880210 at 5.43% — 3.73 pt spread across the city
- **Age peak:** Voters 70–79 lead at 9.01%; under-40 voters lag at 7.17%
- **Party:** Green (10.19%) and Libertarian (9.00%) outperform Republican (8.43%) and Democrat voters in raw turnout rate
- **County:** Southfield (8.58%) edges Northgate (8.22%) — both above city avg
- **Vote method:** 79.7% in-person (220 votes) vs. 20.3% mail-in (56 votes)
- **Precincts 253 & 264 excluded** — no boundary geometry; 322 registered voters and 33 runoff voters affected

---

## Project Structure

```
├── lakeside_map.html         
├── precincts.geojson          
├── Notebook/
│   └── lakeside_analysis.ipynb  # Full analysis notebook
├── Data/
│   ├── registered_voters.csv
│   ├── first_round_may.csv
│   ├── northgate_early_inperson.csv
│   ├── southfield_early_inperson.xlsx
│   └── mail_ballots.xlsx
└── README.md
```

---

## Dashboard Features

- **Choropleth map** — Leaflet.js with CartoDB basemap; toggle between Runoff % and Runoff ÷ May ratio views; click any precinct for a detail panel
- **KPI row** — 5 headline metrics with color-coded accent cards
- **Demographics panel** — gender donut chart, top-3 party bar chart, 5-bin age group turnout
- **Votes by Day** — stacked bar (in-person + mail) with cumulative % trend line
- **County & Vote Method** — Northgate vs. Southfield comparison with city-avg reference marker; in-person vs. mail split

---

## How to View

1. Clone or download this repository
2. Open `lakeside_map.html` in any modern browser
3. No server, no install, no dependencies — everything is embedded

---

## Analysis Notebook

`Notebook/lakeside_analysis.ipynb` covers:

1. Data ingestion & standardization across 4 source files (CSV + XLSX)
2. Voter deduplication and precinct key mapping
3. Precinct-level turnout calculation
4. KPI summary
5. Demographic analysis — gender, age, party
6. Party composition per precinct
7. Precinct runoff vs. first-round comparison
8. Subdivision analysis

**Stack:** Python · pandas · geopandas · matplotlib · Jupyter

---

## Dashboard Tech Stack

| Library | Version | Purpose |
|---|---|---|
| Leaflet.js | 1.9.4 | Interactive choropleth map |
| Chart.js | 4.4.0 | Bar, donut, and line charts |
| chartjs-plugin-datalabels | 2.2.0 | Direct bar value labels |
| chartjs-plugin-annotation | 3.0.1 | City-average reference lines |

---
