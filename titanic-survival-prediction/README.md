# Titanic Survival Prediction with Neural Network

## Project Overview
This project focuses on **binary classification** to predict passenger survival
on the Titanic using a **feedforward neural network**.

The goal is to demonstrate the full machine learning pipeline:
data preprocessing, feature engineering, model training, evaluation,
and overfitting analysis.

---

## Dataset
**Titanic Dataset (Kaggle)**

- 891 passengers
- Target variable: `Survived` (0 = No, 1 = Yes)
- Mix of numerical and categorical features

---

## Data Preprocessing
- Missing values handling:
  - `Age`: filled with median
  - `Embarked`: filled with mode
- Categorical encoding:
  - `Sex` and `Embarked` encoded numerically
- Feature selection to remove non-informative columns
- Feature scaling using `StandardScaler`

---

## Model Architecture
A simple feedforward neural network:

- Input layer matching the number of features
- One hidden layer with ReLU activation
- Output layer with sigmoid activation

Loss function:
- Binary Cross-Entropy

Optimizer:
- Adam

---

## Training Strategy
- Train/Test split: 80% / 20%
- Validation split used during training
- 300 epochs to analyze convergence and overfitting
- Performance monitored using training and validation loss curves

---

## Results
- Test accuracy: **~81%**
- Training and validation loss curves show stable convergence
- Performance is consistent with classical benchmarks on this dataset

---

## Key Insights
- Feature scaling is essential for neural networks
- Simple architectures can achieve strong performance on tabular data
- Validation curves are crucial to detect overfitting
- Neural networks can match traditional models on structured datasets

---

## Technologies Used
- Python
- Pandas, NumPy, Seaborn, Matplotlib
- Scikit-learn
- TensorFlow / Keras

---

## Conclusion
This project demonstrates a complete and well-structured approach to
binary classification on tabular data using neural networks,
with attention to preprocessing, evaluation, and model diagnostics.
