# AGENTS.md

**Project:** Climate Trends Analyzer  
**Last updated:** 2026-05-20  
**Maintainer:** Dr. Priya Sharma

---

## Project Overview

A Python toolkit for cleaning, normalising, and visualising historical climate station data from multiple public sources (NOAA, Copernicus, national meteorological agencies). Designed for reproducible research workflows.

**Tech stack:** Python 3.10+ + pandas + matplotlib + seaborn + Jupyter + pytest  
**Primary language:** Python  
**Entry points:** `notebooks/` (exploratory), `src/pipeline.py` (production pipeline)  
**Test command:** `pytest`

---

## Agent Behaviour Rules

### Do
- [ ] Read `data/README.md` before touching any raw datasets
- [ ] Document data transformations in `notebooks/` with explanatory text cells
- [ ] Save intermediate data to `data/interim/` with clear filenames
- [ ] Update `CODEX_HANDOFF.md` after each session
- [ ] Write tests for any new data-cleaning functions
- [ ] Prefer deterministic operations (set seeds, sort before groupby)

### Don't
- [ ] Download data that isn't from approved public sources
- [ ] Modify raw data in-place — always create derived copies
- [ ] Commit large data files to git (use DVC or exclude in `.gitignore`)
- [ ] Skip data validation steps
- [ ] Hardcode file paths — use `pathlib` and config files

---

## Project Conventions

### Directory structure

```
climate-trends/
  data/
    raw/              — Original data from sources (never modify)
    interim/          — Cleaned/transformed data
    processed/        — Final datasets for analysis
  notebooks/          — Jupyter notebooks (numbered: 01_explore, 02_clean, etc.)
  src/                — Python modules (functions, classes, pipelines)
  tests/              — pytest tests
  reports/            — Generated figures and summary reports
  config/             — YAML configuration files
```

### Naming conventions
- Notebooks: `01_explore_source_name.ipynb`, `02_clean_temperature.ipynb`
- Functions: `verb_noun` (e.g. `clean_temperature_data`, `plot_trend`)
- Data files: `{source}_{variable}_{start_year}_{end_year}.{ext}`
- Branches: `analysis/description`, `fix/description`

### Key dependencies
- `pandas` — Data manipulation
- `matplotlib` + `seaborn` — Plotting
- `pytest` — Testing
- `pyyaml` — Configuration management
- `jupyter` — Interactive analysis

### Environment setup

```bash
conda env create -f environment.yml
conda activate climate-trends
pytest
```

---

## Context Files

- `README.md` — Project overview and data sources
- `CODEX_HANDOFF.md` — Current session state
- `data/README.md` — Approved data sources and provenance
- `config/pipeline.yml` — Pipeline configuration (data paths, parameters)
- Notebooks in `notebooks/` — research context and decisions

---

## Current Priorities

1. Clean and merge NOAA temperature data with Copernicus reanalysis data
2. Identify and document station dropout patterns post-2010
3. Generate preliminary trend visualisations for report

---

## Known Issues

- Copernicus netCDF files are large and slow to parse — may need chunking
- NOAA station metadata has encoding issues in some older files
- Some stations have gaps > 5 years — interpolation strategy not yet decided

## Recent Decisions

- Using linear interpolation for gaps < 3 months; flagging longer gaps rather than interpolating
- All temperature units converted to Celsius at ingestion time
- Station metadata stored as CSV (simpler) rather than JSON (more structured)
