# 🏀 Fantasy NBA Injury Risk Prediction
Capstone- NBA Player Injury Knowledge for NBA Fantasy Game Use

## Overview

This project predicts **NBA players' injury-related game absences** based on their performance and physical stats. The goal is to help Fantasy Basketball players identify riskier picks by analyzing which on-court behaviors and physical attributes are most associated with injury duration.

---

## Project Structure

### `1. Data_Collection.ipynb`
Collects player-level data from the [NBA API](https://github.com/swar/nba_api) for both regular season and playoffs.

- Retrieves basic and advanced stats via `LeagueDashPlayerStats`
- Covers NBA seasons from 2019 to 2024
- Normalizes and merges player stats into clean, labeled datasets

---

### `2. Feature_Selection.ipynb`
Performs EDA and selects the most relevant features for modeling.

- Drops non-informative or leaky variables (e.g., Games Played, Wins)
- Tests feature importance using:
  - Decision Tree (R² per feature)
  - Random Forest importance
- Evaluates multicollinearity and interpretability

---

### `3. Model_Training.ipynb`
Trains and evaluates the injury risk model using tree-based methods.

- Implements and tunes **XGBoost Regressor**
- Compares feature subsets
- Evaluates model performance using:
  - Root Mean Squared Error (RMSE)
  - Mean Absolute Error (MAE)
  - R² score
- Uses **SHAP** for feature impact visualization

---

## Data Sources

- [NBA API](https://github.com/swar/nba_api) – Official player stats (basic + advanced)
- [Spotrac Injury Report (2024)]([https://www.spotrac.com/nba/injured](https://www.spotrac.com/nba/injured/_/year/2024)) – Games missed due to injury

---

## Model Results

| Metric | Value |
|--------|-------|
| RMSE   | 12.1  |
| MAE    | 8.8   |
| R²     | 0.15  |

While R² is modest, the model highlights patterns in player styles and workload that strongly correlate with injury risk, particularly useful for Fantasy Basketball draft strategies.

---

## Future Improvements

- Integrate time series-based injury status and physical attribute data
- Apply classification models (e.g., High Risk vs. Low Risk)

---

## License

This project is for academic/research purposes only. Data is sourced from public APIs.

---
