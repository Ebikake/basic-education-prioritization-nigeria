# Methodology Notes

## Project Aim

The project develops a transparent, reproducible, and data-driven framework for prioritizing public capital allocation to basic education infrastructure across Nigerian states.

## Analytical Unit

The principal analytical unit is the state-year. The final model-ready BENI-Core dataset contains 148 state-year rows across 37 states/FCT and the years 2018, 2019, 2020, and 2022. The BENI-Expanded dataset contains 37 state-level rows for 2022.

## BENI-Core

BENI-Core uses UBEC-derived education infrastructure pressure indicators:

- `pupil_teacher_ratio`
- `pupil_classroom_ratio`
- `unqualified_teacher_share`
- `bad_classroom_share`
- `enrolment_per_school`

## BENI-Expanded

BENI-Expanded extends BENI-Core by adding:

- `nbs_socioeconomic_need_proxy`

This allows prioritization to reflect both education infrastructure pressure and wider socioeconomic disadvantage.

## Validation Strategy

BENI-Core is validated using a time-based holdout strategy:

- Training: 2018, 2019, and 2020
- Testing: 2022

BENI-Expanded is validated using 5-fold cross-validation because only 37 state-level records are available for 2022.

## Models

The project uses:

- Linear Regression
- Ridge Regression
- Random Forest Regressor
- Gradient Boosting Regressor

## Evaluation Metrics

The evaluation uses:

- MAE
- RMSE
- R-squared
- Spearman rank correlation
- Top-10 overlap
- Rank difference

## Interpretation Rule

The models validate BENI score reproducibility and ranking stability. Since BENI is an engineered composite index, strong model performance should be interpreted as internal consistency, not causal prediction.
