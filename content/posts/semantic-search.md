---
title: Semantic Searching
description: A beginners guide to understanding semantic search 
date: 2025-11-21T02:15:00.000-05:00
draft: false
tags: ["Deep Learning","Neural Networks","Pytorch"]
categories: ["AI/Machine Learning"]
---


# Semantic Search

# 💡 Understanding Search and Semantic Search

## 1. Traditional Search (Lexical Search)

**Search** is the fundamental process of retrieving data or documents based on user input.

- **Focus:** It relies purely on **keyword matching**.
- **Mechanism:** It looks for exact or partial word matches between the user's query and the documents.
- **Limitation:** It struggles with **synonyms** and **context**, often resulting in less relevant results if the exact keywords aren't present.

---

## 2. Semantic Search: An Advanced Approach

**Semantic Search** is an advanced method that focuses on the **meaning** and **intent** behind the user's query, moving beyond simple keywords.

- **Mechanism:** It relates the **keyword + context** of the query to the data.
- **Vector Space:** Semantic search operates entirely in a **vector space**, where words and sentences are converted into dense numerical representations called **embeddings**.
    - Vectors that are directionally close are considered **semantically similar**.
- **LLM Integration:** It is frequently used in **Large Language Models (LLMs)** to provide more accurate and contextually relevant responses.
- **Retrieval:** It primarily uses techniques like **k-Nearest Neighbor (kNN)** to find the data vectors closest to the query vector.

---

## 3. Determining the Best Match: Cosine Similarity

The model determines the best match by calculating the **Cosine Similarity Score** between the query vector

### Ranking the Results

The **highest score** (the one closest to **+1.0**) indicates the best match.

| Corpus | Similarity Score | Interpretation | Match Quality |
| --- | --- | --- | --- |
| **C** | **0.65** | Strong positive alignment. | **Best Match** (Closest to 1.0) |
| A | 0.25 | Weak positive alignment. | Low Similarity |
| B | -0.25 | Negative alignment. | Dissimilar |
| D | -0.787 | Strong negative alignment. | Furthest Match (Closest to -1.0) |

The final ranking ensures that **Corpus C** is retrieved as the most relevant result, as its meaning is most closely aligned with the query's intent.