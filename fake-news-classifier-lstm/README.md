# 📰 Fake News Detection with LSTM

This project implements a **binary text classification model** to detect fake news using an LSTM neural network.

## 📂 Dataset
Fake News dataset from Kaggle (20,800 articles).  
After removing null values: **18,285 samples**.

Labels:
- `0` → Reliable
- `1` → Unreliable

The model uses only the **title** column.

---

## 🧹 Preprocessing
- Lowercasing
- Stopwords removal (NLTK)
- Stemming (PorterStemmer)
- One-hot encoding (vocabulary size = 5000)
- Padding to fixed length (20 words)

---

## 🧠 Model

- Embedding(5000, 40)
- LSTM(100)
- Dense(1, activation="sigmoid")
- Loss: `binary_crossentropy`
- Optimizer: `adam`
- Total parameters: **256,501**

---

## 📊 Results

Train/Test split: 80/20  

- Base model accuracy: **90.6%**
- With Dropout (0.3): **91.7%**

The LSTM model performs well on short news titles, achieving ~92% test accuracy.

---

## 🚀 Tech Stack
Python · TensorFlow/Keras · NLTK · Scikit-learn · Pandas · NumPy
