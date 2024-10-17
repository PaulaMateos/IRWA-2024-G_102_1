# Information retrival and web analysis / 2024 UPF G_102_1

## Overview
This project implements an Information Retrieval System using an inverted index, free text querying and TF-IDF ranking algorithms. The goal is to build an efficient search engine that processes documents and ranks them based on their relevance to user queries.

## Table of Contents
- [Usage](#usage)
- [Functionality](#functionality)
  - [1. Index Creation](#1-index-creation)
  - [2. Querying the Index](#2-querying-the-index)
  - [3. Ranking with TF-IDF](#3-ranking-with-tf-idf)
- [Prerequisites](#Prerequisites)
- [Running the Code](#Running-the-Code)


## Functionality

### 1. Index Creation
The system builds an inverted index using the `create_index` function, which processes the document data and creates a mapping of terms to document IDs.

- **`build_terms(line)`**: 
  - Preprocesses the input text.
  - Converts text to lowercase, removes stop words, and applies stemming.

- **`create_index(lines)`**: 
  - Constructs the inverted index by looping through document lines and storing term positions.

### 2. Querying the Index
The system allows users to perform free text searches.

- **`search(query, index)`**:
  - Normalizes the input query and retrieves document IDs based on the terms present in the index.
  - Returns a unique list of matching documents.

### 3. Ranking with TF-IDF
Documents are ranked using the TF-IDF algorithm for better relevance.

- **`create_index_tfidf(lines)`**:
  - Builds the inverted index while calculating Term Frequency (TF), Document Frequency (DF), and Inverse Document Frequency (IDF).

- **`rank_documents(query_vector, document_vectors)`**:
  - Ranks documents based on cosine similarity between the query vector and document vectors.

- **`search_tf_idf(query, index)`**:
  - Retrieves documents containing query terms and ranks them using TF-IDF.


### Prerequisites
This project is designed to be run in Google Colab. So, necessary datasets and libraries are already loaded in the Colab.


### Running the Code
1. **Indexing the Documents**
   The code builds an inverted index and computes the TF-IDF scores for documents in the dataset:
   ```python
   index, title_index = create_index(lines)
   ```

2. **Searching the Index**
   You can perform a search query by calling the search function:
   ```python
   query = "Your search query here"
   docs = search(query, index)
   ```

3. **Ranking Documents**
   To rank documents by relevance based on the TF-IDF score, use:
   ```python
   ranked_docs = rank_documents(terms, docs, index, idf, tf, title_index)
   ```

### Example Query
You can input a query when prompted:
```python
print("Insert your query (i.e.: Computer Science):")
query = input()
ranked_docs = search_tf_idf(query, index)
```
