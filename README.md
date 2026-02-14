# Vehicle CO₂ Emissions Prediction

## Project Overview

This project predicts tailpipe CO₂ emissions (grams per mile) of combustion vehicles using machine learning models.

The goal is to understand how vehicle characteristics such as engine size, year, transmission type, and fuel type influence emissions.

## Dataset

Source: EPA Fuel Economy dataset (via Kaggle)

Records used: ~38,000 vehicles

Target variable:

tailpipe_co2_in_grams_mile_ft1

Selected features:

Engine displacement

Year

Vehicle class

Transmission

Fuel type

Electric vehicles (CO₂ = 0) were excluded to focus on combustion emissions.

## Methodology
### 1. Data Preprocessing

Removed missing values

Filtered CO₂ = 0 rows

One-hot encoded categorical variables

Train/Test split (80/20)

### 2. Models Compared

Dummy Regressor (baseline)

Linear Regression

Gradient Boosting

Random Forest

### 3️. Evaluation Metrics

MAE (Mean Absolute Error)

RMSE (Root Mean Squared Error)

R² Score

## Results
Model	             RMSE	        R²
Random Forest	    ~33.9	       ~0.917
Gradient Boosting   ~48.6	       ~0.83
Linear Regression   ~54.3	       ~0.79
Dummy	            ~117.8	       ~0

Random Forest achieved the best performance.

Cross-validation confirmed stable performance (CV RMSE ≈ 50.16).

Hyperparameter tuning improved Random Forest using:

max_depth = 20

n_estimators = 400

## Key Insights

Engine displacement is the dominant predictor of CO₂ emissions (~75% feature importance).

Newer vehicles tend to emit less CO₂.

Transmission and fuel type have moderate influence.

Tree-based models outperform linear models for this dataset.

## Conclusion

Engine size is the strongest determinant of tailpipe CO₂ emissions.
Modern vehicle design and regulation have significantly reduced emissions over time.

The project establishes a reproducible and interpretable baseline for emissions prediction.
