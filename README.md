# 🏎️ Monaco GP 2025 Predictor - Machine Learning Model

Welcome to the Monaco Grand Prix 2025 prediction repository! This project uses FastF1 API data and Gradient Boosting to predict race outcomes with **0.103s MAE accuracy**.

## Project Overview
This repository contains a machine learning pipeline that:
- Predicts Monaco GP results using **track-specific features**
- Achieves **0.103s MAE** (race-winning margins are often <0.5s)
- Optimized for Monaco's unique characteristics:
  - 65% safety car probability
  - 20.5s pit loss time
  - Sector 3 performance weighted 25%

## 📊 Data Sources
- **FastF1 API**: Lap times, telemetry, weather
- **2024 Monaco GP**: Training data
- **Simulated 2025 Qualifying**: Prediction input

## 🏁 How It Works
1. **Data Collection**:  
   ```python
   import fastf1
   session = fastf1.get_session(2024, 'Monaco', 'R')
   session.load()
   ```
2. **Feature Engineering**:  
   - Qualifying times (40% weight)
   - Sector 3 performance (25%)
   - Team constructor points
   - Monaco-specific adjustments

3. **Model Training**:  
   ```python
   from sklearn.ensemble import GradientBoostingRegressor
   model = GradientBoostingRegressor(n_estimators=200, learning_rate=0.05, max_depth=5)
   ```

4. **Prediction**:  
   ```bash
   python predict_monaco.py
   ```
   **Output**:  
   🏁 Predicted 2025 Monaco GP Winner  
   Driver: Esteban Ocon, Predicted Time: 78.037s  
   MAE: 0.103s

## 🔧 Dependencies
```bash
pip install fastf1 pandas scikit-learn matplotlib
```

##  Model Performance
- **MAE**: 0.103 seconds  
- **Key Influencers**:
  1. Qualifying Time (40%)
  2. Sector 3 Performance (25%)
  3. Team Points (15%)

## 📌 Future Improvements
- [ ] Real-time weather integration
- [ ] Tire degradation modeling
- [ ] Expand to other street circuits (Singapore, Baku)
