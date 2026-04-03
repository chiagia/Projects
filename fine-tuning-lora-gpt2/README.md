# Efficient Fine-Tuning of LLMs using LoRA (PEFT)

## 📌 Overview
This project demonstrates how to efficiently fine-tune a large language model using **LoRA (Low-Rank Adaptation)**, a parameter-efficient fine-tuning (PEFT) technique.

The goal is to perform **sentiment analysis** on movie reviews while updating only a small fraction of the model parameters.

---
## 📊 Dataset
We use a subset of the IMDb dataset:
- 2000 training samples  
- 500 test samples  

This allows for fast experimentation while maintaining a balanced sentiment distribution.  
Each sample consists of a movie review and a binary label:
- 0 → negative  
- 1 → positive  

---

## ⚙️ Preprocessing
Text data is converted into numerical format using a tokenizer compatible with the model.

Steps:
- Tokenization (text → token IDs)  
- Truncation to a maximum length (128 tokens)  
- Dynamic padding using a data collator  
- Conversion to PyTorch tensors  

This ensures efficient batching and compatibility with transformer models.

---

## 🤖 Model
- Base model: GPT-style transformer (DistilGPT2)  
- Task: Binary sentiment classification  
- Approach: Add a classification head on top of the transformer  

Although GPT-style models are designed for text generation, they can be adapted to classification tasks through fine-tuning.

---

## 🔧 LoRA Configuration
We apply **LoRA (Low-Rank Adaptation)** to enable efficient fine-tuning.

- Rank (`r`): 8  
- Alpha: 16  
- Target modules: attention layers  
- Dropout: 0.1  
- Trainable parameters: 0.18% of total model parameters  

Only the LoRA adapters are trained, while the base model remains frozen.

---

## 🏋️ Training
The model is trained using the HuggingFace Trainer:

- Optimizing only LoRA parameters  
- Learning rate: 2e-4  
- Batch size: 4  
- Number of epochs: 3  

This setup allows fast convergence with limited computational resources.

---

## 📈 Results
- **Accuracy:** 0.834  
- **F1-score:** 0.839  

The model converges quickly and achieves strong performance despite training only a small subset of parameters.

---

## 🔍 Qualitative Analysis
The model performs well on clear sentiment examples:

- *"This movie was absolutely amazing!"* → Positive  
- *"I hated every second of this film."* → Negative  

It also handles:
- Sarcasm:  
  *"Yeah, best movie ever... I almost fell asleep."*  
- Mixed sentiment:  
  *"Great visuals but terrible story."*

### Limitations
- Struggles with neutral or ambiguous sentences  

---
