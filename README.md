# 🏎️ Monaco Grand Prix 2025 Prediction

Machine learning model to predict the 2025 Monaco Grand Prix results using FastF1 data, sector times, team performance, and track-specific features
##  Project Highlights

- **Accurate Predictions:** Achieved **0.103s MAE** on lap time forecasts
- **Monaco-Specific Model:** Incorporates:
  - High safety car probability (65%)
  - Extended pit loss time (20.5s)
  - Sector 3 performance weighting (25%)
- **Key Features:** Qualifying times (40% weight), team performance, weather adjustments

## 🛠️ Technical Implementation

### Core Technologies
- **Python** with `FastF1` v3.5.3 for data collection
- **Scikit-learn**'s `GradientBoostingRegressor` (best performing model)
- **Pandas/NumPy** for data processing

### Model Specifications
```python
model = GradientBoostingRegressor(
    n_estimators=200,
    learning_rate=0.05,
    max_depth=5,
    random_state=42
)
