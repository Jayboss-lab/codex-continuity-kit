# GOAL_PROMPT.md

**Date:** 2026-05-19  
**Project:** Climate Trends Analyzer  
**Session:** 7  
**Priority:** HIGH

---

## Goal

Create a reusable Python module (`src/cleaning/noaa_ghcn.py`) that cleans NOAA GHCN daily temperature data for a given region, merges with station metadata, flags data gaps, and outputs analysis-ready CSV.

---

## Background

The Climate Trends Analyzer needs standardised temperature data from multiple sources. NOAA GHCN is the first source. Raw data has quality flags, missing values, and needs to be joined with station metadata. This module will be reused for other regions and variables later.

---

## Acceptance Criteria

- [ ] `clean_daily_temperature()` function reads raw GHCN daily files and returns cleaned DataFrame
- [ ] Quality flags G (good) and blank are kept; flags S (suspect), I (interpolated), and others are excluded
- [ ] Values converted from tenths-of-degrees-C to proper degrees C (divide by 10)
- [ ] `flag_gaps()` identifies gaps ≥ 90 days and adds `gap_flag` column
- [ ] `merge_station_metadata()` joins on 11-char station ID with metadata file
- [ ] 6+ pytest tests covering: nulls, flag filtering, gap detection, metadata join, edge cases
- [ ] Notebook `01_explore_noaa.ipynb` updated with data quality summary
- [ ] `config/pipeline.yml` updated with NOAA GHCN parameters

---

## Constraints

- Do not modify raw data files in-place
- Do not commit large data files or generated CSVs to git
- Use `pathlib` for all file paths
- Keep functions pure where possible (input DataFrame → output DataFrame)
- Follow existing `src/` module structure

---

## Context

- `data/raw/noaa/` — raw GHCN data (already present)
- `notebooks/01_explore_noaa.ipynb` — exploration notebook with data structure notes
- `src/cleaning/` — target directory for cleaning module
- `tests/cleaning/` — target directory for tests
- `config/pipeline.yml` — pipeline configuration

---

## Expected Output

- `src/cleaning/noaa_ghcn.py`
- `tests/cleaning/test_noaa_ghcn.py`
- Updated `notebooks/01_explore_noaa.ipynb`
- Updated `config/pipeline.yml`
- Generated `data/interim/noaa_ghcn_cleaned.csv` (excluded from git)

---

## Out of Scope

- Copernicus ERA5 ingestion (separate task)
- Trend analysis or visualisation (separate task)
- Station move handling (needs literature review first)
- Elevation correction (needs domain expertise)

---

## Time Estimate

- Expected: 2–3 hours
- Hard stop: Stop after 4 hours and hand off. Core functions should be testable even if polish is missing.

---

## Notes

- NOAA fixed-width format specs are documented in `docs/NOAA_GHCN_Daily_Documentation.pdf`. Column widths matter — double-check if parser fails.
- Some stations may have no valid data after flag filtering. This is expected — document it in the notebook.
- Gap detection should respect the temporal order of records. Sort by date before detecting gaps.
