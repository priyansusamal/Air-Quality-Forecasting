# Air Quality Forecasting using Random Forest

A machine learning project that analyzes historical air-quality measurements and predicts the next hour's carbon monoxide (CO) concentration using a Random Forest Regression model.

## Project Overview

Air pollution monitoring is important for understanding environmental conditions and identifying pollution trends. This project uses historical air-quality data to explore pollutant distributions, analyze changes over time, engineer forecasting features, and predict future CO concentration.

## Dataset

**Dataset:** UCI Air Quality Dataset

The dataset contains hourly air-quality measurements collected from an air-quality monitoring station.

The notebook downloads the dataset and loads it from `AirQualityUCI.csv`.

## Tech Stack

- **Language:** Python
- **Data Processing:** Pandas, NumPy
- **Visualization:** Matplotlib
- **Machine Learning:** Scikit-learn
- **Model:** Random Forest Regressor
- **Environment:** Jupyter Notebook / Google Colab

## Project Workflow

1. **Data loading:** Download and load the UCI Air Quality dataset.
2. **Data cleaning:** Remove empty rows and columns, convert invalid `-200` measurement values to missing values, and parse date and time information.
3. **Exploratory Data Analysis:** Examine data types, descriptive statistics, missing values, pollutant distributions, and CO concentration trends.
4. **Feature engineering:** Extract hour, day, month, and day of the week. Create lag features and a rolling average from previous CO measurements.
5. **Target creation:** Predict the CO concentration for the next hour.
6. **Data splitting:** Use a chronological 80:20 training-test split to preserve temporal order.
7. **Model training:** Train a Random Forest Regressor with 100 trees and median imputation for missing feature values.
8. **Evaluation:** Calculate MAE, MSE, RMSE, and R² on the test set.
9. **Feature importance:** Visualize the most influential features used by the trained model.

## Model Details

The model uses a Scikit-learn Pipeline containing:

- `SimpleImputer(strategy="median")` for missing feature values.
- `RandomForestRegressor(n_estimators=100, random_state=42)` for regression.

The input features include time-based variables, lagged CO measurements, rolling averages, other pollutant measurements, and environmental variables.

**Prediction target:** Next-hour CO concentration.

## Installation and Usage

### 1. Clone the repository

```bash
git clone https://github.com/YOUR-USERNAME/air-quality-forecasting.git
cd air-quality-forecasting
```

### 2. Install dependencies

```bash
pip install -r requirements.txt
```

### 3. Run the notebook

Open `AIML_Recruitment_Air_Quality.ipynb` using Jupyter Notebook, JupyterLab, or Google Colab.

Execute the cells in order. The initial notebook cells download and extract the dataset, so an internet connection is required for that step.

## Results

The model is evaluated on the final 20% of the time-ordered data.

The notebook reports the following regression metrics:

- **Mean Absolute Error (MAE):** Add the measured result.
- **Mean Squared Error (MSE):** Add the measured result.
- **Root Mean Squared Error (RMSE):** Add the measured result.
- **R² Score:** Add the measured result.

The notebook also includes visualizations of pollutant distributions, CO concentration over time, missing-value percentages, and feature importance.

## Key Findings

- The dataset contains hourly air-quality measurements.
- Several measurement columns use `-200` to represent missing values.
- CO concentrations vary over time.
- Time-based features, lag features, and rolling averages help represent historical patterns.
- Model performance is evaluated using regression metrics and visualizations.

## Limitations

- The dataset contains substantial missing data, particularly in some pollutant measurements.
- The model is trained on historical measurements from a single monitoring location.
- Sudden pollution changes caused by unusual events or weather conditions may not be captured.
- Predictions depend on the quality and availability of historical measurements.

## Future Improvements

- Compare Random Forest with other regression algorithms.
- Perform hyperparameter tuning using time-series-aware validation.
- Compare predicted and actual CO concentrations over time.
- Explore additional environmental features and alternative imputation strategies.
- Build an interactive dashboard for air-quality forecasting.

## Acknowledgements

Dataset: UCI Machine Learning Repository — Air Quality Dataset.

---

**Project:** Air Quality Forecasting  
**Task:** Machine Learning / Predictive Modelling  
**Model:** Random Forest Regression
