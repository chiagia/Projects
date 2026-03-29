# 🧠 T5 vs GPT-2 for Text Summarization

## 📌 Overview
This project compares different approaches to text summarization:

- **Baselines**: Lead-3, Truncation  
- **T5**: task-specific summarization model  
- **GPT-2**: general language model (zero-shot & few-shot)

Goal: analyze **performance, behavior, and limitations**.

---

## 📊 Dataset
- CNN/DailyMail (news articles + human summaries)

---

## 📏 Evaluation
- ROUGE-1, ROUGE-2, ROUGE-L  
⚠️ Measures lexical overlap, not true semantic quality

---

## 📈 Results

| Model | R-1 | R-2 | R-L |
|------|----|----|----|
| Lead-3 | 0.274 | 0.106 | 0.188 |
| Truncate | **0.293** | **0.110** | 0.200 |
| T5 | 0.283 | 0.106 | **0.212** |
| GPT Zero | 0.136 | 0.045 | 0.097 |
| GPT Few | 0.124 | 0.042 | 0.090 |

---

## 🔍 Key Insights

- **Baselines are strong**  
  → Truncation scores highest due to high word overlap  

- **T5 produces better summaries**  
  → More coherent and structured (higher ROUGE-L)  
  → Penalized by ROUGE for being abstractive  

- **GPT-2 fails on summarization**  
  → Zero-shot: continues text  
  → Few-shot: fails to generalize  

- **Prompting is not enough**  
  → Task-specific training is required  

---

## 💡 Takeaway

> Being a language model is not enough to solve structured tasks.

- Extractive methods → higher ROUGE  
- Abstractive models → better quality  
- Evaluation metrics must be interpreted carefully  
