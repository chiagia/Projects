# 🧠 Community Detection with Spectral Clustering

## 📌 Overview

This small project explores **Spectral Clustering** as a powerful technique for detecting hidden community structures in graph data.

Using the Zachary Karate Club dataset, I model a social network as a graph and uncover its underlying communities through spectral methods.

---

## 🎯 Objectives

- Represent a real-world network as a graph  
- Construct and analyze the **graph Laplacian**  
- Perform **spectral embedding** via eigen decomposition  
- Apply clustering in the embedded space  
- Evaluate results against ground truth communities  

---

## 🧩 Methodology

### 1. Graph Representation
I model the network using NetworkX:
- Nodes → individuals  
- Edges → social interactions  
- Edge weights → interaction strength  

---

### 2. Adjacency Matrix
The graph is converted into an **adjacency matrix** \( A \), encoding connections between nodes.

---

### 3. Graph Laplacian

We compute the **normalized graph Laplacian**:

\[
L_{norm} = D^{-1/2}(D - A)D^{-1/2}
\]

where:
- \( D \) is the degree matrix  
- \( A \) is the adjacency matrix  

This step is crucial as it captures the structure of the graph.

---

### 4. Spectral Embedding

I solve the eigenvalue problem:

\[
L_{norm} v = \lambda v
\]

The first \( k \) eigenvectors (corresponding to the smallest eigenvalues) define a **low-dimensional embedding** where clusters become separable.

---

### 5. Clustering

I apply K-Means on the spectral embedding to identify communities.

---

### 6. Evaluation

I compare predicted clusters with ground truth labels using:

- Adjusted Rand Index (ARI)

---

## 📊 Results

- The algorithm successfully identifies the two main communities in the network  
- Only **one node is misclassified**, highlighting the presence of **boundary (bridge) nodes**  
- Achieved **ARI ≈ 0.88**, indicating strong agreement with the true structure  


---

## 📁 Project Structure
