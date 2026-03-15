# Wine Classification with Linear Discriminant Analysis

## Project Overview
This project explores **Linear Discriminant Analysis (LDA)** for classification and dimensionality reduction using the **Wine dataset** from scikit-learn.

The objectives are to:

- perform exploratory data analysis (EDA)
- train an **LDA classifier**
- visualize the **discriminant subspace**
- compare **LDA with PCA**
- compare **LDA with Quadratic Discriminant Analysis (QDA)**
- evaluate model stability using **cross-validation**

---

## Dataset

The dataset contains:

- **178 samples**
- **13 numerical features**
- **3 wine classes**

Features describe chemical properties of wines (e.g. alcohol, flavanoids, color intensity, proline).

Target variable: class ∈ {0,1,2}

Each class corresponds to a different wine cultivar.

---

## Exploratory Data Analysis

Main observations:

- The dataset contains **no missing values**.
- Some features show **strong correlations**, suggesting redundancy.
- Certain variables (e.g. **flavanoids**, **color intensity**) show good class separation.
- Individual feature distributions are not always Gaussian; however, LDA assumes **multivariate Gaussian distributions within each class**, which is generally robust to moderate deviations.

EDA included:

- feature distributions
- correlation heatmap
- pairplots for class separation

---

## Preprocessing

The preprocessing pipeline includes:

- **train/test split (80/20)**
- **feature scaling using StandardScaler**

Scaling is useful because LDA relies on **covariance estimation**.

---

## Linear Discriminant Analysis (LDA)

An LDA classifier is trained on the scaled features.

**Test accuracy: ≈ 0.94**

The confusion matrix shows that most samples are correctly classified, confirming that the wine classes are well separated in the feature space.

---

## LDA for Dimensionality Reduction

The projection into the space of the first 2 discriminant axes reveals clear clustering of the wine classes.

Analysis of the coefficients shows which features contribute most to the discriminant directions.

---

## PCA vs LDA

A comparison with **Principal Component Analysis (PCA)** highlights a key difference:

- **PCA** maximizes variance and ignores class labels
- **LDA** maximizes class separability

As a result, classes appear **more overlapped in PCA space**, while LDA produces clearer separation.

---

## Comparison with QDA

**Quadratic Discriminant Analysis (QDA)** relaxes the assumption of equal covariance matrices across classes.

Results:

QDA Accuracy: 1.00


Both models perform very well, indicating that the dataset is **highly separable**. However, the dataset is relatively small, so perfect accuracy should be interpreted cautiously.

---

## Cross Validation

To obtain a more robust estimate of performance, **5-fold cross-validation** was applied.

LDA mean CV score ≈ 0.99

QDA mean CV score ≈ 0.98

These results confirm that both models generalize well, with LDA providing slightly more stable performance.

---

## Key Takeaways

- The Wine dataset is **highly separable** in the feature space.
- **LDA performs well both as a classifier and as a dimensionality reduction method.**
- Compared to PCA, LDA produces projections that better separate the classes.
- Although QDA is more flexible, **LDA performs similarly with fewer parameters**, making it a strong choice for this dataset.
