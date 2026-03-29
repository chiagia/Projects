# 🧠 Support Vector Machines: From Linear Separation to Kernel Trick

## 📌 Overview
This project explores the behavior of **Support Vector Machines (SVMs)** on non-linearly separable datasets.

The goal is to demonstrate how SVMs evolve from simple linear classifiers to powerful non-linear models through the **kernel trick**, and how hyperparameters influence their performance.

---

## 📊 Datasets
Synthetic datasets generated using `scikit-learn`:

- **Moons Dataset** → non-linear, interleaving classes  
- **Circles Dataset** → concentric structure  

These datasets are intentionally **not linearly separable**, making them ideal for studying kernel methods.

---

## 🧪 Experiments

### 1. Linear SVM
- Applied a linear kernel  
- Observed poor performance on non-linear data  
- Highlighted limitations of linear decision boundaries  

---

### 2. Kernel SVM (RBF)
- Introduced the Radial Basis Function (RBF) kernel  
- Achieved non-linear decision boundaries  
- Successfully classified complex datasets  

---

### 3. Support Vectors Analysis
- Identified support vectors used by the model  
- Demonstrated that only a subset of points defines the decision boundary  
- Verified that training on support vectors alone yields similar results  

---

### 4. Effect of C (Regularization)
- Explored different values of **C**  
- Observed trade-off between margin size and classification errors  
- Connected results to bias-variance trade-off  

---

### 5. Effect of Gamma
- Analyzed how **gamma** affects decision boundary complexity  
- Low gamma → smooth boundary (underfitting)  
- High gamma → complex boundary (overfitting)  

---

### 6. Model Comparison
- Compared linear and RBF SVMs  
- Evaluated performance across different hyperparameters  
- Highlighted the importance of model selection  

---

## 📈 Results
- Linear SVM fails on non-linear datasets  
- RBF kernel significantly improves performance  
- Proper tuning of **C** and **gamma** leads to optimal results  


This project highlights the importance of **feature space transformation**, **support vectors**, and **hyperparameter tuning** in building robust machine learning models.
