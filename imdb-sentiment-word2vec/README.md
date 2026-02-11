# 🎬 Sentiment Analysis on IMDB 50K using Word2Vec

## 📌 Project Overview

This project performs sentiment classification on the **IMDB 50K Movie Reviews Dataset** using **Word2Vec embeddings** combined with classical machine learning models.

---

## 📂 Dataset

**IMDB Dataset of 50K Movie Reviews**

- 50,000 movie reviews
- Balanced dataset (25,000 positive / 25,000 negative)
- Binary sentiment classification task

---

## 🧠 Methodology

### 1️⃣ Data Preprocessing

Minimal but structured preprocessing was applied:

- Removal of HTML tags (`<br />`, etc.)
- Lowercasing
- Tokenization using `gensim.simple_preprocess`
- Lemmatization using NLTK
- Stopwords were intentionally **not removed** to preserve contextual information for Word2Vec training

The output of preprocessing is a tokenized corpus suitable for Word2Vec training.

---

### 2️⃣ Word Embedding Strategies

Two embedding approaches were evaluated:

---

#### 🔹 A) Word2Vec Trained on IMDB (Domain-Specific)

- Architecture: **CBOW**
- Vector size: 200
- Window size: 5
- min_count: 5
- Trained directly on the IMDB corpus

Sentence embeddings were obtained by computing the **average of word vectors** for each review.

---

#### 🔹 B) Pre-trained Word2Vec (Google News)

- Vector size: 300
- Trained on a large news corpus

The same averaging strategy was used to obtain sentence embeddings.

---

### 3️⃣ Classification Models

The following classifiers were tested:

- Logistic Regression  
- Linear SVM  
- MLP (1 hidden layer)

Since performance across models was very similar, **Logistic Regression** was selected.

---

## 📊 Results

| Embedding Strategy        | Vector Size | Accuracy |
|---------------------------|-------------|----------|
| IMDB-trained Word2Vec     | 200         | **86.6%** |
| Google News Word2Vec      | 300         | 84.8% |

### 🔎 Key Findings

- Domain-specific embeddings outperformed generic pre-trained embeddings.
- Increasing embedding dimensionality (300 vs 200) did not compensate for lack of domain relevance.
- The embedding space appears **almost linearly separable**, as linear models performed as well as non-linear ones.

---

## 🧩 Interpretation

This experiment suggests that:

- Domain relevance can be more important than embedding dimensionality.
- Average Word2Vec provides a strong baseline (~87% accuracy).
- Classical ML models remain competitive when combined with meaningful embeddings.

---

## 🛠 Tech Stack

- Python
- Pandas
- NumPy
- Gensim
- Scikit-learn
- NLTK
- tqdm
