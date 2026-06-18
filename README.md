# 🧠 Swami Vivekananda RAG System

> **Production-Style Retrieval-Augmented Generation (RAG) Pipeline** built on the complete works of Swami Vivekananda using Semantic Chunking, Vector Search, ChromaDB, and Hugging Face LLMs.

![Python](https://img.shields.io/badge/Python-3.10+-blue)
![RAG](https://img.shields.io/badge/GenAI-RAG-green)
![ChromaDB](https://img.shields.io/badge/VectorDB-ChromaDB-orange)
![Transformers](https://img.shields.io/badge/HuggingFace-Transformers-yellow)
![License](https://img.shields.io/badge/License-MIT-brightgreen)

---

## 📚 Table of Contents

* [Overview](#-overview)
* [Dataset](#-dataset)
* [Architecture](#-architecture)
* [Features](#-features)
* [Pipeline Flow](#-pipeline-flow)
* [Semantic Chunking](#-semantic-chunking)
* [Embeddings](#-embeddings)
* [Vector Database](#-vector-database)
* [RAG Workflow](#-rag-workflow)
* [Sample Queries](#-sample-queries)
* [Tech Stack](#-tech-stack)
* [Project Structure](#-project-structure)
* [Future Enhancements](#-future-enhancements)
* [Learning Outcomes](#-learning-outcomes)

---

# 🚀 Overview

This project demonstrates an end-to-end **Retrieval-Augmented Generation (RAG)** system built using the **Complete Works of Swami Vivekananda**.

The system:

✅ Extracts text from a large PDF corpus

✅ Creates structured documents

✅ Performs semantic chunking

✅ Generates vector embeddings

✅ Stores vectors in ChromaDB

✅ Retrieves relevant context

✅ Uses an LLM to answer questions grounded in the source material

---

# 📖 Dataset

### Source

https://www.vedanta-pitt.org/wp-content/uploads/2020/05/Complete_Works_of_Swami_Vivekananda_all_volumes.pdf

### Contents

* Lectures
* Discourses
* Interviews
* Newspaper Reports
* Conversations
* Letters
* Essays
* Poems
* Historical Notes

---

# 🏗️ Architecture

```text
                    User Question
                           │
                           ▼
                  Query Embedding
                           │
                           ▼
                     ChromaDB
                           │
                   Top-K Retrieval
                           │
                           ▼
                  Context Builder
                           │
                           ▼
                    HuggingFace
                         LLM
                           │
                           ▼
                    Final Answer
```

---

# ✨ Features

### 📄 Document Processing

* PDF Download & Parsing
* Structured Document Creation
* Metadata Preservation
* Page Tracking

### ✂️ Advanced Chunking

* Paragraph Chunking
* Sentence Chunking
* Semantic Chunking
* Token-Aware Chunking
* Context Overlap

### 🔍 Retrieval

* Semantic Similarity Search
* Top-K Retrieval
* Metadata Filtering
* Context Reconstruction

### 🤖 LLM Integration

* Hugging Face Models
* Context-Aware QA
* Grounded Responses
* Hallucination Reduction

---

# 🔄 Pipeline Flow

```text
PDF
 │
 ▼
Text Extraction
 │
 ▼
Document Structuring
 │
 ▼
Semantic Chunking
 │
 ▼
Embedding Generation
 │
 ▼
ChromaDB Storage
 │
 ▼
Semantic Retrieval
 │
 ▼
Context Construction
 │
 ▼
LLM
 │
 ▼
Answer
```

---

# 🧩 Semantic Chunking

Unlike traditional fixed-size chunking, this project groups paragraphs based on **meaning**.

### Strategy

* Generate paragraph embeddings
* Calculate cosine similarity
* Merge related paragraphs
* Split on topic changes
* Respect token limits
* Preserve context overlap

### Benefits

✅ Better retrieval quality

✅ Reduced context fragmentation

✅ Higher answer relevance

✅ Production-ready approach

---

# 🧠 Embeddings

### Model

```python
BAAI/bge-small-en-v1.5
```

### Why BGE?

* High retrieval performance
* Fast inference
* Strong semantic understanding
* Lightweight deployment

---

# 🗄️ Vector Database

### ChromaDB

Each chunk stores:

| Field      | Description           |
| ---------- | --------------------- |
| ID         | Unique Chunk ID       |
| Text       | Chunk Content         |
| Volume     | Book Volume           |
| Section    | Section Name          |
| Subheading | Topic                 |
| Pages      | Source Pages          |
| Embedding  | Vector Representation |

---

# 🔎 RAG Workflow

### Step 1

User asks:

```text
When did Swami Vivekananda first arrive in America?
```

### Step 2

Generate query embedding.

### Step 3

Search ChromaDB.

### Step 4

Retrieve top relevant chunks.

### Step 5

Build context.

### Step 6

Pass context to LLM.

### Step 7

Generate grounded answer.

---

# 💡 Sample Queries

```text
What is Karma Yoga?
```

```text
What did Swami Vivekananda teach about religion?
```

```text
What were his views on education?
```

```text
When did Swami Vivekananda first visit America?
```

```text
What was discussed at the Parliament of Religions?
```

---

# ⚙️ Tech Stack

| Category        | Technology             |
| --------------- | ---------------------- |
| Language        | Python                 |
| Notebook        | Google Colab           |
| Embeddings      | Sentence Transformers  |
| Embedding Model | BAAI/bge-small-en-v1.5 |
| Vector DB       | ChromaDB               |
| LLM             | Hugging Face Models    |
| Framework       | Transformers           |
| Backend         | PyTorch                |

---

# 📂 Project Structure

```bash
.
├── swamivivekanad.ipynb
├── README.md
├── data/
│   └── Complete_Works_of_Swami_Vivekananda.pdf
├── chunks/
├── embeddings/
└── chromadb/
```

---

# 📈 Future Enhancements

* [ ] Hybrid Search (BM25 + Vector Search)
* [ ] Cross Encoder Reranking
* [ ] Citation-Based Responses
* [ ] Streamlit UI
* [ ] LangChain Integration
* [ ] Evaluation Metrics
* [ ] Agentic RAG
* [ ] Multi-Document Support

---

# 🎯 Learning Outcomes

This project demonstrates practical experience with:

* Retrieval-Augmented Generation (RAG)
* Semantic Search
* Embedding Models
* Vector Databases
* Document Processing
* Semantic Chunking
* Context Engineering
* LLM Integration
* Production AI Pipelines

---

# 👨‍💻 Author

### Vieer Dwivedi

⭐ If you found this project useful, consider starring the repository.
