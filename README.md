# WL2Vec: Word Embeddings of Bolzano’s Wissenschaftslehre (1838)

## Project Overview

This project creates **word embeddings** from Bolzano’s *Wissenschaftslehre* (1838), a major work in logic and philosophy of science. The goal is two-fold: first, to explore the *Wissenschaftslehre* computationally, to get new insights about Bolzano's views; second, to evaluate the utility of word embeddings for text-based philosophical research.

After preprocessing the text (removing manually chosen stopwords and infrequent words), frequent bigrams are extracted and a **sparse co-occurrence matrix** is built. **Truncated Singular Value Decomposition (SVD)** is applied to reduce dimensionality, producing dense embeddings for each word. These embeddings allow analysis of semantic similarity and conceptual structure within the text.

---

## Methodology

1. **Preprocessing**
   - Tokenization of text into sentences and words
   - Removal of manually selected stopwords
   - Filtering words by frequency (keeping words that occur at least 5 times)
   - Filtering of bigrams by frequency (≥3 occurrences)

2. **Bigram and Co-occurrence Extraction**
   - Creation of word pairs (bigrams) within a context window and within sentence boundaries
   - Construction of a sparse co-occurrence matrix

3. **Dimensionality Reduction**
   - Application of Truncated SVD to the sparse matrix
   - Each word is represented as a dense vector in a lower-dimensional space (e.g., 100 dimensions)

4. **Analysis**
   - Cosine similarity between word vectors to find semantically related terms
  
     **Example:** Top 5 words most similar to "Wissenschaft": 'wahrheiten', 'lehren', 'finden', 'logik', 'jeden'

5. **Future Work**
   - Explore analogical proportions to identify meaningful semantic relations
   - Experiment with preprocessing and design choices, such as adding n-grams and adjusting dimensionality reduction
   - Compare co-occurrence embeddings with neural embeddings (e.g., Word2Vec)

---

## Design Choices
- Co-occurrence matrix built from words and bigrams within sentence boundaries to capture local semantic relationships
- Neural networks are avoided to enhance interpretability  

## Limitations
- Small corpus size limits embedding generalizability  
- Stopwords and additional noise are manually chosen based on domain knowledge, which may introduce bias
- Only unigrams are considered; multi-word expressions and higher n-grams are not included yet

## Usage

### Requirements
- Python 3.x  
- `scipy`  
- `scikit-learn`  

Install dependencies with:

```bash
pip install -r requirements.txt```

