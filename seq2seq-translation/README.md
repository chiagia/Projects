# English → French Neural Machine Translation (Seq2Seq with Attention)

Implementation of a **Neural Machine Translation (NMT)** system that translates sentences from **English to French** using a **Seq2Seq architecture with LSTM and attention**, implemented from skratch in **PyTorch**.

The project reproduces the main components of classical neural machine translation systems and demonstrates the full workflow of building and training a sequence-to-sequence model from raw text data to inference.

---

## Key Features

- Text preprocessing and tokenization pipeline  
- Vocabulary construction with frequency filtering  
- Custom **PyTorch Dataset and DataLoader**  
- **LSTM Encoder–Decoder architecture**  
- **Bahdanau-style attention mechanism**  
- **Teacher forcing** training strategy  
- **Gradient clipping** for training stability  
- **Early stopping** using a validation set  
- **Beam search decoding** for improved inference  
- Model evaluation using **BLEU score**

---

## Model Architecture

The system follows a classical **Seq2Seq architecture** composed of:

**Encoder**
- Multi-layer LSTM
- Encodes the input English sentence into hidden representations

**Attention Mechanism**
- Computes alignment scores between decoder states and encoder outputs
- Allows the decoder to focus on relevant tokens of the input sequence

**Decoder**
- Multi-layer LSTM
- Generates the French translation token-by-token

**Decoding Strategy**
- Beam search is used during inference to improve translation quality compared to greedy decoding.

---

## Dataset

The model is trained on English–French parallel sentences from the **Tatoeba dataset**:

http://www.manythings.org/anki/

For faster experimentation the training uses:
- sentence length filtering
- a subset of approximately **50,000 sentence pairs**

---

## Example Translation

Example output produced by the trained model:

**Input** : "he was sick yesterday"

**Prediction** : "il était malade hier"

While the model is trained on a relatively small dataset, it captures basic translation patterns and demonstrates the mechanics of neural machine translation systems.

---

## Technologies Used

- **Python**
- **PyTorch**
- Pandas
- NumPy
- Matplotlib
- NLTK
