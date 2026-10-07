# BB-018 — GK-05 Final Reconstruction

## Objective
The objective of this project is to reconstruct the black-box continuous risk scoring system of the GK-05 Access Control Oracle using a machine learning surrogate model.

## Data
- **Training Observations**: 60 (covering sites A, B, and C)
- **Holdout Observations**: 0
- **Holdout Evaluation**: There was NO unseen holdout evaluation performed because no legitimate unseen holdout data exists in the active workspace.

## Features
### Original Features
- `anomaly_ratio`
- `badge_age_days`
- `clearance_level`
- `escorts`
- `history_score`
- `linked_badges`
- `recent_denials`
- `requested_zone`
- `tenure_years`
- `site` (Categorical)

### Engineered Features
- `clearance_vs_requested`
- `clearance_zone_ratio`
- `anomaly_clearance_int`
- `anomaly_history_int`
- `history_clearance_int`
- `escorts_denials_int`

## Model Selection
We evaluated multiple models using a rigorous 5-fold cross-validation scheme. HistGradientBoosting was chosen as our final surrogate model because it produced the lowest validation error (MAE and RMSE) and was the only candidate model to achieve a positive cross-validated R² score.

| Model | CV MAE | CV RMSE | CV R² |
| :--- | :---: | :---: | :---: |
| **HistGradientBoosting** | **0.17867** | **0.21473** | **0.03529** |
| Extra Trees | 0.19272 | 0.23400 | -0.14555 |
| Gradient Boosting | 0.19678 | 0.24414 | -0.24702 |
| Random Forest | 0.19789 | 0.23478 | -0.15325 |
| Ridge Regression | 0.19820 | 0.23890 | -0.19410 |
| Ensemble | 0.19968 | 0.23700 | -0.17519 |
| Ridge (with interactions) | 0.20043 | 0.24106 | -0.21581 |

## Decision Rule
Because the available dataset is severely skewed and did not contain sufficient binary outcome variety (providing only `"APPROVE"` labels in the active training subset), there was insufficient evidence to infer or model the true binary `APPROVE`/`DECLINE` decision boundary. We treat the decision cutoff of `0.5` purely as a provisional surrogate threshold, not as a discovered physical attribute of the hidden system. Consequently, no decision accuracy metrics are claimed.

## Limitations & Cautious Conclusions
- **Small Sample Size**: The model was trained on only 60 observations, restricting overall generalization.
- **True Algorithm**: This surrogate model represents an empirical approximation of the scoring function and does not claim to represent the true hidden GK-05 system logic.
- **Data Deficit**: The complete lack of verified `DECLINE` instances limits our ability to resolve any classification task.
