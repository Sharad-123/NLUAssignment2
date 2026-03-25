# 📌 Natural Language Understanding Projects  
### Word Embeddings + Character-Level Name Generation

This repository contains two NLP projects:

- **Problem 1:** Learning Word Embeddings from IIT Jodhpur Data  
- **Problem 2:** Character-Level Name Generation using RNN Variants  

---

#  Problem 1: Word Embeddings (Word2Vec)

##  Overview

This project trains **Word2Vec models (CBOW and Skip-gram)** on a domain-specific corpus collected from IIT Jodhpur websites to learn semantic word representations.

---

##  Dataset

- **Source:** 19 IIT Jodhpur web pages  
- **Tokens:** 7,179  
- **Vocabulary Size:** 1,963  

### Content Includes:
- Faculty profiles  
- Department pages  
- Research facilities  
- Institute announcements  

---

##  Preprocessing

- Removed HTML tags, URLs, emails  
- Removed numbers and punctuation  
- Lowercasing and whitespace normalization  
- Tokenization (NLTK)  
- Stopword removal  
- Removed domain-specific frequent words  

---

##  Models

###  CBOW
- Predicts target word from context  
- Uses averaged embeddings  

###  Skip-gram (Negative Sampling)
- Predicts context from target  
- Uses negative sampling  

---

##  Hyperparameters

- Embedding Dimension: {50, 100}  
- Context Window: {2, 4}  
- Negative Samples: {5, 10}  
- Optimizer: Adam  
- Epochs: 5  

---

##  Results

###  CBOW (Best)
- Final Loss: **0.501**

###  Skip-gram
- Best Loss: **1.561**

---

##  Analysis

- CBOW performs better on small datasets  
- Larger embeddings improve representation  
- Small context windows reduce noise  

---

##  Semantic Evaluation

### Cosine Similarity
- `research → publication, graduate`  
- `student → placements, alumni`  

### Analogy Tasks
- Limited success due to small corpus  

---

##  Visualization

- **PCA:** Global structure  
- **t-SNE:** Better cluster separation  

---

##  Conclusion (P1)

- CBOW is more stable for small datasets  
- Embeddings reflect domain-specific semantics  
- Corpus size limits performance  

---

#  Problem 2: Name Generation using RNN Variants

##  Overview

This project generates **Indian names at character level** using:

- Vanilla RNN  
- BiLSTM  
- Attention-based RNN  

---

##  Dataset

- **Size:** 1000 names  
- **Vocabulary:** 29 (including special tokens)  

---

##  Models

###  Vanilla RNN
- 2-layer RNN  
- Hidden size: 128  

###  BiLSTM
- Bidirectional LSTM  
- High capacity model  

###  Attention RNN
- RNN + attention mechanism  

---

##  Model Statistics

| Model           | Parameters | Model Size |
|----------------|----------|------------|
| Vanilla RNN    | 63,453   | ~0.24 MB   |
| BiLSTM         | 603,229  | ~2.30 MB   |
| Attention RNN  | 83,806   | ~0.32 MB   |

---

##  Training Setup

- Optimizer: Adam  
- Learning Rate: 0.003  
- Epochs: 20  
- Batch Size: 64  

---

##  Evaluation Metrics

- **Novelty**  
- **Diversity**  
- **Realism**

---

##  Results

| Model          | Novelty | Diversity | Realism |
|----------------|--------|----------|---------|
| Vanilla RNN    | 0.80   | 0.965    | **0.98** |
| BiLSTM         | 1.00   | 0.795    | 0.02    |
| Attention RNN  | 1.00   | **0.975** | 0.24    |

---

##  Observations

###  Vanilla RNN (Best)
- Highly realistic outputs  
- Balanced performance  

###  BiLSTM
- Severe overfitting  
- Repetitive outputs (`kkkk`, `vivivi`)  

###  Attention RNN
- High diversity  
- Suffers from repetition  

---

##  Sample Outputs

**Vanilla RNN**
