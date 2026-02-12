# RAG Document Q&A System - Assignment 1

##  Assignment Overview
**Assignment 1 Deliverable**: Complete RAG prototype that ingests **10+ technical PDF documents**, stores chunks in ChromaDB, provides natural language Q&A via Streamlit UI, and returns grounded answers with source citations. **Completed within 1-week deadline.**

---

##  Requirements Checklist
| Assignment Requirement | Status |
|----------------------|--------|
| 10+ PDF/MD documents | ✅ **15 technical PDFs ingested** |
| Vector database | ✅ ChromaDB (local) + Pinecone option |
| Natural language interface | ✅ Streamlit UI |
| Source references | ✅ Chunk citations displayed |
| Working prototype | ✅ End‑to‑end pipeline built |
| Technical write‑up | ✅ Included |
| Video walkthrough | ✅ Prepared |

---

##  Key Features
- **PDF Ingestion**: 15 technical documents → 500‑character chunks with 100‑character overlap  
- **Embeddings**: `sentence-transformers/all-MiniLM-L6-v2` (fast + CPU friendly)  
- **Vector Storage**: ChromaDB local persistence  
- **Optional Cloud DB**: Pinecone integration supported  
- **Retrieval**: Cosine similarity search (Top‑K = 5)  
- **Generation**: HuggingFace LLM with grounded prompt  
- **Hallucination Control**: Returns *“Not found in documents”* if context missing  
- **UI**: Streamlit app for natural language Q&A  
- **Source Transparency**: Shows document + chunk references  
- **Metrics**:
  - Retrieval time
  - Generation time
  - Total response time
- **Performance**: ~0.5–1.5 sec avg response on CPU

---

##  Tech Stack
- Python
- LangChain
- HuggingFace Transformers
- Sentence‑Transformers
- ChromaDB (local vector store)
- Pinecone (optional cloud vector DB)
- Streamlit (UI)

---

## 📁 Project Structure
```
RAG-Document-QA/
│
├── app.py                 # Streamlit UI for Q&A
├── ingest.py              # PDF ingestion + embeddings + DB storage
├── query.py               # CLI version for testing
│
├── requirements.txt       # Dependencies
├── README.md              # Documentation
├── .gitignore             # Ignore large/local files
│
├── data/                  # Input PDFs (not required in repo)
├── db/                    # Vector DB (auto-created after ingest)
└── venv/                  # Virtual environment
```

---

## ▶️ How to Run

### 1️⃣ Install dependencies
```
pip install -r requirements.txt
```

### 2️⃣ Ingest documents
```
python ingest.py
```

### 3️⃣ Run Streamlit UI
```
streamlit run app.py
```

---

##  How RAG Works in This Project
1. PDFs are loaded and split into chunks  
2. Chunks converted into embeddings  
3. Stored in vector database  
4. User asks question  
5. Top‑K similar chunks retrieved  
6. Context sent to LLM  
7. Grounded answer generated with sources  

---

##  Hallucination Handling
- Strict prompt: answer only from context  
- If not found → returns “Not found in documents”  
- Source chunks always displayed  

---

##  Future Improvements
- Hybrid search (BM25 + vector)
- Reranking model
- Conversation memory
- Better UI
- Evaluation metrics

---

##  Author
Harish A.N  
RAG Assignment Submission
