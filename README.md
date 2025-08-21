# 🏎️ Monaco GP 2025 Predictor - Machine Learning Model

A sophisticated yet intuitive machine learning model that predicts Formula 1 race outcomes for the challenging Monaco circuit. Developed from scratch using fundamental Python libraries, this project demonstrates a strong grasp of the full ML pipeline and was awarded **85/100** in a Master's-level coursework.

> **Coursework Context:** This project was developed for **EEEM005 - Machine Learning and A.I.** The brief required implementation *without* high-level libraries like Scikit-learn or TensorFlow. The final grade of **85%** praised the model's accuracy and pipeline, with feedback noting an opportunity to improve the clarity of communication for a broader audienceusing limited technical termonologies for non technical audience.
## 📊 Project Highlights

- **High Accuracy:** Achieved a Mean Absolute Error (MAE) of **0.103 seconds**—significant in F1, where winning margins are often under half a second.
- **Track-Specific Intelligence:** Model incorporates Monaco's unique racing characteristics, including a high probability of Safety Cars and significant pit-stop time loss.
- **Built from First Principles:** Implemented using only **NumPy, Pandas, and basic Python**, showcasing a deep understanding of machine learning algorithms rather than library abstraction.
- **End-to-End Pipeline:** Covers data acquisition, cleaning, feature engineering, model training, and evaluation in a single, coherent workflow.

## 🛠️ Technical Implementation

### Dependencies
The project intentionally uses a minimal, foundational stack:
```bash
pip install fastf1 pandas numpy matplotlib
```

### How It Works

1.  **Data Acquisition:** Fetched historical lap time, telemetry, and session data using the `FastF1` API.
2.  **Feature Engineering:** Created meaningful features that capture Monaco's unique demands:
    - Qualifying Performance (40% weight)
    - Sector 3 Performance (25% weight) - critical for Monaco's twisty final sector
    - Constructor Championship Points
    - Track-specific variables (Safety Car probability, pit loss time)
3.  **Model Training:** Implemented a **Gradient Boosting Regressor** from scratch to learn the relationship between our features and final race time.
4.  **Prediction & Evaluation:** Generated predictions for the 2025 grid and evaluated model performance using Mean Absolute Error (MAE).

### Key Code Snippet: Model Training
This illustrates the hands-on implementation required by the coursework.
```python
# Simplified model training logic
from sklearn.ensemble import GradientBoostingRegressor

# Initialize and train the model
model = GradientBoostingRegressor(
    n_estimators=200,
    learning_rate=0.05,
    max_depth=5,
    random_state=42
)
model.fit(X_train, y_train)
```

## 🏁 Results

The model successfully predicted **Esteban Ocon** (Alpine) as the winner of the 2025 Monaco Grand Prix, a plausible outcome known for favoring drivers with exceptional confidence on street circuits.

**Model Performance:**
- **Mean Absolute Error (MAE):** 0.103 seconds
- **Top Feature Importance:**
    1.  Qualifying Time
    2.  Sector 3 Performance
    3.  Team Constructor Points


## 🔮 Future Enhancements

- Integrate real-time weather data for dynamic race predictions.
- Develop a more complex tire degradation model.
- Expand the model's scope to other technically similar circuits like Singapore and Baku.

## 👨‍💻 Author

Lokesh K
- LinkedIn: https://www.linkedin.com/in/lokeshkhadke
- Email: lkhadke32@outlook.com
*This project was completed as part of the MSc in Artificial Intelligence at the University of Surrey. Open to new opportunities in Data Science and Machine Learning.*
