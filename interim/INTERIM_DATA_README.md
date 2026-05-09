# Interim Data Folder

This folder contains partially cleaned, harmonised, and merged datasets created from the capstone project workbook.

The files in this folder preserve the transformation path between the original source files in `data/raw/` and the final model-ready datasets in `data/processed/`.

## Purpose

The interim data files support transparency and reproducibility by showing how UBEC-derived education indicators, NBS socioeconomic indicators, Budget Office allocation-context variables, and DMO fiscal-context variables were prepared before final processing and modelling.

## Source Workbook

The interim files in this folder were produced from:

```text
Capstone_Stage_ML1_Model_Ready_Dataset.xlsx
```

The main workbook sheets used were:

```text
Model_Ready_Core_StateYear
Model_Ready_Expanded_2022
```

## Files in This Folder

| File | Description | Source Sheet |
|---|---|---|
| `ubec_cleaned_interim.csv` | Cleaned UBEC-derived education infrastructure indicators used for BENI-Core modelling | `Model_Ready_Core_StateYear` |
| `nbs_cleaned_interim.csv` | Cleaned NBS-derived socioeconomic need proxy and school-age population fields used for BENI-Expanded | `Model_Ready_Expanded_2022` |
| `budget_cleaned_interim.csv` | Allocation-context file based on the available matching-grant variable in the project workbook | `Model_Ready_Core_StateYear` |
| `dmo_cleaned_interim.csv` | Cleaned DMO domestic debt and fiscal-pressure context fields | `Model_Ready_Expanded_2022` |
| `state_name_mapping.csv` | State-name harmonisation file generated from actual state labels across workbook sheets | All sheets with state labels |
| `merged_state_year_interim.csv` | Interim merged state-year dataset retaining 148 core rows and joining 2022 expanded/context fields where available | `Model_Ready_Core_StateYear`; `Model_Ready_Expanded_2022` |
| `INTERIM_DATA_README.md` | Explains the purpose, source, and contents of the interim data folder | Created for repository documentation |

## Dataset Coverage

The merged interim dataset contains:

```text
148 state-year rows
37 states including FCT
4 years: 2018, 2019, 2020, and 2022
```

The 2022 expanded dataset contributes:

```text
37 state-level rows
NBS socioeconomic need proxy
DMO domestic debt stock
Fiscal pressure band
BENI-Expanded target score and rank
```

## Data Handling Rule

- Raw source files remain unchanged in `data/raw/`.
- Interim files show cleaned, harmonised, and partially merged versions of the source data.
- Final model-ready datasets are stored in `data/processed/`.
- Output tables, charts, and model results are stored in `outputs/`.

## Notes

The interim files are not intended to replace the final processed datasets. They are included to demonstrate a clear and auditable data pipeline.

Budget Office variables were not available as a separate capital-budget table in the uploaded workbook. The available allocation-context variable was `matching_grant_million_naira`, which is retained in `budget_cleaned_interim.csv`.

DMO debt data are retained as fiscal-context variables and are not direct BENI inputs. BENI is designed to measure education infrastructure need, while DMO fields support fiscal-context interpretation.
