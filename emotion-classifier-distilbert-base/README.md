# 🧠 BERT Emotion Classification & Attention Analysis

This project explores emotion classification using a fine-tuned Transformer model, with a focus on **model behavior and interpretability** rather than only performance.

---

## 📌 Overview

The goal is to classify short text snippets into one of six emotions:

- **sadness**
- **joy**
- **love**
- **anger**
- **fear**
- **surprise**

The project follows a complete NLP pipeline:
- Dataset exploration
- Tokenization
- Fine-tuning a Transformer model
- Evaluation
- Error analysis
- Attention visualization

---

## 📊 Dataset

We use the **Emotion dataset** from Hugging Face.

- 16,000 training samples
- 2,000 validation samples
- 2,000 test samples

### Key observations:
- The dataset is **not perfectly balanced**
- Texts are relatively short (avg ~19 words)
- Some samples are **ambiguous or multi-emotion**

---

## ⚙️ Model

We use:

- **DistilBERT (uncased)** for efficiency on CPU
- Fine-tuned for **multi-class classification (6 labels)**

### Why DistilBERT?
- Faster than BERT (~40%)
- Comparable performance
- Suitable for local experimentation

---

## 🧪 Training Setup

- Learning rate: `2e-5`
- Batch size: `8`
- Epochs: `3`
- Evaluation: per epoch
- Metric: **weighted F1 score**

### Results

| Epoch | Accuracy | F1 Score |
|------|----------|----------|
| 1 | 0.73 | 0.68 |
| 2 | 0.82 | 0.81 |
| 3 | **0.84** | **0.83** |

The model shows consistent improvement with no strong signs of overfitting.

---

## 🔍 Error Analysis

We analyze misclassifications to understand model limitations.

### Common confusion patterns:
- **joy ↔ love**
- **anger ↔ sadness**
- **fear ↔ sadness**

### Example errors:

> *"i feel underappreciated and under valued"*  
→ **True:** joy  
→ **Predicted:** sadness  

> *"i feel shame in a strange way"*  
→ **True:** surprise  
→ **Predicted:** sadness  

### Insights:
- Emotion boundaries are often **ambiguous**
- The model tends to over-predict **sadness**
- High-confidence errors suggest **overconfidence on unclear inputs**

---

## 🔬 Attention Analysis

To better understand model behavior, we visualize **self-attention patterns**.

### What we analyze:
- Attention across tokens
- Differences between attention heads
- Role of the `[CLS]` token

---

### Key observations:

- Different heads specialize in different roles:
  - Some focus on **local token relationships**
  - Some reconstruct **subword tokens**
  - Others aggregate **global context**

- The `[CLS]` token often receives high attention:
  - Acts as a **global information aggregator**
  - Used for final classification

- Some heads show near-diagonal patterns


## 📎 Notes

This project is designed as a **learning-focused exploration of Transformer models**, with emphasis on interpretability and analysis rather than production deployment.
