# Breast Cancer Classification with Logistic Regression

This project applies **Logistic Regression** to classify breast tumors as **malignant or benign** using the **Breast Cancer Wisconsin dataset** available in `scikit-learn`.

The notebook demonstrates a complete machine learning workflow, including data exploration, preprocessing, model training, evaluation, and model interpretation.

---

## Dataset

- **569 samples**
- **30 numerical features**
- Target classes:
  - `0 → malignant`
  - `1 → benign`

The features describe characteristics of cell nuclei extracted from breast mass images (radius, texture, perimeter, concavity, symmetry, etc.).

---

## Workflow

1. **Data exploration**
   - dataset inspection
   - descriptive statistics
   - class distribution
   - feature correlation analysis

2. **Data preparation**
   - train/test split
   - feature scaling with `StandardScaler`

3. **Model training**
   - Logistic Regression model trained on scaled features

4. **Model evaluation**
   - Accuracy
   - Confusion matrix
   - Classification report
   - ROC curve and ROC-AUC
   - Precision–Recall curve

5. **Model interpretation**
   - analysis and visualization of model coefficients to understand feature influence

6. **Regularization comparison**
   - comparison between **L1** and **L2** regularization

---

## Results

The Logistic Regression model achieves high performance on the test set:

- **Accuracy ≈ 98–99%**

The analysis of model coefficients provides insight into which tumor characteristics most influence predictions.

