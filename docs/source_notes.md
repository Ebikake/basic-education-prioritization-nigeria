# Source Notes

This document records the source categories used in the capstone project and their analytical roles.

## Source Categories

| Source | Role in the Study | Repository Location |
|---|---|---|
| Universal Basic Education Commission (UBEC) | Core education infrastructure indicators: enrolment, schools, teachers, classrooms, classroom condition, and matching-grant context | `data/raw/ubec/`; `data/interim/ubec_cleaned_interim.csv`; `data/processed/beni_core_model_ready.csv` |
| National Bureau of Statistics (NBS) | Socioeconomic and demographic indicators used to create the socioeconomic need proxy | `data/raw/nbs/`; `data/interim/nbs_cleaned_interim.csv`; `data/processed/beni_expanded_2022_model_ready.csv` |
| Budget Office of the Federation | Public capital-budget and allocation-context evidence | `data/raw/budget_office/`; `data/interim/budget_cleaned_interim.csv` |
| Debt Management Office (DMO) | State domestic debt and fiscal-pressure context | `data/raw/dmo/`; `data/interim/dmo_cleaned_interim.csv` |
| UNICEF Nigeria | Supplementary education deprivation and access context | Report literature and source notes |
| UNESCO | Supplementary education equity and governance context | Report literature and source notes |
| World Bank Nigeria | Supplementary education financing and human-capital context | Report literature and source notes |

## Data Handling Notes

- Raw files are retained unchanged in `data/raw/`.
- Cleaned intermediate files are stored in `data/interim/`.
- Final analytical datasets are stored in `data/processed/`.
- Model tables, figures, and workbooks are stored in `outputs/`.

## Interpretation Notes

UBEC and NBS variables are used directly in the BENI analytical framework. Budget Office and DMO variables are retained for fiscal and allocation context and are not direct BENI inputs.
