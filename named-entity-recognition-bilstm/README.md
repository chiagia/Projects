# Named Entity Recognition with BiLSTM (CoNLL-2003)

This project implements a **Named Entity Recognition (NER)** system using a **Bidirectional LSTM (BiLSTM)** architecture on the **CoNLL-2003 English dataset**.

The objective is to assign a named entity tag to each token in a sentence.

---

## 📌 Dataset

Dataset: **CoNLL-2003 (English version)**  
Source: Kaggle (`alaakhaled/conll003-englishversion`)

### Entity Labels

- **PER** – Person  
- **LOC** – Location  
- **ORG** – Organization  
- **MISC** – Miscellaneous  
- **O** – Outside any entity  

BIO tagging scheme:
- **B-** → Beginning of entity  
- **I-** → Inside entity  

### Dataset Split

| Split | Sentences |
|--------|-----------|
| Train | 14,041 |
| Validation | 3,250 |
| Test | 3,453 |

Vocabulary size: **23,625**

---

## ⚙️ Preprocessing

1. Load CoNLL format (`token` + `NER tag`)
2. Build vocabulary from training set
3. Map tokens → indices
4. Map tags → indices
5. Pad sequences to max length (113 tokens)

---

## 🧠 Models

### 1️⃣ Baseline BiLSTM

Architecture:
- Embedding (random initialization, 100d)
- Bidirectional LSTM (128 hidden units)
- TimeDistributed Dense (softmax)

**Test Results**

| Entity | F1-score |
|--------|----------|
| LOC | 0.79 |
| MISC | 0.67 |
| ORG | 0.61 |
| PER | 0.65 |
| **Micro F1** | **0.68** |

---

### 2️⃣ Stacked BiLSTM + Dropout

Improvements:
- SpatialDropout on embeddings
- Two stacked BiLSTM layers
- Dropout regularization

**Test Results**

| Entity | F1-score |
|--------|----------|
| LOC | 0.75 |
| MISC | 0.62 |
| ORG | 0.62 |
| PER | 0.73 |
| **Micro F1** | **0.69** |

Recall increased, but precision slightly decreased.

---

### 3️⃣ Pre-trained GloVe Embeddings

Strategy:
- Loaded **GloVe 100d**
- Case-insensitive matching
- Embeddings frozen (`trainable=False`)

Architecture:
- GloVe Embedding layer
- BiLSTM (128)
- TimeDistributed Dense

**Test Results**

| Entity | F1-score |
|--------|----------|
| LOC | 0.82 |
| MISC | 0.64 |
| ORG | 0.65 |
| PER | 0.72 |
| **Micro F1** | **0.72** |

---

## 📊 Performance Comparison

| Model | Micro F1 |
|--------|----------|
| BiLSTM (baseline) | 0.68 |
| + Dropout + Stacked | 0.69 |
| + GloVe (frozen) | **0.72** |

Using pretrained embeddings provided the most significant improvement.

---


## 🛠️ Tech Stack

- Python
- TensorFlow / Keras
- PyTorch (padding utilities)
- NumPy / Pandas
- SeqEval (entity-level metrics)
