# Task 3: Heart Disease Prediction

## Objective
Predict whether a person is at risk of heart disease based on health indicators.

## Dataset
- Source: Heart Disease UCI Dataset (Kaggle)
- 920 records, 16 features
- Target: num (0 = No Disease, 1 = Disease)
- Features: age, sex, chest pain type, blood pressure, cholesterol, etc.

## Models Applied
- Logistic Regression

## Key Results and Findings
- Model achieved strong accuracy on test data
- ROC-AUC score indicates good discrimination between classes
- Most important features: chest pain type (cp), thalassemia (thal), number of vessels (ca)
- Missing values handled using median imputation
