# Amazon Reviews Sentiment Analysis — LSTM & GloVe

Binary sentiment classification (positive vs negative) on the **Amazon Reviews Polarity** dataset using LSTM networks and pre-trained word embeddings.

## Dataset
- Original: 3.6M train / 400k test samples  
- Subset used:  
  - 200,000 training samples (balanced)  
  - 50,000 test samples (balanced)  
- Input text: concatenation of *title + review*

## Preprocessing
- Lowercasing and removal of special characters  
- Vocabulary size selected via frequency coverage (90%) → `8000` words  
- Tokenization with OOV handling  
- Sequence padding to max length `150`  

## Model Architecture
Embedding → LSTM(128) → Dropout(0.3) → Dense(1, sigmoid)  
~917K parameters

## Experiments

Three configurations were compared:

1. **Trainable Embedding (Random Initialization)**
2. **GloVe 6B 100d (Frozen)**
3. **GloVe 6B 100d (Fine-Tuned)**

## Results

| Model | Accuracy | F1-score |
|--------|----------|----------|
| Trainable Embedding | 91.36% | 0.913 |
| GloVe (Frozen) | 92.07% | 0.920 |
| GloVe (Fine-Tuned) | **92.72%** | **0.928** |

## Key Insights

- Pre-trained embeddings improve performance over random initialization.
- Fine-tuning GloVe yields the best results.
- Even with a large dataset, domain adaptation provides measurable gains.

---

**Tech stack:** Python, TensorFlow/Keras, Scikit-learn, GloVe, Pandas, NumPy.
