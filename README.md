# Ensemble-Methods-for-Regression-and-EMA-in-Stock-Price-data-

## Overview
This project focuses on predicting the stock prices of The Coca-Cola Company (KO) using financial data obtained from Yahoo Finance through the `yfinance` Python library. The dataset spans from January 1, 2000, to December 1, 2023, and includes the S&P 500 index data (^GSPC) for benchmarking purposes.

## Features
The following features are utilized for predictive modeling:
- **S&P 500 Close Prices (SP500_Close)**
- **Correlation with S&P 500 (SP500_Correlation)**
- **Trend, Seasonality, and Residual Components** obtained through seasonal decomposition
- **Exponential Moving Average (EMA)** of the stock's close prices

## Methodology
### Data Processing and Exploration
1. **Correlation Calculation**
   - Calculate the correlation of KO's close prices with S&P 500 close prices.
   - Handle missing values from the correlation calculation.
  
2. **Time Series Decomposition**
   - Utilize seasonal decomposition to extract trend, seasonality, and residual components.
   - Fill NaN values in the decomposed components.
  
3. **Feature Selection**
   - Select features for predictive modeling, including S&P 500-related features, decomposition components, and EMA.

### Modeling
- **Ridge Regression**
  - Implement Ridge Regression using the `sklearn` library.
  - Optimize hyperparameter (alpha) using Grid Search with cross-validation.

- **Random Forest Regression**
  - Implement Random Forest Regression using the `sklearn` library.
  - Optimize hyperparameters (n_estimators, max_depth, min_samples_split) using Grid Search with cross-validation.

- **Ensemble Modeling**
  - Combine predictions from Ridge Regression and Random Forest Regression.
  - Assess performance using Mean Squared Error (MSE) and R-squared.

- **Directional Accuracy**
  - Evaluate the directional accuracy of predictions for both models.

- **Bootstrap Aggregating (Bagging)**
  - Explore an ensemble method utilizing bagging with multiple datasets.
  - Train separate Ridge Regression and Random Forest models on each dataset and aggregate predictions.

- **Meta-Modeling**
  - Train a meta-model (Linear Regression) on the predictions from Ridge and Random Forest.
  - Evaluate the meta-model's performance on a separate test set.

## Knowledge Representation
The dataset includes crucial financial attributes from 2000 to 2023, such as 'Open,' 'High,' 'Low,' 'Close,' and 'Date.' Derived attributes like 'Trend,' 'Seasonality,' 'Residual,' and 'EMA' are engineered for enhanced temporal insights. The dataset is structured for machine learning input, emphasizing financial indicators and temporal patterns, with numeric features scaled for ensemble methods. Preprocessing steps, including addressing missing values and outliers, are detailed, and visualizations aid in understanding data structure.

## Algorithms
### Ensemble Methods
Ensemble methods combine multiple classifiers or predictors to improve decision-making accuracy. The project utilizes:
- **Support Vector Machine (SVM)**
- **XGBoost**
- **Stacking Ensemble**
- **Bagging**

### Model Evaluations
- **Ridge Regression**:
  - MSE: 0.6523
  - R-squared: 0.9960
  
- **Random Forest Regression**:
  - MSE: 0.3019
  - R-squared: 0.9981

### Ensemble Performance
- **Stacking Ensemble**:
  - MSE: 0.3214
  - R-squared: 0.9981

- **Bagging Ensemble**:
  - Ridge: Average MSE: 0.6604, R-squared: 0.9958
  - Random Forest: Average MSE: 0.2441, R-squared: 0.9985

### Final Evaluation of Ensemble Models
- **EMA and XGBoost Ensemble**:
  - MSE: 0.4165
  - R-squared: 0.9974
  
- **EMA and SVM Ensemble**:
  - MSE: 4.8409
  - R-squared: 0.9703

## Conclusion
This project effectively demonstrates the application of machine learning techniques to predict stock prices for The Coca-Cola Company. The findings indicate that Random Forest Regression outperforms Ridge Regression, and the ensemble methods further enhance predictive accuracy.
