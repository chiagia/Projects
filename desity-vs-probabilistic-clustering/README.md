# 🧠 DBSCAN vs GMM: Density-Based vs Probabilistic Clustering

## 📌 Overview
This project explores and compares two powerful clustering algorithms:

- **DBSCAN (Density-Based Spatial Clustering)**
- **Gaussian Mixture Models (GMM)**

The goal is to understand **when each method performs best**, highlighting their strengths, weaknesses, and underlying assumptions through experiments on multiple datasets.

---

## 🎯 Objectives

- Compare **density-based** vs **probabilistic** clustering approaches  
- Analyze performance on datasets with different structures  
- Evaluate clustering using both **metrics** and **visual inspection**  
- Demonstrate limitations of common evaluation techniques  

---

## 📊 Datasets

We tested the algorithms on four datasets with increasing complexity:

| Dataset | Description |
|--------|------------|
| **Blobs** | Well-separated Gaussian clusters |
| **Moons** | Non-linear, interleaving shapes |
| **Circles** | Nested circular structure |
| **Custom** | Mixed density clusters + noise |

---

## ⚙️ Methods

### 🔹 DBSCAN
- Density-based clustering
- Detects arbitrary shapes
- Identifies **outliers (noise)**

---

### 🔹 GMM (Gaussian Mixture Models)
- Probabilistic clustering
- Assumes data is generated from Gaussian distributions
- Provides **soft cluster assignments**

---

## 📈 Evaluation Metrics

- **Silhouette Score**
- **BIC (Bayesian Information Criterion)** for GMM

⚠️ Note:
> Silhouette Score favors convex clusters and may not reflect true performance on non-linear data.

---

## 📉 Results

| Dataset | DBSCAN Silhouette | GMM Silhouette |
|--------|------------------|----------------|
| Blobs  | 0.524            | **0.844** |
| Moons  | 0.334            | **0.474** |
| Circles| 0.113            | **0.348** |
| Custom | 0.537            | **0.579** |

---

## 🔍 Key Insights

- **GMM performs best** when data follows Gaussian distributions (e.g., blobs)  
- **DBSCAN excels** at detecting non-linear cluster shapes (e.g., moons, circles)  
- DBSCAN is the only method that **explicitly detects outliers**  
- GMM provides **soft clustering (probabilities)**  
- DBSCAN struggles with **varying densities**  
- GMM struggles with **non-linear structures**

---

## ⚠️ Critical Observation

> Higher Silhouette Score does not necessarily mean better clustering.

In datasets like **moons** and **circles**:
- DBSCAN correctly identifies the structure  
- GMM produces incorrect partitions  
- Yet GMM scores higher due to metric bias  

