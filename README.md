# National Urban Concentration and CO₂ Emissions from Transport and Buildings: Panel Evidence from OECD Countries

Replication code for the bachelor thesis of Leonardo Gonnelli, University of St. Gallen (2026),
supervised by Prof. Dr. Despoina Makariou.

## Repository structure

```
├── code_urban_structure.Rproj   # RStudio project (sets the working directory via `here`)
├── .Rprofile                    # activates renv when the project is opened
├── renv.lock                    # exact package versions
├── renv/activate.R
├── data/
│   └── raw/                     # World Bank WDI exports
└── scripts/
    ├── 01_data_cleaning.qmd
    ├── 02_econometrics.qmd
    └── 03_figures.qmd
```

## How to reproduce

1. Open `code_urban_structure.Rproj` in RStudio.
2. Run `renv::restore()` once to install the exact package versions.
3. Run the scripts in the following order:
   - `scripts/01_data_cleaning.qmd`: imports the WDI series from `data/raw/`, restricts the
     sample to 35 OECD countries (2000–2019) and constructs the variables
     → `data/clean/cleaned_wdi_panel.csv`
   - `scripts/02_econometrics.qmd`: estimates all models and tests, and exports Tables 2–5
     and A1–A4 → `output/tables/`
   - `scripts/03_figures.qmd`: produces Figure 1 → `output/figures/`

The folders `data/clean/` and `output/` are created automatically.

## Software

R 4.5.1. Packages: tidyverse, here, plm, lmtest, sandwich, car, flextable, officer
(exact versions in `renv.lock`).

## Data

World Bank, World Development Indicators (version of July 13, 2026; downloaded on
September 10 and October 6, 2026). CO₂ emissions come from the EDGAR Community GHG Database
and urban concentration data from the UN World Urbanization Prospects 2018.
The data are licensed under CC BY 4.0.
