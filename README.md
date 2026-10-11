# 📊 Delhi Electricity Demand Forecasting

*“Predicting the future of power—one model at a time.”*

Welcome to my very first hands-on Machine Learning project! This repository contains a complete pipeline—from data exploration to model evaluation—predicting total electricity demand in Delhi. The goal is to leverage machine learning techniques on natural data to uncover trends and predictions that can support governance, infrastructure planning, and social development initiatives.

---

## 🚀 Overview

This project presents a data-driven approach to forecasting total electricity demand (in MW) in Delhi. By utilizing historical energy data alongside past weather conditions, the project compares three machine learning models—**Linear Regression**, **Random Forest Regressor**, and **XGBoost**—to understand the impact of various features and identify the best predictive approach.

---

## 📌 Dataset Description

- **Source:** Real-world historical dataset (CSV)
- **Date Range:** 2018–2023

### 🧾 Features Included

- **Weather Features:** Temperature (`temp2(c)`), Wind Speed (`wind_speed50_ave`), Precipitation (`prectotcorr`), and Surface Pressure.
- **Energy Features:** Total Demand in MW (`total_demand(mw)`), Maximum Generation in MW (`max_generation(mw)`).
- **Time Features:** Day, Month, Year.

#### Sample Data

| temp2(c) | wind_speed50_ave | prectotcorr | total_demand(mw) | max_generation(mw) |
|----------|------------------|-------------|------------------|--------------------|
| 19.11    | 2.64             | 0.00        | 8000.0           | 7651.0             |

---

## 📂 Project Workflow

1. **📥 Data Collection:** Sourced from authentic datasets relevant to Delhi's power consumption and weather.
2. **🔍 Data Exploration:** Identified key attributes, correlations, and visual patterns.
3. **🧼 Data Preprocessing:** Cleaned missing values, formatted dates, and normalized the data using Pandas.
4. **🧠 Model Building:** Trained regression models using Scikit-learn and XGBoost.
5. **📊 Evaluation:** Assessed performance using R² and Mean Squared Error (MSE).
6. **📈 Interpretation:** Translated predictions into meaningful insights for feature importance.

---

## 🧪 Models & Performance

| Model                | Train R² | Test R² | Train MSE | Test MSE | Remarks |
|----------------------|----------|---------|-----------|----------|---------|
| **Linear Regression**| 0.897    | 0.901   | 292,897   | 263,111  | Strong baseline, but misses complex non-linear patterns. |
| **Random Forest**    | 0.839    | 0.839   | 455,537   | 427,145  | Depth deliberately limited (`max_depth=2`). Underfits relative to others. |
| **XGBoost**          | 0.987    | 0.941   | 38,321    | 157,357  | **Best performer.** Captures non-linear interactions well. |

> **💡 Key Insight:** XGBoost achieves the best test performance by successfully mapping the complex, non-linear interactions between weather and time features. While the gap between its Train R² (0.987) and Test R² (0.941) indicates a healthy fit, tighter regularization (e.g., lower `max_depth` or fewer estimators) could close this gap if pure generalization becomes a priority over raw test scores. 
> *(XGBoost Params used: `n_estimators=200, max_depth=4, learning_rate=0.08, subsample=0.9, colsample_bytree=0.9`)*

---

## 📉 Visualizations (Available in Notebook)

1. **Actual vs. Predicted (Test Set):** Visualizing how closely model predictions track real demand.
2. **Residual Distribution:** Checking for normal distribution of errors.
3. **Feature Importance:** Highlighting which variables (based on Linear Regression coefficients and tree splits) drive power demand the most.

---

## 🛠️ Technologies Used

| Tool / Library | Purpose |
|----------------|---------|
| **Python** | Core programming language |
| **Pandas & NumPy** | Data manipulation and numerical operations |
| **Scikit-learn & XGBoost**| Machine learning modeling and metrics |
| **Matplotlib & Seaborn** | Data visualization |
| **Jupyter Lab** | Interactive coding and development environment |

---

## 🚀 How to Run

1. Clone this repository to your local machine.
2. Ensure you have the required libraries installed (`pip install pandas numpy scikit-learn xgboost matplotlib seaborn`).
3. Open the `.ipynb` file using **Jupyter Notebook** or **Jupyter Lab**.
4. Run the cells sequentially to see the data processing, model training, and visualizations.

---

## ✅ What I Learned

- **Data Preprocessing:** Cleaning data and managing complex datetime formats.
- **Model Building:** The end-to-end process of training, validating, and comparing regression models.
- **Metrics Interpretation:** Understanding the real-world implications of R², MSE, and hyperparameter tuning.
- **Storytelling with Data:** Presenting technical insights through clear, effective visual plots.

---

## 🔮 Future Improvements

- **Hyperparameter Tuning:** Implement `GridSearchCV` or `Optuna` for a more rigorous, automated tuning of the XGBoost parameters.
- **Additional Regressors:** Explore Lasso, Ridge, and LightGBM for a wider baseline comparison.
- **Time-Series Analysis:** Incorporate dedicated forecasting methods like ARIMA, Prophet, or LSTM networks.

---

## 🙋‍♂️ About Me

I’m **Mukunth B**, a Computer Science student at PSG Tech. This project marks my first major step into the exciting world of Machine Learning! 🚀 Let's connect and build the future. 

## 📜 License

This project was built for educational and learning purposes. Feel free to reuse, fork, or draw inspiration from it with proper credits!
