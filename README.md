# TeleShift

Seasonal comparison of extreme precipitation synchronization
networks using ERA5 reanalysis data and complex network analysis.

## Hypotheses

**H1 — Connectivity**
Extreme precipitation synchronization networks constructed from
boreal winter (DJF) data exhibit significantly higher global
connectivity — measured by mean node degree and link density —
than networks constructed from boreal summer (JJA) data.

**H2 — Hub Shift**
The geographic distribution of high-degree hub nodes in the
extreme precipitation synchronization network differs
significantly between boreal winter (DJF) and boreal summer
(JJA), with tropical monsoon regions dominating as hubs in
summer and extratropical regions emerging as hubs in winter.

**H3 — Long-range Links**
The proportion of long-distance links (>2500 km) in the extreme
precipitation synchronization network is significantly higher in
boreal winter (DJF) than in boreal summer (JJA), consistent
with stronger Rossby wave activity in the colder season.

## Tools

| Tool | Purpose |
|---|---|
| Python + xarray | Data loading and preprocessing |
| NetworkX | Network construction and analysis |
| Gephi | Network visualization |
| ERA5 (CDS) | Reanalysis climate data |

## Project Structure

```
TeleShift/
├── data/
│   ├── raw/              ← ERA5 .nc files (not tracked by git)
│   └── data_sources.md   ← full data documentation
├── notebooks/
│   ├── 01_data_collection.ipynb
│   ├── 02_network_construction.ipynb
│   ├── 03_analysis.ipynb
│   └── 04_visualization.ipynb
└── figures/              ← exported maps and plots
```

## Reproducing this project

1. Register at https://cds.climate.copernicus.eu
2. Download ERA5 data as described in `data/data_sources.md`
3. Run notebooks in order (01 → 04)

## Data

ERA5 reanalysis provided by ECMWF via the Copernicus Climate
Data Store. See `data/data_sources.md` for full details.
Period: 1980–2026.

## Context

NetSciSU Miniconference project.