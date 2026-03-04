# Sentiment Analysis with GRU and LSTM (IMDb Reviews)

This project compares **GRU** and **LSTM** recurrent neural networks for **sentiment analysis** on the IMDb movie reviews dataset using the same preprocessing pipeline and hyperparameters.

## Dataset

- **50,000 movie reviews** labeled as positive or negative  
- Perfectly balanced dataset  

Data split:

- **70% Training**
- **15% Validation**
- **15% Test**

Stratified sampling is used to maintain class balance.

## Preprocessing

Text preprocessing includes:

- HTML removal
- Lowercasing
- Removing punctuation and numbers
- Tokenization

The vocabulary is built **only on the training set** to avoid data leakage.

- Vocabulary size: **6000**
- Special tokens: `<PAD>` and `<UNK>`

Sequences are **truncated and padded to 300 tokens**.

## Models

Two recurrent architectures are implemented:

**GRU**

Embedding → GRU → Linear → Sigmoid

**LSTM**

Embedding → LSTM → Linear → Sigmoid


Main hyperparameters:

- Embedding size: **100**
- Hidden size: **128**
- Batch size: **64**
- Optimizer: **Adam**
- Loss: **BCEWithLogitsLoss**

Packed sequences are used to handle padded inputs efficiently.

## Results

| Model | Test Accuracy |
|------|------|
| **GRU** | **89.55%** |
| **LSTM** | **88.17%** |

## Conclusion

In this experiment **GRU slightly outperforms LSTM**.  
This may be due to the relatively small dataset and moderate sequence length, where the simpler GRU architecture generalizes well while using fewer parameters.

## Technologies

- Python
- PyTorch
- Pandas
- Scikit-learn
