# Tokenization and Embedding Techniques

## 📌 Overview

This project explores two fundamental components of modern Natural Language Processing (NLP):

- **Tokenization** (WordPiece, BPE, SentencePiece)  
- **Embeddings** (Static vs Contextual)

The goal is to understand how text is transformed into meaningful numerical representations and how this impacts language understanding in models like BERT, GPT-2, and T5.

---

## 🔤 Tokenization Analysis

We compare how different models tokenize the same sentences:

- **BERT (WordPiece)**
- **GPT-2 (BPE)**
- **T5 (SentencePiece)**

### Key Findings

- All models rely on **subword tokenization**
- Different conventions (`##`, `Ġ`, `▁`) represent similar underlying ideas

---

## 🌌 Static Embeddings (GloVe)

Using pre-trained GloVe embeddings, we analyze semantic similarity between words.

### Key Findings

- Each word has a **single fixed representation**
- Words like *"bank"* mix multiple meanings (finance vs river)
- Static embeddings cannot handle **polysemy**

---

## 🧠 Contextual Embeddings (BERT)

We extract contextual embeddings from BERT to analyze how meaning changes depending on context.

### Experiment

We compare embeddings of the word *"bank"* across different sentences:

- Financial context → close to *money*, *loan*
- Natural context → close to *river*, *water*

### Key Findings

- The same word is mapped to **different vectors**
- Meaning depends on **context**
- Contextual embeddings solve ambiguity effectively

---

## 📉 Visualization

Using PCA, we project embeddings into 2D space.

### Result

- Static embeddings → one fixed position per word  
- Contextual embeddings → multiple positions per word  

The word *"bank"* clearly separates into:
- a **finance cluster**
- a **nature cluster**

