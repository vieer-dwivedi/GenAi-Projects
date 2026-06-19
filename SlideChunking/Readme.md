# 📚 AWS RAG Pipeline from Scratch

## 🚀 Pipeline Overview

```text
PDF
 ↓
Document Structuring
 ↓
Metadata Extraction
 ↓
Sliding Window Chunking
 ↓
Token Validation
 ↓
BGE Embedding Generation
 ↓
FAISS Vector Database
 ↓
Semantic Retrieval
 ↓
Cross-Encoder Reranking
 ↓
Metadata-Aware Context Building
 ↓
LLM Inference
 ↓
Answer Generation
```

# 📖 Steps Implemented

## 1. Load PDF

* Read PDF using PyMuPDF
* Skip unwanted pages
* Stream PDF content for processing

---

## 2. Document Structured Chunking

### Get Headings and Paragraphs

* Extract text blocks using `rawdict`
* Detect headings using:

  * Font Size
  * Font Weight (Bold)
* Map paragraphs under corresponding headings

### Print Paragraphs

* Verify document structure
* Inspect extracted content

---

## 3. Add Metadata

Metadata captured for every paragraph:

```python
{
    "source": "aws-overview.pdf",
    "page": 11,
    "heading": "Overview of Amazon Web Services",
    "bbox": (...)
}
```

---

## 4. Sliding Window Chunking

### Add Sliding Chunking

Implemented:

```text
Window Size = 3
Overlap = 1
```

Example:

```text
Chunk 1:
P1 + P2 + P3

Chunk 2:
P3 + P4 + P5

Chunk 3:
P5 + P6
```

### Print Sliding Chunk Difference

* Visualized overlap
* Verified contextual continuity

---

## 5. Token Validation

Validated chunk sizes using tokenizer.

Measured:

* Minimum Tokens
* Maximum Tokens
* Average Tokens
* Distribution Analysis

Example:

```text
Chunks < 50
Chunks 50-100
Chunks 100-300
Chunks > 300
```

---

## 6. BGE (BAAI General Embedding)

### Load BGE Model

Used:

```text
BAAI/bge-small-en-v1.5
```

### Generate Embeddings

Converted every chunk into dense vector embeddings.

### Attach Embeddings Back to Chunks

Stored:

```python
{
    "content": "...",
    "metadata": {...},
    "embedding": [...]
}
```

### Verify Embeddings

Validated:

* Vector dimensions
* Embedding generation success

---

## 7. Semantic Similarity Testing

Performed:

* Query Embedding
* Cosine Similarity
* Similarity Score Validation

---

## 8. Proper Top-K Retrieval

Implemented retrieval pipeline:

```text
User Query
 ↓
Embedding
 ↓
FAISS Search
 ↓
Top-K Candidates
```

---

## 9. Dump into Database

### Mount Google Drive

Persisted vector database externally.

### Store in DB

Saved:

* FAISS Index
* Chunk Metadata

### Write Files to Google Drive

Stored:

```text
faiss_index.bin
chunks.pkl
```

### Save Metadata Separately

Ensured metadata persistence.

---

## 10. Load Database from Google Drive

### Fetch Files

Loaded:

```text
faiss_index.bin
chunks.pkl
```

### Restore Retrieval Pipeline

Reconstructed complete vector store.

---

## 11. Run Sample Query

### Add User Query

Example:

```text
What is cloud computing?
```

### Print Retrieval Output

Displayed:

* Similarity Scores
* Retrieved Chunks
* Associated Metadata

---

## 12. Cross Encoder Reranking

### Load Reranker Model

Used Cross-Encoder model for relevance scoring.

### Get Candidates from FAISS

Retrieved Top-K candidates.

### Create Query-Chunk Pairs

Example:

```python
(query, chunk)
```

### Score Candidates

Generated semantic relevance scores.

### Print Scores

Sorted by:

```text
Highest relevance first
```

---

## 13. Metadata-Aware Context Building

Constructed final context using:

* Heading Information
* Paragraph Range
* Retrieved Content
* Rerank Scores

Result:

```text
Question
 +
Most Relevant Context
 +
Metadata
```

---

## 14. LLM Integration

### Load Model

Integrated Hugging Face LLM.

### Generate Answer

Pipeline:

```text
Question
 +
Context
 ↓
LLM
 ↓
Final Answer
```

---

# 🛠 Skills Developed

### 📄 Document Processing

* PDF Parsing
* Layout Analysis
* Heading Detection
* Structured Extraction

### ✂️ Chunking Strategies

* Structural Chunking
* Paragraph Chunking
* Sliding Window Chunking
* Token-Aware Chunking

### 🧠 Embedding Systems

* BGE Embeddings
* Dense Vector Representations
* Semantic Similarity

### 🗄️ Vector Databases

* FAISS Indexing
* Vector Search
* Top-K Retrieval

### 🔍 Retrieval Engineering

* Semantic Search
* Metadata Filtering
* Retrieval Optimization

### 🎯 Reranking

* Cross Encoder Models
* Relevance Scoring
* Candidate Refinement

### 🏗️ Context Engineering

* Metadata-Aware Context Construction
* Prompt Building
* Retrieval-Augmented Context Generation

### 🤖 LLM Integration

* Hugging Face Transformers
* Retrieval-Augmented Generation (RAG)
* Question Answering Pipelines

---

# 🎯 Final Outcome

Built a complete Production-Style RAG Pipeline featuring:

✅ Structured Document Parsing

✅ Metadata Extraction

✅ Sliding Window Chunking

✅ Token Validation

✅ BGE Embeddings

✅ FAISS Vector Database

✅ Semantic Retrieval

✅ Cross-Encoder Reranking

✅ Metadata-Aware Context Building

✅ Hugging Face LLM Integration

✅ End-to-End Question Answering System
