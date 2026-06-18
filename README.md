# Swami Vivekananda RAG System

A Retrieval-Augmented Generation (RAG) application built using the *Complete Works of Swami Vivekananda*. This project demonstrates how to build a production-style RAG pipeline from document ingestion to question answering using semantic search and Large Language Models.

## Dataset

Source PDF:

https://www.vedanta-pitt.org/wp-content/uploads/2020/05/Complete_Works_of_Swami_Vivekananda_all_volumes.pdf

The corpus contains lectures, discourses, interviews, letters, writings, and newspaper reports across multiple volumes.

---

## Features

* PDF text extraction
* Structured document processing
* Semantic chunking using embeddings
* Token-aware chunk sizing
* Context overlap between chunks
* Embedding generation with BGE
* ChromaDB vector storage
* Semantic similarity search
* Metadata-aware retrieval
* RAG pipeline with Hugging Face LLMs
* Context-based question answering

---

## Tech Stack

* Python
* Google Colab
* Sentence Transformers
* BAAI/bge-small-en-v1.5
* ChromaDB
* Hugging Face Transformers
* PyTorch

---

## Pipeline

```text
PDF
 ↓
Text Extraction
 ↓
Document Structuring
 ↓
Semantic Chunking
 ↓
Embedding Generation
 ↓
ChromaDB
 ↓
Semantic Retrieval
 ↓
Context Construction
 ↓
LLM
 ↓
Answer Generation
```

---

## Semantic Chunking

Instead of fixed-size chunks, this project uses semantic similarity between paragraphs to create meaningful chunks.

Features:

* Similarity-based chunk boundaries
* Maximum token limits
* Context overlap
* Retrieval-optimized chunk generation

---

## Embeddings

Model used:

```text
BAAI/bge-small-en-v1.5
```

Embeddings are normalized and stored in ChromaDB along with metadata including:

* Volume
* Section
* Subheading
* Page Numbers

---

## Example Questions

* When did Swami Vivekananda first arrive in America?
* What is Karma Yoga?
* What did Swami Vivekananda teach about religion?
* What are his views on education?
* What was his experience in the West?

---

## Learning Outcomes

This project demonstrates:

* Document chunking strategies
* Semantic search
* Vector databases
* Embedding models
* Retrieval-Augmented Generation (RAG)
* LLM integration using Hugging Face

---

## Future Improvements

* Hybrid Search (BM25 + Vector Search)
* Cross Encoder Reranking
* Streaming Responses
* Citation-Based Answers
* Evaluation Framework
* Web Interface using Streamlit

DevOps Engineer | GenAI Enthusiast | RAG Systems
