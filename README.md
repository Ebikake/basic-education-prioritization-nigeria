Yes. Below is the updated README content, refined to reflect the files now uploaded and to clarify that the **project workbook is uploaded**, while the **external raw source files from UBEC/NBS/Budget Office/DMO were not uploaded**. This updates the repository structure and data-source explanation from the pasted README draft. 

````markdown
# A Data-Driven Framework for Prioritizing Public Capital Allocation to Basic Education Infrastructure across Nigerian States Using Education Need Indicators

## Project Overview

This repository contains the datasets, notebooks, model outputs, figures, tables, and documentation for a data analytics capstone project focused on basic education infrastructure prioritization in Nigeria.

The project develops a transparent, reproducible, and evidence-based decision-support framework for ranking Nigerian states by relative basic education infrastructure need. The central analytical output is the **Basic Education Need Index (BENI)**, a composite index designed to support public capital allocation decisions across Nigeria’s 36 states and the Federal Capital Territory.

Two versions of BENI are developed:

- **BENI-Core**: constructed from UBEC-derived education and infrastructure-pressure indicators.
- **BENI-Expanded**: extends BENI-Core by adding an NBS-derived socioeconomic need proxy.

The project also uses regression-based machine-learning models to validate whether the BENI scores and rankings can be reproduced from the selected indicators.

## Research Questions

The project is guided by the following research questions:

1. Which indicators are most relevant for assessing relative basic education infrastructure need across Nigerian states?

2. How can these indicators be standardized and combined into a composite Basic Education Need Index?

3. How can Nigerian states be prioritized for capital allocation using BENI?

4. How does BENI-based prioritization compare with equal and population-based allocation approaches?

5. How well can regression-based machine-learning models reproduce BENI-Core and BENI-Expanded scores and rankings?

## Data Sources

The project uses secondary data from official and credible public sources.

| Source | Purpose in the Study |
|---|---|
| Universal Basic Education Commission (UBEC) | Education indicators on enrolment, schools, teachers, classrooms, infrastructure condition, and matching grants |
| UBEC Reports / Document Library | Annual reports, personnel audit reports, and education-sector documents |
| National Bureau of Statistics (NBS) | Socioeconomic and demographic indicators for the socioeconomic need proxy |
| NBS eLibrary | Poverty, population, deprivation, and related statistical publications |
| Budget Office of the Federation | Federal education and Universal Basic Education capital-budget context |
| Debt Management Office (DMO) | State domestic debt data for fiscal-pressure context |
| UNICEF Nigeria | Supplementary evidence on education access, deprivation, and child vulnerability |
| UNESCO | Supplementary education governance, equity, and global education monitoring context |
| World Bank Nigeria | Supplementary education financing and human-capital policy context |

## Raw Data Access Note

The primary project workbook used for this capstone project has been uploaded to the repository:

