# 🧠 GPT Inference Lab — Understanding Decoder-Only LLMs

A hands-on project to explore how **GPT-style (decoder-only) language models** work at inference time.

This notebook focuses on understanding:
- Tokenization (BPE)
- Next-token prediction
- Decoding strategies
- Model uncertainty (entropy)
- Failure modes and prompt sensitivity

---

## 🚀 Objectives

The goal of this project is to move beyond simply *using* LLMs and instead understand:

- How GPT generates text step-by-step  
- How different decoding strategies affect output  
- When and why models fail  
- How uncertainty evolves during generation  

---

## 🧩 Key Components

### 1. Model Setup
- Load GPT-2 using Hugging Face Transformers
- Run inference on CPU/GPU

---

### 2. Tokenization Deep Dive
- Explore Byte Pair Encoding (BPE)
- Analyze token IDs and decoded tokens
- Understand why tokens ≠ words

---

### 3. Next Token Prediction
- Extract logits from the model
- Apply softmax to obtain probabilities
- Inspect top-k candidate tokens

---

### 4. Decoding Strategies

Implemented and compared:

- **Greedy decoding** (deterministic, repetitive)
- **Temperature sampling** (controls randomness)
- **Top-K sampling** (limits candidate tokens)
- **Top-P (nucleus) sampling** (dynamic selection)

---

### 5. Unified Generation Pipeline
A flexible `generate()` function supporting all strategies

### 6. Step-by-Step Debugger

A custom debugger to inspect the generation process token-by-token:

- Current input sequence at each step  
- Top-k candidate tokens and their probabilities  
- Selected token and its probability  

This allows a deeper understanding of **how decisions are made during generation**.

---

### 7. Probability Visualization

- Visualize top-k token probability distributions  
- Compare distributions under different temperatures  
- Analyze whether the model is:
  - **confident (sharp distribution)**  
  - **uncertain (flat distribution)**  

---

### 8. Entropy Analysis

- Compute Shannon entropy of the probability distribution  
- Track entropy across generation steps  
- Plot entropy aligned with generated tokens  

**Key insight:**
- Low entropy → high confidence  
- High entropy → uncertainty / ambiguity  

---

### 9. Prompt Sensitivity

Analyzed how small changes in prompts affect outputs:

- Wording variations  
- Additional context  
- Ambiguous vs specific prompts  
- Instruction-based prompts  

