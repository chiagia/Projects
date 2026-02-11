# 📩 SMS Spam Classification (NLP)

This project explores different Natural Language Processing techniques for binary spam detection using the SMS Spam Collection dataset.

## 📊 Dataset

The SMS Spam Collection v1 is a public dataset of **5,574 English SMS messages**, labeled as:

- **ham (0)** → legitimate message  
- **spam (1)** → unsolicited / promotional message  

The corpus was compiled from multiple public sources, including:
- UK spam reports (Grumbletext)
- Academic SMS corpora (NUS SMS Corpus)
- Research datasets used in prior spam detection studies

The dataset contains real-world short informal messages, making it suitable for practical NLP experiments.

---

## 🔎 Objective
Classify SMS messages as **ham (0)** or **spam (1)** using multiple text representation methods and machine learning models.

## 🧹 Preprocessing
- Text cleaning (regex)
- Tokenization
- Stopword removal
- Stemming / Lemmatization

## 🧠 Approaches Compared

1. **Bag of Words + Multinomial Naive Bayes**
   - Accuracy: 97.1%

2. **TF-IDF + Multinomial Naive Bayes**
   - Accuracy: 98.1%

3. **TF-IDF + Random Forest**
   - Accuracy: 98.2%

4. **Average Word2Vec (trained from scratch) + Logistic Regression**
   - Accuracy: 89.2%

## 📊 Key Insight

Sparse representations (TF-IDF) outperform averaged word embeddings for this task, likely because spam detection relies heavily on specific keyword patterns.

## 🛠 Technologies
- Python
- Scikit-learn
- NLTK
- Gensim
- NumPy / Pandas

---

This project focuses on comparing feature representations and classical ML models for text classification.
