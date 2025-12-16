# 🧠 Intelligent Multi-Document Q&A System  
### Enhanced Retrieval-Augmented Generation (RAG) with Document Intelligence

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.x-blue.svg" />
  <img src="https://img.shields.io/badge/LLM-Google%20Gemini-purple.svg" />
  <img src="https://img.shields.io/badge/RAG-LlamaIndex%20%2B%20FAISS-green.svg" />
  <img src="https://img.shields.io/badge/UI-Gradio-orange.svg" />
  <img src="https://img.shields.io/badge/Status-Production--Ready-success.svg" />
</p>

---

## 📄 Project Overview

This project implements an **Intelligent Multi-Document Question Answering System** based on an **Enhanced Retrieval-Augmented Generation (RAG) pipeline**.

It is designed to handle **complex, heterogeneous PDF documents** commonly found in industries such as **finance**, **legal**, and **mortgage services**, where critical information is distributed across multiple document types within a single file.

Unlike standard RAG systems, this solution integrates **Document Intelligence** to improve retrieval precision and answer quality.

---

## 💡 Problem Statement

Professionals in regulated industries face three major challenges:

1. 📑 **Multiple document types** (contracts, fee sheets, disclosures) bundled into a single PDF  
2. 🔍 **Keyword-based search limitations** that fail to capture semantic meaning  
3. ⏱️ **Manual document review** that is slow, costly, and error-prone  

Traditional RAG systems retrieve content blindly across all documents, often introducing **irrelevant context** that degrades LLM responses.

---

## 🎯 Solution: Enhanced RAG with Document Intelligence

This project introduces an **end-to-end RAG architecture** that incorporates **LLM-powered document classification and query routing** before retrieval.

### Key Innovations

- 🧠 **Multi-Document Classification**  
  Each page or segment is classified into a logical document type (e.g., *Mortgage Contract*, *Lender Fee Sheet*) using an LLM.

- 🏷️ **Metadata-Aware Indexing**  
  Every text chunk is stored with rich metadata:
  - `document_id`
  - `document_type`
  - `page_range`

- 🎯 **Query Routing**  
  User questions are analyzed to determine **which document types are relevant**, reducing retrieval noise and improving answer precision.

---

## 🏗️ Architecture Overview

The system is organized into **three logical layers**:

### 1️⃣ Ingestion Layer

- Reads multi-page PDF files  
- Segments PDFs into logical documents using LLM-based classification  
- Chunks text and generates embeddings  
- Stores embeddings and metadata in a FAISS vector index  

**Technologies used:**  
`PyMuPDF`, `PyPDF2`, `Sentence Transformers`, `LlamaIndex`, `FAISS`

---

### 2️⃣ Query Layer

- 🧭 **Query Router** analyzes the user question  
- Identifies relevant document types  
- Performs **filtered vector search** restricted to those document types  

This step drastically reduces irrelevant context.

---

### 3️⃣ Generation Layer

- Retrieved, context-specific chunks are passed to the LLM  
- The LLM generates a **precise, grounded answer**  
- Answers reference the originating document types  

**LLM used:** Google Gemini

---

## ⚙️ Technical Stack

| Component | Technology | Purpose |
|----------|------------|---------|
| Core Language | Python 3.x | End-to-end system implementation |
| LLM | Google Gemini API | Document classification & answer generation |
| Document Processing | PyMuPDF, PyPDF2 | Text extraction from complex PDFs |
| Embeddings | all-MiniLM-L6-v2 | Semantic vector representation |
| Indexing & Retrieval | LlamaIndex + FAISS | RAG orchestration & fast vector search |
| UI | Gradio | Interactive web-based interface |

---

## ✨ Key Features

| Feature | Impact |
|--------|--------|
| Multi-Document Classification | Enables logical segmentation inside a single PDF |
| Query Routing | Prevents irrelevant documents from polluting context |
| Metadata Filtering | Improves retrieval precision |
| Scalable Vector Search | Efficient handling of large document sets |
| Interactive UI | Easy document upload and real-time Q&A |

---

## 🚀 Getting Started

### Prerequisites

- ✅ Google Gemini API Key  
- ✅ Google Colab account **or** local Python environment  

---

### Installation & Usage

#### 1️⃣ Clone the Repository

```bash
git clone https://github.com/your-username/intelligent-rag-qa.git
```

#### 2️⃣ Open the Notebook

Open the main notebook (e.g. `Enhanced_RAG_Pipeline.ipynb`) in Google Colab or locally.

#### 3️⃣ Configure API Key

Set your Google Gemini API key securely  
(Colab Secrets are recommended).

#### 4️⃣ Run the Pipeline

Execute all notebook cells sequentially.  
The final cell launches the **Gradio web interface**.

---

## 🌟 Project Context

This project was developed during the  
**Outamation Advanced Externship – AI-Powered Document Insights & Data Extraction**,  
in collaboration with **Extern & Outamation**.

It demonstrates:

- Production-ready RAG design  
- Advanced NLP and vector database usage  
- Full-stack AI application development
```
