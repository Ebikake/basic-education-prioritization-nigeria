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

## Repository Structure

```text
basic-education-prioritization-nigeria/
├── README.md
├── .gitignore
├── LICENSE
├── data/
│   ├── raw/
│   │   ├── ubec/
│   │   │   ├── reports/
│   │   │   └── .gitkeep
│   │   ├── nbs/
│   │   │   └── .gitkeep
│   │   ├── budget_office/
│   │   │   └── .gitkeep
│   │   └── dmo/
│   │       └── .gitkeep
│   ├── interim/
│   │   ├── ubec_cleaned_interim.csv
│   │   ├── nbs_cleaned_interim.csv
│   │   ├── budget_cleaned_interim.csv
│   │   ├── dmo_cleaned_interim.csv
│   │   └── merged_state_year_interim.csv
│   └── processed/
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
│   │   ├── core_model_performance.csv
│   │   ├── expanded_model_performance.csv
│   │   ├── expanded_beni_ranking_comparison.csv
│   │   ├── top_10_priority_states.csv
│   │   ├── coefficient_importance_beni_expanded.csv
│   │   ├── sample_size_assessment.csv
│   │   └── cleaning_summary.csv
│   ├── figures/
│   │   ├── figure_c1_core_model_rmse.png
│   │   ├── figure_c2_expanded_model_rmse.png
│   │   ├── figure_c3_actual_vs_predicted_beni_expanded.png
│   │   ├── figure_c4_top_10_predicted_priority_states.png
│   │   ├── figure_c5_coefficient_importance_beni_expanded.png
│   │   ├── figure_b1_processed_dataset_preview.png
│   │   ├── figure_b2_repository_folder_structure.png
│   │   └── figure_b3_beni_expanded_model_ready_preview.png
│   └── model_results/
│       └── Capstone_ML_Model_Results_Workbook.xlsx
└── docs/
    ├── data_dictionary.xlsx
    ├── source_notes.md
    ├── methodology_notes.md
    ├── literature_relevance_matrix.xlsx
    ├── CapstoneProject.html
    ├── rubric_compliance_checklist.md
    └── appendix_screenshot_log.md
Methodology Summary
The project follows a structured data analytics workflow:
1.	Data Acquisition
Publicly available education, socioeconomic, budget, and fiscal-context data were collected from UBEC, NBS, the Budget Office of the Federation, DMO, and supplementary policy sources.
2.	Data Cleaning and Harmonisation
Source files were cleaned separately. Key cleaning tasks included state-name standardisation, numeric conversion, missing-value review, duplicate handling, and validation of derived ratios.
3.	Dataset Integration
Cleaned datasets were merged into a state-year framework covering Nigerian states and the Federal Capital Territory.
4.	Feature Engineering
Education infrastructure-pressure indicators were derived, including pupil-teacher ratio, pupil-classroom ratio, unqualified-teacher share, bad-classroom share, and enrolment per school.
5.	BENI Construction
Indicators were standardized and combined into two composite index versions:
o	BENI-Core
o	BENI-Expanded
6.	State Prioritization
States were ranked by relative infrastructure need using BENI scores.
7.	Allocation Comparison
BENI-based prioritization was compared with simpler allocation approaches, including equal allocation and population-based allocation.
8.	Machine-Learning Validation
Regression models were trained to assess whether BENI scores and rankings could be reproduced from the selected indicators.
Model Summary
The modelling stage validates BENI reproducibility and ranking stability. Since BENI scores are continuous index values, regression models were used.
The models include:
Model	Purpose
Linear Regression	Baseline model for reproducing the engineered BENI scores
Ridge Regression	Regularized linear model for stability testing
Random Forest Regressor	Nonlinear robustness check
Gradient Boosting Regressor	Ensemble-based robustness check
Two modelling workflows were used:
Dataset	Target	Validation Strategy
BENI-Core dataset	target_beni_core_score	Train on 2018–2020; test on 2022
BENI-Expanded dataset	target_beni_expanded_score	5-fold cross-validation on 2022 data
The main evaluation metrics include:
•	Mean Absolute Error (MAE)
•	Root Mean Squared Error (RMSE)
•	R-squared (R²)
•	Spearman rank correlation
•	Top-10 overlap
•	Rank difference
The modelling results show that Linear Regression and Ridge Regression reproduce BENI scores most accurately because BENI is an engineered composite index derived from the selected indicators. The results should therefore be interpreted as evidence of internal consistency and reproducibility, not as causal prediction.
Key Outputs
The project produces the following key outputs:
Output	Description
Integrated state-year dataset	Full analytical dataset combining education, socioeconomic, budget, and debt-context indicators
BENI-Core scores	Composite index based on UBEC-derived education and infrastructure-pressure indicators
BENI-Expanded scores	Composite index combining BENI-Core indicators with socioeconomic need
State priority rankings	Ranking of Nigerian states by relative basic education infrastructure need
Allocation comparison outputs	Comparison of BENI-based prioritization with equal and population-based approaches
Model performance tables	Regression validation results for BENI-Core and BENI-Expanded
Ranking validation tables	Actual versus predicted BENI-Expanded rankings
Visualisations	RMSE charts, actual-versus-predicted plots, top-10 priority-state charts, and coefficient-importance charts
Model results workbook	Consolidated Excel workbook containing model outputs and validation evidence
The top 10 BENI-Expanded priority states identified at the interim stage are:
1.	Katsina
2.	Yobe
3.	Borno
4.	Sokoto
5.	Kebbi
6.	Zamfara
7.	Imo
8.	Kano
9.	Kaduna
10.	Bauchi
How to Reproduce the Analysis
To reproduce the analysis, follow these steps.
1. Clone the Repository
git clone https://github.com/YOUR-USERNAME/basic-education-prioritization-nigeria.git
cd basic-education-prioritization-nigeria
2. Create a Python Environment
python -m venv .venv
Activate the environment.
On Windows:
.venv\Scripts\activate
On macOS or Linux:
source .venv/bin/activate
3. Install Required Libraries
Install the required Python libraries:
pip install pandas numpy matplotlib scikit-learn openpyxl jupyter
4. Run the Notebooks in Order
Run the notebooks in the following sequence:
01_data_cleaning_and_integration.ipynb
02_beni_index_construction.ipynb
03_model_training_and_validation.ipynb
04_visualisations_and_outputs.ipynb
5. Review Processed Data
The final processed datasets are stored in:
data/processed/
Important files include:
integrated_state_year_dataset.csv
beni_core_model_ready.csv
beni_expanded_2022_model_ready.csv
beni_core_scores.csv
beni_expanded_scores.csv
allocation_comparison_outputs.csv
6. Review Output Tables
Model and analysis tables are stored in:
outputs/tables/
7. Review Figures
Generated figures are stored in:
outputs/figures/
8. Review Model Workbook
The consolidated model results workbook is stored in:
outputs/model_results/Capstone_ML_Model_Results_Workbook.xlsx
9. Review Documentation
Supporting documentation is stored in:
docs/
Key documents include:
data_dictionary.xlsx
source_notes.md
methodology_notes.md
literature_relevance_matrix.xlsx
CapstoneProject.html
rubric_compliance_checklist.md
Author
Ebikake John
MSc Artificial Intelligence and Machine Learning
QM640 Data Analytics Capstone
Walsh College
May 2026

