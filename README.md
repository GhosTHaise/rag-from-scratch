---

# 📚 RAG From Scratch

*A practical journey into Retrieval-Augmented Generation*

---

## 🔍 Overview

Large Language Models (LLMs) are incredibly powerful — but they are **not always trained on the specific, private, or recent data** that our tasks require.

**Retrieval-Augmented Generation (RAG)** solves this problem.

RAG connects LLMs to **external data sources**, enabling them to generate accurate, context-aware responses using information that wasn’t part of their original training set.

This repository follows a clear, progressive approach to understanding RAG **from absolute basics to advanced techniques**.

---

## 🎯 What You’ll Learn

This project (and video series) will guide you through:

### 🧱 **Core Foundations**

* What RAG is and why it matters
* How indexing works
* How retrieval systems fetch relevant data
* How LLMs integrate retrieved knowledge during generation

### 🚀 **Intermediate Concepts**

* Embeddings and vector stores
* Chunking strategies
* Query transformation + rewriting
* Latency optimization

### 🧩 **Advanced Techniques**

* Handling edge cases in retrieval
* Dealing with hallucinations
* Improving relevance and ranking
* Multi-step or multi-vector RAG
* Using domain-specific metadata

---

## 🔤 RAG Query Translation (Query Rewriting)

**Query Translation** is a powerful RAG technique used to improve retrieval quality when the user’s query is unclear, ambiguous, too short, or phrased differently from how documents are written.

### Why it matters

LLMs can:

* **Rewrite the user query** to match the style of your documents
* **Expand** or **disambiguate** the query
* **Translate** between languages or jargon (“GPU VRAM failure” → “NVIDIA driver error logs troubleshooting”)

### Examples

* *“fix lag”* → rewritten as:
  **“Troubleshooting high latency in real-time processing systems”**

* *“aircraft doc”* → rewritten as:
  **“Retrieve the aircraft maintenance documentation and safety inspection records”**

### Benefits

* Much better retrieval accuracy
* Works extremely well with specialized or technical corpora
* Reduces hallucinations because the retrieved documents are more relevant

This repo covers:

* Basic query rewriting
* Multi-rewrite retrieval (ask the LLM to generate multiple query variants)
* Weighted query expansion

---

## 🔀 RAG Fusion (RRF — Reciprocal Rank Fusion)

**RAG Fusion** combines the results of *multiple retrieval strategies* to improve accuracy and reduce blind spots.

### Why use Fusion?

Different retrievers are good at different things:

* **Dense retrievers** (embeddings) excel at semantic meaning
* **BM25** excels at keyword matching
* **Query rewrites** find hidden relevant passages

Using only one can bias your system.
Fusion lets you **merge all results** into a single ranked list.

### RRF in a nutshell

Reciprocal Rank Fusion gives each document a score based on its ranking:

```
score = 1 / (k + rank)
```

Where:

* `rank` is the position in a specific retriever's list
* `k` is a smoothing factor (usually 60)

Then scores from all retrievers are summed.

### Benefits

* More stable and consistent retrieval
* Greatly reduces false negatives
* Works even if one retriever fails
* Very simple and extremely effective

This repo covers:

* How RRF works under the hood
* Implementing manual RRF
* Evaluating fused rankings
* Combining BM25 + embeddings + rewritten queries

---

## 🧠 Why Build RAG From Scratch?

Modern frameworks simplify RAG, but they also hide how things really work.
Building it manually helps you understand:

* What each step does
* How data flows through a RAG pipeline
* Where bottlenecks appear
* How to customize RAG for your real use-case

If you want to *master* RAG rather than just use it, this is the place.

---

## 📁 Project Structure (Recommended)

```
rag-from-scratch/
│
└── README.md
```

---

## 🎥 Video Series

This project is designed to follow along with a video series that incrementally builds a RAG system.
Each step introduces a new concept, followed by hands-on implementation.

> Start with the basics — end with production-ready RAG skills.
> [https://www.youtube.com/watch?v=wd7TZ4w1mSw](https://www.youtube.com/watch?v=gTCU9I6QqCE&list=PLfaIDFEXuae2LXbO1_PKyVJiQ23ZztA0x&index=12)

---

## 🤝 Contributing

Contributions, suggestions, and improvements are welcome!
Feel free to open PRs or issues.

---

## ⭐ Support the Project

If you find this helpful, consider giving the repository a **star** — it helps visibility and motivates future content.

---

