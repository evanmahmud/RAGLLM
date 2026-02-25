# 🇧🇩 Bangla Visual Question Answering using Hybrid RAG + Qwen3-VL

This project implements a Hybrid Retrieval-Augmented Generation (RAG) system for Bangla Visual Question Answering (VQA) using Qwen3-VL and CLIP-based similarity retrieval.

---

## 📌 Project Overview

We compare two approaches:

### 1️⃣ Vanilla Qwen3-VL
Direct multimodal inference:
Image + Question → Qwen3-VL → Answer

### 2️⃣ Hybrid RAG + LLM
Image + Question → CLIP Embedding → FAISS Retrieval → Context Building → Qwen3-VL → Answer

---

## 🧠 Motivation

The dataset shows:
- 42,717 total samples
- Only 4,663 unique embeddings
- Only 948 unique text answers

This high redundancy motivates a retrieval-based approach.

---

## 🏗 Architecture

### 🔹 Vanilla Pipeline

Image + Question  
→ Qwen3-VL  
→ Answer  

### 🔹 Hybrid RAG Pipeline

Image + Question  
→ CLIP Encoder  
→ FAISS Index  
→ Retrieve Top-K similar QA  
→ Prompt Construction  
→ Qwen3-VL  
→ Final Answer  

---

## 📊 Evaluation Metrics

We evaluate using:

- Exact Match
- Soft Match
- Token-level F1
- BLEU
- ROUGE
- Recall@K (retrieval quality)

---

## 📈 Results (Validation - 500 Samples)

Vanilla Qwen3-VL:
- Exact: 0.418
- Soft: 0.430
- F1: 0.4298

Hybrid RAG:
(To be filled after evaluation)

---

## 📦 Components

- Qwen/Qwen3-VL-8B-Instruct (4-bit quantized)
- openai/clip-vit-base-patch32
- FAISS similarity search
- Bangla dataset preprocessing
- Visualization tools

---

## 📊 Visualizations

- Answer type distribution
- Retrieval similarity bars
- Full pipeline visualization
- Embedding redundancy analysis

All figures are saved automatically in high resolution.

---

## ⚠ Observations

- Dataset contains heavy answer repetition
- Many embeddings are identical
- Retrieval similarity often saturates at 1.0
- CLIP may not be optimal for Bangla VQA retrieval

---

## 🚀 Future Work

- Replace CLIP with multilingual CLIP
- Fine-tune retrieval encoder
- Use cross-attention reranker
- Evaluate answer-type specific accuracy
- Improve Bangla token normalization

---

## 🧑‍🔬 Research Goal

To analyze whether retrieval augmentation improves Bangla multimodal reasoning in open-ended VQA tasks.

---

## 👤 Author

Evan  
Bangladesh  
