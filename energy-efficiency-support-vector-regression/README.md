# Energy Efficiency Prediction with Support Vector Regression

This project applies **Support Vector Regression (SVR)** to predict the **heating load of residential buildings** using the Energy Efficiency dataset.

The goal is to explore how kernel-based regression models perform compared to a simple linear model, and to analyze the impact of hyperparameter tuning and kernel choice.

---

## Dataset

**Energy Efficiency Dataset (UCI)**

The dataset contains **768 simulated building designs** with geometric and glazing-related features affecting energy efficiency.

Main features:

- Relative Compactness  
- Surface Area  
- Wall Area  
- Roof Area  
- Overall Height  
- Orientation  
- Glazing Area  
- Glazing Area Distribution  

Targets:

- Heating Load  
- Cooling Load  

In this project, **Heating Load** is used as the prediction target.

---

## Workflow

1. **Data Loading and Exploration**
   - Dataset inspection and descriptive statistics
   - Correlation analysis using a heatmap

2. **Data Preparation**
   - Train/test split
   - Feature scaling with `StandardScaler`

3. **Baseline Model**
   - Linear Regression

4. **Support Vector Regression**
   - Initial model with RBF kernel

5. **Hyperparameter Tuning**
   - `GridSearchCV` with 5-fold cross-validation
   - Optimization of:
     - `C`
     - `epsilon`
     - `gamma`

6. **Model Evaluation**
   - RMSE on the test set
   - Predicted vs true values plot
   - Residual analysis

7. **Kernel Comparison**
   - Linear
   - Polynomial
   - RBF

---

## Results

| Model | RMSE |
|------|------|
| Linear Regression | ~3.03 |
| SVR (default RBF) | ~2.82 |
| Tuned SVR | ~0.73 |

Cross-validation comparison between kernels:

| Kernel | Best CV Score (−RMSE) |
|------|------|
| Linear | -2.98 |
| Polynomial | -2.54 |
| RBF | **-1.16** |

The **RBF kernel performs best**, suggesting that the relationship between building features and heating load is **nonlinear**.

tory Structure
