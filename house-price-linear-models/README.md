# House Price Prediction with Linear and Regularized Regression

## Project Overview

In this project I explore **house price prediction** using a linear regression model on two real-world datasets:

1. **KC House Dataset (Seattle area)**  
2. **California Housing Dataset**

The goal is to compare baseline linear regression with regularization techniques (Ridge, Lasso, Elastic Net) to understand:
- how well the models generalize,
- how regularization affects performance,
- the role of multicollinearity and feature selection.

---

## Datasets

### 📌 KC House Dataset
- Contains ~21,000 observations of house sales in the Seattle area
- Features include structural, locational, and quality attributes (e.g., square footage, grade, waterfront, etc.)
- Target variable: `price`

### 📌 California Housing Dataset
- Contains ~20,000 observations from California housing data
- Features include median income, average rooms, latitude/longitude, etc.
- Target variable: `MedHouseVal` (median house value)

---

## Methods

The following models are implemented and compared:

| Model | Description |
|-------|-------------|
| **Linear Regression** | Baseline model without regularization |
| **Ridge Regression** | L2 regularization to stabilize coefficients |
| **Lasso Regression** | L1 regularization for sparsity and feature selection |
| **Elastic Net** | Combination of L1 and L2 regularization |

### Evaluation Metrics
I use:
- **Mean Squared Error (MSE)**  
- **Root Mean Squared Error (RMSE)**  
- **Mean Absolute Error (MAE)**  
- **R² (Coefficient of Determination)**

to assess model performance on the training and test sets.

---

## Key Findings

### 📍 KC House Dataset Results
- The linear regression baseline generalizes well with **R² ≈ 0.70**
- Ridge and Elastic Net yield similar predictive performance, indicating limited overfitting
- Lasso produces sparsity in coefficient values, highlighting correlated features
- Regularization primarily improves coefficient interpretability and stability rather than raw performance

### 📍 California Housing Dataset Results
- Linear regression explains a substantial portion of variance (**R² ≈ 0.60**) depending on feature subsets
- Regularization does not significantly improve R² on test sets

---

## Insights

- **Model generalization** is strong even without regularization in both datasets, suggesting that linear models capture dominant relationships.
- **Multicollinearity** is present in both datasets, particularly among square footage related features (e.g., `sqft_living`, `sqft_above`, `sqft_basement` in KC).
- **Lasso** can help remove redundant features and produce a simpler model representation.
- **Ridge** produces stable coefficients when predictors are correlated, aligning with theoretical expectations.

---


