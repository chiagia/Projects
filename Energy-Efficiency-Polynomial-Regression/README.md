# Polynomial Regression & Model Complexity Analysis
### A Bias–Variance and Regularization Case Study

## 📌 Project Objective

This project investigates model complexity using Polynomial Regression 
on the Energy Efficiency dataset.

The goal is to:

- Study the Bias–Variance tradeoff
- Analyze overfitting in high-degree polynomial models
- Evaluate the impact of Ridge regularization
- Compare model performance across different complexity levels

---

## 📊 Dataset

Energy Efficiency Dataset (768 samples, 8 features)

Target variable:
- Heating Load

The dataset describes building characteristics and their energy efficiency performance.

---

## 🧠 Methodology

### 1️⃣ Baseline Model
- Linear Regression
- Train/Test split (80/20)
- RMSE and R² evaluation

### 2️⃣ Polynomial Regression
- Degrees tested: 1 → 6
- Train vs Test error comparison
- Model complexity curve visualization

### 3️⃣ Regularization
- Ridge Regression applied to degree 6
- Multiple alpha values tested
- Generalization improvement analysis

---

## 📈 Results

### Linear Regression
- Test RMSE ≈ 3.02
- Test R² ≈ 0.91

### Best Polynomial Model
- Degree 4
- Test RMSE ≈ 0.45
- Test R² ≈ 0.998

### Overfitting Example
Degree 6 without regularization:
- Train RMSE ≈ 0.14
- Test RMSE ≈ 0.96

### Regularization Effect
Degree 6 + Ridge (alpha = 0.001):
- Test RMSE reduced to ≈ 0.48

---

## 🔎 Key Insights

- Increasing polynomial degree reduces bias but increases variance.
- Model performance improves up to degree 4.
- Higher degrees cause overfitting.
- Ridge regularization successfully stabilizes high-complexity models.
- Regularization shrinks coefficients and improves generalization.

