## Heart Disease Prediction with K-Nearest Neighbors

This project applies **machine learning classification** techniques to predict the presence of heart disease using the **UCI Heart Disease dataset**.

### Dataset
- **Source:** UCI Heart Disease Dataset (via Kaggle)
- **Observations:** 920 patients
- **Target:** Binary classification  
  - `0` → No heart disease  
  - `1` → Heart disease

### Data Preprocessing
- Removed non-informative columns: `id`, `dataset`
- Converted the original target variable (`num`) into a **binary target**
- Dropped columns with too many missing values:
  - `ca`, `thal`, `slope`
- Handled remaining missing values:
  - **Median** imputation for numerical features
  - **Mode** imputation for categorical features
- Applied **One-Hot Encoding** to categorical variables
- Split data into **80% training / 20% testing**
- Standardized features using **StandardScaler** 

### KNN Modeling
- Evaluated **K values from 1 to 30**
- Used **5-fold cross-validation** to estimate model performance
- Selected optimal value using the **Elbow Method**

**Best parameter**
- `K = 15`

### Model Performance
Test set results:

| Metric | Value |
|------|------|
| Accuracy | **0.815** |
| F1-score (class 0) | 0.79 |
| F1-score (class 1) | 0.83 |

Evaluation tools:
- **Confusion Matrix**
- **Classification Report**
- **ROC Curve**

### Decision Boundary Visualization
To visualize how KNN separates the classes:
- Applied **PCA (Principal Component Analysis)** to reduce the data to **2 dimensions**
- Plotted the **KNN decision boundary** in the reduced feature space

### Model Comparison
The KNN model was compared with other classification algorithms:

| Model | Test Accuracy |
|------|------|
| KNN | **0.815** |
| Logistic Regression | 0.799 |
| Decision Tree | 0.723 |
| Random Forest | **0.848** |

Cross-validation results:

| Model | CV Accuracy |
|------|------|
| KNN | **0.819** |
| Logistic Regression | 0.802 |
| Decision Tree | 0.726 |
| Random Forest | 0.798 |

### Conclusion
- **KNN achieved strong and stable performance** on this dataset.
- **Random Forest achieved the highest test accuracy**, highlighting the strength of ensemble models.
