# 📊 Prompt Engineering Evaluation with Instruction-Tuned Models

## 🧠 Overview

This project explores how different **prompt engineering strategies** influence the behavior and performance of Large Language Models (LLMs).

We evaluate three prompting techniques:

- **Zero-shot prompting**
- **Few-shot prompting**
- **Chain-of-Thought (CoT) prompting**

All experiments are conducted using the instruction-tuned model **FLAN-T5**.

---

## 🧪 Tasks

We evaluate the model on three NLP tasks:

### 1. Sentiment Analysis
Classify text as:
- Positive
- Negative
- Neutral

### 2. Topic Classification
Classify text into:
- Sports
- Politics
- Technology

### 3. Reasoning (Math/Logic)
Solve simple arithmetic and logical problems.

---

## ⚙️ Model

We use the instruction-tuned model:

- `google/flan-t5-small`

This model is designed to follow natural language instructions, making it suitable for prompt engineering experiments.

---

## 🧩 Prompting Strategies

### 🔹 Zero-shot
The model receives only task instructions, without examples.

### 🔹 Few-shot
The model is provided with a few labeled examples before the input.

### 🔹 Chain-of-Thought (CoT)
The model is encouraged to reason step-by-step before answering (used for reasoning tasks).

---

## 📊 Evaluation

We evaluate performance using:

- **Accuracy** for classification tasks  
- **Exact match** for reasoning tasks  

Predictions are normalized before evaluation to ensure fair comparison.

---

## 📈 Results

| Strategy      | Sentiment | Topic | Reasoning |
|--------------|----------|------|----------|
| Zero-shot    | 0.67     | 1.00 | 0.00     |
| Few-shot     | 0.67     | 0.33 | 0.00     |
| Chain-of-Thought | —    | —    | 0.00     |

---

## 🔍 Key Insights

- **Zero-shot prompting can be surprisingly strong** on simple classification tasks  
- **Few-shot prompting may degrade performance** if examples are not representative  
- **Chain-of-Thought does not guarantee correctness**  
- **Model capacity plays a crucial role** in reasoning performance  



## 📁 Project Structure
