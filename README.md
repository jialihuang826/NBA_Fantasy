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

### 4. `DBSCAN.ipynb`
- Implements **DBSCAN clustering** using NBA player on-court performance and bio data
- Covers seasons from **2019 to 2024**.
- Visualizes natural clusters of player performance patterns.

---

### 5. `Risk Tier Profiling.ipynb`
- Calculates a **risk score** for each player based on five SHAP-identified key features.
- Uses **standardized scores** and statistical thresholds to classify players into:
  - **High Risk**
  - **Medium Risk**
  - **Low Risk**
- Output risk tiers are used in the Streamlit dashboard.

---
### 6. `Streamlit_Project_Fantasy_Basketball_Risk_Profiling.py`
- Builds an **interactive Streamlit dashboard** to display player risk tiers.
- Based on **2024-25 season data** (as of April 4, 2025).
- Enables filtering by player, team, and position.

---

## 📊 Key Technologies
- Python (pandas, scikit-learn, SHAP, Xgboost, Streamlit, Seborn, Numpy)
- Clustering: **DBSCAN**
- Modeling & Predicton:**XGboost**
- Visualization: **Streamlit**
- Data: NBA player performance & bio data (2019–2025)


## Data Sources

- [NBA API](https://github.com/swar/nba_api) – Official player stats (basic + advanced)
- [Spotrac Injury Report (2024)](https://www.spotrac.com/nba/injured/_/year/2024) – Games missed due to injury

---

## Model Results

| Metric | Value |
|--------|-------|
| RMSE   | 12.1  |
| MAE    | 8.8   |
| R²     | 0.15  |

While R² is modest, the model highlights patterns in player styles and workload that strongly correlate with injury risk, particularly useful for Fantasy Basketball draft strategies.

---

# 🚀 Live Dashboard

👉 Explore the dashboard here:  
**[NBA Fantasy Injury Risk Dashboard](https://nbafantasy-lcddcz9dxmxunjfop42qn8.streamlit.app/)**


---

## Future Improvements

- Integrate time series-based injury status and physical attribute data
- Apply classification models (e.g., High Risk vs. Low Risk)

---

## License

This project is for academic/research purposes only. Data is sourced from public APIs.

---
## ✍️ Author
Created by ** Jialee Huang, Zac Sheng Yuan** | 2025 Apr  

---
