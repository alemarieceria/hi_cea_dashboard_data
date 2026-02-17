# Hawai'i CEA Dashboard Data Outputs

Data processing pipeline for the Hawai'i Coastal Ecosystem Accounting (CEA) dashboard. Currently transforms raw fisheries exchange value data into outputs for use in an interactive dashboard with choropleth maps, tables, and line plots.

## Project Structure

```
project_root/
├── data/
│   ├── 01_raw/          # Source data (not modified by code)
│   ├── 02_interim/      # Intermediate datasets
│   └── 03_processed/    # Analysis-ready outputs (date-stamped and by account)
├── notebooks/           # Processing notebooks
├── renv/                # R environment (managed by `{renv}`)
└── renv.lock            # Package versions
```

## Setup

1. Clone the repository.
2. Open the project in RStudio (or ensure the `.Rproj`/`.here` sentinel file is present at the root).
3. Run `renv::restore()` in the R console to install all dependencies at the correct versions.

## Notebooks

| Notebook | Description |
|----------|-------------|
| `notebooks/process_fisheries_ev_data.qmd` | Processes commercial and non-commercial fisheries exchange value data for MHI. See notebook header for full documentation. |

## Outputs

Processed data is exported to `data/03_processed/` in date-stamped and account subdirectories. Each output folder contains a README with a data dictionary, file descriptions, and dashboard usage instructions.

| Dataset | Reporting unit | Temporal coverage | Formats |
|---------|---------------|-------------------|---------|
| Commercial fisheries EV | DAR catch areas (82) | 1997--2021 | CSV, GeoPackage, GeoJSON |
| Non-commercial fisheries EV | Islands (6) | 2005--2022 | CSV, GeoPackage, GeoJSON |

Some processed spatial files exceed GitHub's file size limits and are not included in the repository. To generate them locally, run the corresponding notebook after completing the setup steps above.
