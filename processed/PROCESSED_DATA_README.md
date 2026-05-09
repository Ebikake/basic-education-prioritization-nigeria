# Processed Data Folder

This folder contains the final cleaned, integrated, score-ready, and model-ready datasets used in the capstone analysis.

These files are the final analytical datasets derived from the project workbook and should be used for report tables, modelling, validation, prioritization, and repository evidence.

## Source Workbook

The processed files in this folder were produced from:

```text
Capstone_Stage_ML1_Model_Ready_Dataset.xlsx
```

The main workbook sheets used were:

```text
Model_Ready_Core_StateYear
Model_Ready_Expanded_2022
Feature_Dictionary
```

## Files in This Folder

| File | Description | Main Use |
|---|---|---|
| `integrated_state_year_dataset.csv` | Final integrated state-year dataset combining BENI-Core rows with 2022 expanded/context fields where available | Overall processed dataset evidence |
| `beni_core_model_ready.csv` | Final BENI-Core model-ready dataset with 148 state-year observations | Core model training and 2022 holdout validation |
| `beni_expanded_2022_model_ready.csv` | Final BENI-Expanded 2022 model-ready dataset with 37 state-level observations | Expanded 5-fold cross-validation and ranking validation |
| `beni_core_scores.csv` | Final BENI-Core scores, ranks, and priority bands | Core prioritization and within-year ranking |
| `beni_expanded_scores.csv` | Final BENI-Expanded scores, ranks, and contextual fields | Expanded prioritization and top-priority state analysis |
| `allocation_comparison_outputs.csv` | Comparison of equal allocation, population-based allocation, BENI-Expanded allocation, and matching-grant benchmark shares | Allocation-comparison analysis |
| `final_dataset_dictionary.csv` | Final feature dictionary exported from the workbook | Data dictionary and reproducibility evidence |
| `PROCESSED_DATA_README.md` | Explains the processed-data folder and each file | Repository documentation |

## Dataset Coverage

### BENI-Core Model-Ready Dataset

```text
Rows: 148
States: 37 including FCT
Years: 2018, 2019, 2020, and 2022
Missing values: 0
```

This dataset supports the core machine-learning workflow:

```text
Train: 2018, 2019, and 2020
Test: 2022 holdout set
```

### BENI-Expanded Model-Ready Dataset

```text
Rows: 37
States: 37 including FCT
Year: 2022
Missing values: 0
```

This dataset supports the expanded workflow:

```text
5-fold cross-validation
BENI-Expanded ranking validation
Top-10 priority-state analysis
```

## Key Analytical Variables

Important variables include:

```text
target_beni_core_score
target_beni_expanded_score
beni_rank_within_year
beni_expanded_rank
pupil_teacher_ratio
pupil_classroom_ratio
unqualified_teacher_share
bad_classroom_share
enrolment_per_school
nbs_socioeconomic_need_proxy
school_age_basic_population
dmo_domestic_debt_stock_naira
matching_grant_2018_2022_naira
```

## Allocation Comparison Logic

The file `allocation_comparison_outputs.csv` compares four allocation perspectives:

| Allocation Method | Basis |
|---|---|
| Equal allocation | Identical share for each state |
| Population-based allocation | Share based on school-age basic population |
| BENI-Expanded allocation | Share based on BENI-Expanded need score |
| Matching-grant benchmark | Historical/contextual matching-grant share |

The allocation shares are comparative decision-support outputs. They are not final government allocation decisions.

## Data Handling Rule

- Raw source files remain unchanged in `data/raw/`.
- Interim files are stored in `data/interim/`.
- Final processed and model-ready datasets are stored in this folder.
- Output tables, figures, and model workbooks are stored in `outputs/`.

## Notes

The processed datasets are suitable for use in the capstone report, appendices, GitHub repository evidence, and reproducibility checks.

BENI should be interpreted as a transparent composite need index. Machine-learning models are used to validate score reproducibility and ranking stability, not to establish causal effects.
