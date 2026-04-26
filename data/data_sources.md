# TeleShift — Data Sources

All data is sourced from the Copernicus Climate Data Store (CDS):
https://cds.climate.copernicus.eu

---

## Variable 1: Total Precipitation

| Field | Value |
|---|---|
| Dataset | ERA5 hourly data on single levels |
| CDS ID | reanalysis-era5-single-levels |
| Variable | Total precipitation (tp) |
| Period | 1980–2020 |
| Months | DJF (Dec, Jan, Feb) and JJA (Jun, Jul, Aug) |
| Days | All |
| Time | 00:00 UTC |
| Resolution | 0.25° × 0.25° (native ERA5) |
| Format | NetCDF4 |
| File | data/raw/era5_precip_1980_2020_DJF_JJA.nc |
| Downloaded | 2026-04-22 |

---

## Variable 2: Geopotential at 500 hPa

| Field | Value |
|---|---|
| Dataset | ERA5 hourly data on pressure levels |
| CDS ID | reanalysis-era5-pressure-levels |
| Variable | Geopotential (z) at 500 hPa |
| Period | 1980–2020 |
| Months | DJF (Dec, Jan, Feb) and JJA (Jun, Jul, Aug) |
| Days | All |
| Time | 00:00 UTC |
| Resolution | 0.25° × 0.25° (native ERA5) |
| Format | NetCDF4 |
| File | data/raw/era5_z500_1980_2020_DJF_JJA.nc |
| Downloaded | 2026-04-22 |

---

## Why these variables?

**Total precipitation** is the core variable for constructing
extreme precipitation synchronization networks. It is used
directly in all three hypotheses (H1, H2, H3).

**Geopotential at 500 hPa (Z500)** is used for physical
interpretation only — it allows us to link the hub locations
identified in H2 and the long-distance links in H3 to known
atmospheric dynamics such as Rossby waves and jet streams.
Z500 does not enter the network construction pipeline.

---

## Why ERA5?

ERA5 is the standard reanalysis dataset in the climate network
literature. Key properties:

- Global coverage at 0.25° horizontal resolution
- Available from 1940 to present
- Freely accessible via CDS API
- Widely validated for extreme precipitation studies

---

## Why 1980–2020?

The 40-year period 1980–2020 provides:
- Sufficient extreme events per grid cell for robust
  event synchronization statistics
- Full overlap with the satellite era (post-1979),
  meaning ERA5 is better constrained by observations
- Consistency with comparable studies in the literature

---

## Why DJF and JJA?

DJF (December–January–February) and JJA (June–July–August)
are the standard boreal winter and summer seasons used across
the climate teleconnections literature. They represent the
most contrasting states of the atmospheric circulation:

- **JJA:** Dominated by tropical monsoon systems
- **DJF:** Dominated by extratropical jet streams and
  Rossby wave activity

Comparing these two seasons directly tests all three
TeleShift hypotheses.

---

## Licence

ERA5 data is provided under the Copernicus Licence:
https://cds.climate.copernicus.eu/licence-to-use-copernicus-products





---

## Reproducing the Data Download

Since raw data files are too large to host on GitHub, follow
these steps to reproduce the exact same download:

### Step 1 — Register
Create a free account at https://cds.climate.copernicus.eu

### Step 2 — Accept licences
Accept the terms of use for both datasets:
- https://cds.climate.copernicus.eu/datasets/reanalysis-era5-single-levels
- https://cds.climate.copernicus.eu/datasets/reanalysis-era5-pressure-levels

### Step 3 — Download Variable 1: Total Precipitation
Use these exact settings on the download form:

| Field | Value |
|---|---|
| Product type | Reanalysis |
| Variable | Total precipitation |
| Year | 1980 → 2026 |
| Month | January, February, June, July, August, December |
| Day | All |
| Time | 00:00 UTC |
| Geographical area | Whole available region |
| Data format | NetCDF4 |

Save the file as `data/raw/era5_precip_1980_2026_DJF_JJA.nc`

### Step 4 — Download Variable 2: Geopotential at 500 hPa
Use these exact settings on the download form:

| Field | Value |
|---|---|
| Product type | Reanalysis |
| Variable | Geopotential |
| Pressure level | 500 hPa |
| Year | 1980 → 2026 |
| Month | January, February, June, July, August, December |
| Day | All |
| Time | 00:00 UTC |
| Geographical area | Whole available region |
| Data format | NetCDF4 |

Save the file as `data/raw/era5_z500_1980_2026_DJF_JJA.nc`

### Step 5 — Verify
Run `notebooks/01_data_collection.ipynb` to confirm both
files are correctly formatted and complete.

---

## File sizes (approximate)

| File | Size |
|---|---|
| era5_precip_1980_2026_DJF_JJA.nc | ~10 GB |
| era5_z500_1980_2026_DJF_JJA.nc | ~8 GB |  