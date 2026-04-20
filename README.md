# F1-Telemetry-Project
### By Sergio Baz Galicia
# 🏎️ F1 Telemetry & Lap Time Prediction

Formula 1 telemetry analysis and Machine Learning model to predict lap times using real data from the 2024 season.

---

## 📌 What does this project do?

1. **Telemetry Analysis** — Compares real telemetry data (speed, throttle, gears) between drivers in the same circuit and session.
2. **Exploratory Data Analysis (EDA)** — Inspects raw data from the official FastF1 API.
3. **ML Prediction** — Trains a `RandomForestRegressor` to predict lap times based on features like tyre life, max speed, throttle usage, and braking events.
4. **Model Evaluation** — Visualizes predictive performance with Predicted vs Actual plots and feature importance analysis.

---

## 📊 Included Visualizations

- Speed vs distance comparison: Verstappen vs Leclerc (Qatar 2024)
- Telemetry dashboard: speed, gear, and throttle (Jeddah 2024 Qualifying)
- Scatter plot: Predicted vs actual lap time
- Top 10 most important model features

---

## 🛠️ Tech Stack

| Library | Usage |
|---|---|
| `fastf1` | F1 session and telemetry data |
| `pandas` | Data manipulation and cleaning |
| `scikit-learn` | ML pipeline, Random Forest, metrics |
| `matplotlib` | Base visualizations |
| `seaborn` | Statistical visualizations |

---

## 🚀 How to Run

### 1. Clone the repository
```bash
git clone https://github.com/your-username/ProyectoF1.git
cd ProyectoF1
```

### 2. Install dependencies
```bash
pip install fastf1 pandas scikit-learn matplotlib seaborn
```

### 3. Open the notebook
```bash
jupyter notebook ProyectoF1_1.ipynb
```

> ⚠️ **Note:** FastF1 downloads session data and stores it in a local cache. The first run may take several minutes depending on your internet connection.

## 🧠 Machine Learning Model

- **Algorithm:** Random Forest Regressor (100 estimators)
- **Features:** Tyre life, max speed, average throttle, braking events, tyre compound, driver
- **Preprocessing:** `StandardScaler` for numerical features + `OneHotEncoder` for categorical features
- **Data Cleaning:** IQR-based outlier removal + minimum speed filter
- **Result:** MAE < 1 second — the model predicts lap times with under 1 second of average error on real 2024 F1 data

