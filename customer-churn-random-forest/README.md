# Telco Customer Churn Prediction – Random Forest

## Overview

This project builds a Random Forest classifier to predict customer churn in a telecom company.

The focus is on:
- Generalization analysis
- Hyperparameter optimization
- Business-oriented threshold tuning
- Recall optimization for churn detection

---

## Dataset

- 7,043 customers  
- 20 features (demographic, services, billing, tenure)  
- Binary target: `Churn`  

Source: Kaggle – Telco Customer Churn

---

## Methodology

- Clean preprocessing with `Pipeline` and `ColumnTransformer`
- One-hot encoding for categorical variables
- Stratified train-test split
- Hyperparameter tuning via `RandomizedSearchCV`
- Evaluation using ROC-AUC, precision, recall, and confusion matrix
- Threshold adjustment to prioritize churn recall

---

## Results

After hyperparameter tuning:

- **Train ROC-AUC:** 0.91  
- **Test ROC-AUC:** 0.84  

By adjusting the classification threshold:

- **Recall (churn):** up to 0.90  
- Trade-off: increased false positives  

This aligns with a retention strategy where missing churners is more costly than contacting non-churners.

---

## Tech Stack

- Python  
- pandas  
- scikit-learn  
- matplotlib / seaborn  
