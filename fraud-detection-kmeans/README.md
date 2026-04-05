# 🚨 Anomaly Detection with K-Means

Unsupervised learning project focused on detecting anomalous transactions using clustering-based methods and comparing them with specialized anomaly detection algorithms.

---

## 📌 Overview

In many real-world scenarios, labeled data for anomalies (e.g., fraud) is scarce or unavailable.  
This project explores how unsupervised learning can be used to identify unusual patterns in data.

We use **K-Means clustering** as a baseline method and compare it with more advanced techniques.

---

## 🎯 Objectives

- Model normal behavior using clustering
- Define an anomaly score based on distance from cluster centroids
- Detect anomalous observations
- Compare K-Means with other anomaly detection algorithms
- Analyze strengths and limitations of each approach

---

## 📂 Dataset

- Credit Card Fraud Detection dataset  
- Highly imbalanced dataset (fraud cases are rare)
- All features are numerical and preprocessed (PCA-transformed)

---

## ⚙️ Methodology

### 1. Data Preprocessing
- Feature scaling using StandardScaler
- Dimensionality reduction (PCA) for visualization

### 2. Clustering (K-Means)
- Optimal number of clusters selected using Elbow Method
- Clustering performed on scaled data

### 3. Anomaly Detection
- Distance from cluster centroid used as anomaly score
- Threshold defined using top 5% highest distances

### 4. Benchmark Models
- Isolation Forest
- Local Outlier Factor (LOF)

---

## 📊 Results

| Model               | Precision | Recall | F1-score |
|--------------------|----------|--------|----------|
| K-Means            | 0.03     | 0.87   | 0.06     |
| Isolation Forest   | 0.03     | 0.85   | 0.06     |
| LOF                | 0.00     | 0.12   | 0.01     |

---

## 🔍 Key Insights

- K-Means achieves **high recall**, successfully identifying most anomalies  
- However, precision is very low → many false positives  
- Isolation Forest performs similarly to K-Means  
- LOF performs poorly on this dataset  

👉 Anomalies appear to be primarily **distance-based**, not density-based  

---

## ⚠️ Limitations

- Threshold selection is arbitrary (top 5%)  
- K-Means assumes spherical clusters  
- Unsupervised approach does not directly optimize classification performance  
- High false positive rate  

