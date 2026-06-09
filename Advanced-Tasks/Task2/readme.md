# Task 2: End-to-End ML Pipeline with Scikit-learn

## Objective
Build a reusable and production-ready machine learning pipeline for predicting customer churn.

---

## Dataset
**Telco Customer Churn Dataset**
Download from [Kaggle](https://www.kaggle.com/datasets/blastchar/telco-customer-churn)

Place the file in your project folder:
```
task2/
└── WA_Fn-UseC_-Telco-Customer-Churn.csv
```

---

## Setup & Installation

```bash
pip install scikit-learn pandas numpy joblib
```

---

## Usage

```bash
python pipeline.py
```

---

## What It Does

| Step | Description |
|------|-------------|
| 1 | Load and clean the Telco dataset |
| 2 | Split into numerical and categorical columns |
| 3 | Preprocess: scale numbers, encode categories |
| 4 | Train Logistic Regression and Random Forest via Pipeline |
| 5 | Tune both models using GridSearchCV |
| 6 | Evaluate with accuracy and classification report |
| 7 | Save the best model to `churn_pipeline.joblib` |

---

## Pipeline Structure

```
Raw Data
   ↓
ColumnTransformer
   ├── StandardScaler      (numerical columns)
   └── OneHotEncoder       (categorical columns)
   ↓
Classifier
   ├── LogisticRegression  (tuned with GridSearchCV)
   └── RandomForestClassifier (tuned with GridSearchCV)
   ↓
Best Model → churn_pipeline.joblib
```

---

## Project Structure

```
task2/
├── pipeline.py                          # Main ML pipeline script
├── WA_Fn-UseC_-Telco-Customer-Churn.csv # Dataset
├── churn_pipeline.joblib                # Exported best model
└── README.md
```

---

## Requirements

```
scikit-learn
pandas
numpy
joblib
```

---

## Skills Gained
- ML pipeline construction with `sklearn.pipeline.Pipeline`
- Hyperparameter tuning with `GridSearchCV`
- Model export and reusability using `joblib`
- Production-readiness practices