```text
data/raw/Capstone_Stage_ML1_Model_Ready_Dataset.xlsx
````

This workbook contains the model-ready datasets and supporting sheets used to generate the interim cleaned datasets, processed datasets, model outputs, figures, and documentation included in the repository.

However, the original external raw source files downloaded from UBEC, NBS, the Budget Office of the Federation, and DMO were **not uploaded** to this repository. Those external source files are retained locally as source evidence because some raw files may be large, externally hosted, or not required for reproducing the current interim analysis from the uploaded model-ready workbook.

The uploaded workbook and derived repository files are sufficient to reproduce the interim analysis and model validation reported in the capstone document. Full source-level audit verification should consult the original external UBEC, NBS, Budget Office, and DMO files separately.

## Repository Structure

```text
basic-education-prioritization-nigeria/
├── README.md
├── .gitignore
├── requirements.txt
├── data/
│   ├── raw/
│   │   └── Capstone_Stage_ML1_Model_Ready_Dataset.xlsx
│   ├── interim/
│   │   ├── INTERIM_DATA_README.md
│   │   ├── ubec_cleaned_interim.csv
│   │   ├── nbs_cleaned_interim.csv
│   │   ├── budget_cleaned_interim.csv
│   │   ├── dmo_cleaned_interim.csv
│   │   ├── state_name_mapping.csv
│   │   └── merged_state_year_interim.csv
│   └── processed/
│       ├── PROCESSED_DATA_README.md
│       ├── integrated_state_year_dataset.csv
│       ├── beni_core_model_ready.csv
│       ├── beni_expanded_2022_model_ready.csv
│       ├── beni_core_scores.csv
│       ├── beni_expanded_scores.csv
│       ├── allocation_comparison_outputs.csv
│       └── final_dataset_dictionary.csv
├── notebooks/
│   ├── 01_data_cleaning_and_integration.ipynb
│   ├── 02_beni_index_construction.ipynb
│   ├── 03_model_training_and_validation.ipynb
│   └── 04_visualisations_and_outputs.ipynb
├── outputs/
│   ├── tables/
│   │   ├── appendix_b_beni_expanded_model_ready_preview.csv
│   │   ├── appendix_b_processed_dataset_preview.csv
│   │   ├── cleaning_summary.csv
│   │   ├── coefficient_importance_beni_expanded.csv
│   │   ├── core_model_performance.csv
│   │   ├── core_model_predictions.csv
│   │   ├── dataset_components_summary.csv
│   │   ├── expanded_beni_ranking_comparison.csv
│   │   ├── expanded_model_performance.csv
│   │   ├── expanded_model_predictions.csv
│   │   ├── model_summary.csv
│   │   ├── output_log.csv
│   │   ├── sample_size_assessment.csv
│   │   └── top_10_priority_states.csv
│   ├── figures/
│   │   ├── figure_c1_core_model_rmse.png
│   │   ├── figure_c2_expanded_model_rmse.png
│   │   ├── figure_c3_actual_vs_predicted_beni_expanded.png
│   │   ├── figure_c4_top_10_predicted_priority_states.png
│   │   └── figure_c5_coefficient_importance_beni_expanded.png
│   └── model_results/
│       ├── Capstone_ML_Model_Results_Workbook.xlsx
│       └── best_model_summary.txt
└── docs/
    ├── CapstoneProject.html
    ├── appendix_screenshot_log.md
    ├── data_dictionary.xlsx
    ├── literature_relevance_matrix.xlsx
    ├── methodology_notes.md
    ├── rubric_compliance_checklist.md
    └── source_notes.md
