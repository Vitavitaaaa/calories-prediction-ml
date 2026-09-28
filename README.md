# Calories Prediction & Classification

Machine Learning project for predicting calories burned during physical activity and studying the transition between regression and classification tasks.

## Overview

This project analyzes a dataset containing information about users and their physical activity, including age, gender, height, weight, exercise duration, heart rate, body temperature, and calories burned.

The main objective is to build and evaluate machine learning models for predicting the number of calories burned. The project also demonstrates how a continuous regression target can be transformed into discrete classes and solved as a classification problem.

## Dataset

The dataset contains **15,000 observations** and the following features:

* `User_ID` — unique user identifier
* `Gender` — user gender
* `Age` — age
* `Height` — height
* `Weight` — weight
* `Duration` — exercise duration
* `Heart_Rate` — heart rate
* `Body_Temp` — body temperature
* `Calories` — target variable representing calories burned

## Project Workflow

### 1. Data Preprocessing

* Loaded and inspected the dataset
* Checked for missing values
* Split the data into training and test sets using an 80/20 ratio
* Encoded the categorical `Gender` feature
* Standardized numerical features

### 2. Regression

The project evaluates several regression approaches for predicting the continuous `Calories` target.

Models and techniques include:

* Linear Regression
* Random Forest Regressor
* Gradient Boosting
* Stacking
* Hyperparameter optimization

Regression performance was evaluated using:

* MAE — Mean Absolute Error
* RMSE — Root Mean Squared Error
* R² — coefficient of determination

The project also investigates prediction and confidence intervals for regression estimates.

### 3. Regression Model Optimization

Hyperparameter optimization was applied to improve model performance. Models were re-evaluated after optimization to compare the results before and after tuning.

The best-performing regression model in the final experiment was **Random Forest Regressor**:

| Metric | Result |
| ------ | -----: |
| MAE    |  1.815 |
| RMSE   |  2.830 |
| R²     |  0.998 |

### 4. Regression-to-Classification Transformation

The continuous `Calories` target was transformed into discrete classes using **Equal-width binning** and `KBinsDiscretizer`.

This allowed the same dataset to be investigated as a classification problem.

Classification models included:

* Logistic Regression
* Decision Tree
* XGBoost

Classification performance was evaluated using:

* Accuracy
* Precision
* Recall
* F1-score
* Confusion Matrix

For the 4-class classification task, the best result in the final experiment was obtained with **XGBoost**:

| Metric    | Result |
| --------- | -----: |
| Accuracy  |  0.980 |
| Precision |  0.980 |
| Recall    |  0.980 |
| F1-score  |  0.980 |

### 5. Probability Analysis

The project also analyzes the probability distributions of classification predictions.

The analysis includes:

* prediction confidence distributions;
* comparison of probability behavior across models;
* investigation of overfitting and underfitting;
* visualization of class probabilities.

### 6. Regression vs Classification

An additional experiment compares regression predictions with their discretized classification equivalents.

The project investigates:

* conversion of regression predictions into classes;
* classification accuracy of discretized regression predictions;
* reconstruction of numerical predictions from class means;
* comparison of the resulting MAE with the original regression model.

## Technologies

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-learn
* XGBoost
* Statsmodels


## Repository Structure

```text
calories-prediction-ml/
├── README.md
├── calories.csv
└── calories-prediction-ml.ipynb

```

