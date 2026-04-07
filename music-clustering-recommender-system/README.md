# 🎧 Musical Personalities Clustering & Recommender System

## 📌 Overview
This project applies **Hierarchical Clustering** to Spotify audio features to uncover distinct *musical personalities*.  
It also includes a simple **content-based recommender system** built on top of the discovered clusters.

---

## 🎯 Objectives
- Segment songs based on audio characteristics  
- Identify interpretable musical profiles (clusters)  
- Build a simple recommender system using clustering + distance  

---

## 📊 Dataset
- Spotify Tracks Dataset (audio features)
- ~114,000 tracks

### Key features:
- `danceability`
- `energy`
- `valence`
- `tempo`
- `acousticness`
- `instrumentalness`
- `liveness`
- `speechiness`
- `loudness`

---

## 🧹 Data Preparation
- Removed non-relevant columns (IDs, names, text fields)
- Selected only numerical audio features
- Handled missing values
- Standardized features using **StandardScaler**

---

## 📈 Exploratory Data Analysis
- Feature distributions
- Correlation analysis

### Key findings:
- Energy and loudness are strongly correlated
- Acousticness is inversely related to energy
- Valence captures emotional tone

---

## 🌳 Hierarchical Clustering
- Method: **Ward linkage**
- Distance metric: Euclidean

### ⚠️ Note
Hierarchical clustering has **O(n²)** complexity → not scalable to full dataset  
→ clustering performed on a **random sample**

---

## 🌲 Dendrogram Analysis
- Used truncated dendrogram for visualization
- Identified optimal range: **4–6 clusters**
- Selected **5 clusters** for best interpretability

---

## 🎭 Cluster Interpretation

| Cluster | Name | Description |
|--------|------|------------|
| 1 | 🎼 Ambient Focus | Instrumental, acoustic, low energy |
| 2 | 🌙 Chill Acoustic | Soft, vocal, relaxed |
| 3 | 🎤 Live Energy | High liveness, dynamic |
| 4 | 🎧 Instrumental Drive | Energetic, instrumental |
| 5 | 🕺 Dance Hits | High energy, danceable, mainstream |

---

## 🔍 Key Insights
- Clusters are driven by **audio features**, not genres  
- A dominant cluster represents **mainstream music**  
- Strong separation between:
  - instrumental vs vocal tracks  
  - high vs low energy  
- Music can be described along:
  - **intensity (energy)**
  - **mood (valence)**  

---

## 🎁 Recommender System

A simple recommender based on:
- Cluster filtering (coarse similarity)
- Euclidean distance (fine similarity)