```

## Methodology Summary

The project follows a structured data analytics workflow:

1. **Data Acquisition**
   Publicly available education, socioeconomic, budget, and fiscal-context data were reviewed from UBEC, NBS, the Budget Office of the Federation, DMO, and supplementary policy sources. The uploaded project workbook consolidates the model-ready data used for the current interim analysis.

2. **Data Cleaning and Harmonisation**
   Source fields were cleaned and harmonised into interim datasets. Key cleaning tasks included state-name standardisation, numeric conversion, missing-value review, duplicate handling, and validation of derived ratios.

3. **Dataset Integration**
   Cleaned datasets were merged into a state-year framework covering Nigerian states and the Federal Capital Territory.

4. **Feature Engineering**
   Education infrastructure-pressure indicators were derived, including pupil-teacher ratio, pupil-classroom ratio, unqualified-teacher share, bad-classroom share, and enrolment per school.

5. **BENI Construction**
   Indicators were standardized and combined into two composite index versions:

   * BENI-Core
   * BENI-Expanded

6. **State Prioritization**
   States were ranked by relative infrastructure need using BENI scores.

7. **Allocation Comparison**
   BENI-based prioritization was compared with simpler allocation approaches, including equal allocation and population-based allocation.

8. **Machine-Learning Validation**
   Regression models were trained to assess whether BENI scores and rankings could be reproduced from the selected indicators.

## Model Summary

The modelling stage validates BENI reproducibility and ranking stability. Since BENI scores are continuous index values, regression models were used.

| Model                       | Purpose                                               |
| --------------------------- | ----------------------------------------------------- |
| Linear Regression           | Baseline model for reproducing engineered BENI scores |
| Ridge Regression            | Regularized linear model for stability testing        |
| Random Forest Regressor     | Nonlinear robustness check                            |
| Gradient Boosting Regressor | Ensemble-based robustness check                       |

Two modelling workflows were used:

| Dataset               | Target                       | Validation Strategy                  |
| --------------------- | ---------------------------- | ------------------------------------ |
| BENI-Core dataset     | `target_beni_core_score`     | Train on 2018–2020; test on 2022     |
| BENI-Expanded dataset | `target_beni_expanded_score` | 5-fold cross-validation on 2022 data |

The main evaluation metrics include:

* Mean Absolute Error (MAE)
* Root Mean Squared Error (RMSE)
* R-squared (R²)
* Spearman rank correlation
* Top-10 overlap
* Rank difference

The modelling results show that Linear Regression and Ridge Regression reproduce BENI scores most accurately because BENI is an engineered composite index derived from the selected indicators. The results should therefore be interpreted as evidence of internal consistency and reproducibility, not as causal prediction.

## Key Outputs

| Output                        | Description                                                                                                   |
| ----------------------------- | ------------------------------------------------------------------------------------------------------------- |
| Integrated state-year dataset | Analytical dataset combining education, socioeconomic, budget/allocation-context, and debt-context indicators |
| BENI-Core scores              | Composite index based on UBEC-derived education and infrastructure-pressure indicators                        |
| BENI-Expanded scores          | Composite index combining BENI-Core indicators with socioeconomic need                                        |
| State priority rankings       | Ranking of Nigerian states by relative basic education infrastructure need                                    |
| Allocation comparison outputs | Comparison of BENI-based prioritization with equal and population-based approaches                            |
| Model performance tables      | Regression validation results for BENI-Core and BENI-Expanded                                                 |
| Ranking validation tables     | Actual versus predicted BENI-Expanded rankings                                                                |
| Visualisations                | RMSE charts, actual-versus-predicted plot, top-10 priority-state chart, and coefficient-importance chart      |
| Model results workbook        | Consolidated Excel workbook containing model outputs and validation evidence                                  |

The top 10 BENI-Expanded priority states identified at the interim stage are:

1. Katsina
2. Yobe
3. Borno
4. Sokoto
5. Kebbi
6. Zamfara
7. Imo
8. Kano
9. Kaduna
10. Bauchi

## How to Reproduce the Analysis

To reproduce the analysis, follow these steps.

### 1. Clone the Repository

```bash
git clone https://github.com/YOUR-USERNAME/basic-education-prioritization-nigeria.git
cd basic-education-prioritization-nigeria
```

### 2. Create a Python Environment

```bash
python -m venv .venv
```

Activate the environment.

On Windows:

```bash
.venv\Scripts\activate
```

On macOS or Linux:

```bash
source .venv/bin/activate
```

### 3. Install Required Libraries

```bash
pip install -r requirements.txt
```

### 4. Run the Notebooks in Order

```text
notebooks/01_data_cleaning_and_integration.ipynb
notebooks/02_beni_index_construction.ipynb
notebooks/03_model_training_and_validation.ipynb
notebooks/04_visualisations_and_outputs.ipynb
```

### 5. Review Processed Data

The final processed datasets are stored in:

```text
data/processed/
```

Important files include:

```text
integrated_state_year_dataset.csv
beni_core_model_ready.csv
beni_expanded_2022_model_ready.csv
beni_core_scores.csv
beni_expanded_scores.csv
allocation_comparison_outputs.csv
```

### 6. Review Output Tables

Model and analysis tables are stored in:

```text
outputs/tables/
```

### 7. Review Figures

Generated figures are stored in:

```text
outputs/figures/
```

### 8. Review Model Workbook

The consolidated model results workbook is stored in:

```text
outputs/model_results/Capstone_ML_Model_Results_Workbook.xlsx
```

### 9. Review Documentation

Supporting documentation is stored in:

```text
docs/
```

Key documents include:

```text
data_dictionary.xlsx
source_notes.md
methodology_notes.md
literature_relevance_matrix.xlsx
CapstoneProject.html
rubric_compliance_checklist.md
appendix_screenshot_log.md
```

## Author

Ebikake John
MSc Artificial Intelligence and Machine Learning
QM640 Data Analytics Capstone
Walsh College
May 2026

```
```
