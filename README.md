# Harnessing RAG in Kidney Failure Risk Prediction

This project presents a **Retrieval-Augmented Generation (RAG)** based system designed to improve **early detection and risk assessment of kidney failure**. By integrating **Large Language Models (LLMs)** with a **vector database of clinical case histories**, the system augments diagnostic reasoning with relevant medical context, leading to more **accurate and explainable predictions**.

---

## 🔍 Overview

Kidney failure is difficult to diagnose due to overlapping symptoms with other renal and metabolic diseases. Conventional machine learning methods fail to fully capture unstructured clinical notes, while standalone LLMs often lack domain-specific precision.  

To address these challenges, this project implements a **RAG pipeline** that combines:

- **Case Retrieval Module** – retrieves similar historical kidney failure cases from authoritative nephrology sources.  
- **Diagnostic Module** – fuses patient data with retrieved cases to generate accurate diagnostic insights.  

The system significantly improves diagnostic reliability and demonstrates potential for **clinical decision support systems in nephrology**.

<img width="1919" height="960" alt="image" src="https://github.com/user-attachments/assets/bb9e3583-70ea-4ca6-a093-8d02ef3213c3" />

---

## 📂 Repository Structure
```
📂 Project Root
 ├── app.py                     # Flask-based backend for web interface
 ├── get_embedding_function.py  # Embedding model integration (nomic-embed-text)
 ├── populate_database.py       # Data ingestion, preprocessing, and vector storage
 ├── query_data.py              # Query interface for retrieval and generation
 ├── chroma/                    # ChromaDB vector store files
 ├── frontend/                  # HTML-based frontend for user interaction
 ├── requirements.txt           # Dependencies
 ├── Harnessing RAG in Kidney Failure Risk.pdf  # Full project paper
```

---

## ⚙️ Installation & Setup

### Step 1: Clone the Repository
```bash
git clone https://github.com/PravardhanPrasad/R_A_G.git
cd R_A_G
```

### Step 2: Create a Virtual Environment
```bash
python -m venv venv
source venv/bin/activate   # Linux/Mac
venv\Scripts\activate      # Windows
```

### Step 3: Install Dependencies
```bash
pip install -r requirements.txt
```
---

## ▶️ Usage

### Populate the Database
```bash
python populate_database.py
```

### Run the Web Application
```bash
python app.py
```
Open [http://localhost:5000](http://localhost:5000) in your browser.

### Query via CLI
```bash
python query_data.py --query "What are the early signs of kidney failure?"
```

---

## 📊 Results & Evaluation

- **Evaluation Metric**: BERTScore  
- **Baseline Comparison**: RAG vs standalone LLM  
- **Findings**:  
  - Precision: ↑ 9% over LLM-only  
  - F1-score: ↑ 6% improvement  
  - RAG responses were **more factually accurate and context-aware**  

Example outcome:  
- LLM-only response: General, prone to omissions.  
- RAG-enhanced response: Context-rich, medically grounded, with specific renal biomarkers and risk factors.  

---

## 🧩 Suggested Methodology

1. **Document Ingestion & Preprocessing** – PDFs and text files from nephrology literature are normalized, cleaned, and chunked semantically.  
2. **Chunk Embedding** – `nomic-embed-text` model generates embeddings.  
3. **Vector Storage** – ChromaDB stores embeddings with metadata.  
4. **Query Processing** – Queries embedded and matched with stored chunks.  
5. **Answer Generation** – Top-k relevant chunks fused with user query and passed to LLM.  
6. **Frontend Interaction** – Flask backend + HTML frontend for easy document upload and query.  

---

## 📈 Performance Metrics

| Metric       | Value   |
|--------------|---------|
| Precision    | 88.5%   |
| Recall       | 87.3%   |
| F1-score     | 87.9%   |
| BERTScore ↑  | +9%     |

---

## 🏥 Applications

- **Clinical Decision Support in Nephrology**  
- **Medical Education & Training in Renal Medicine**  
- **Virtual Assistants for Kidney Disease Management**  
- **Knowledge Navigation in Nephrology Research**  

---

## 📜 Conclusion

The proposed **RAG-based kidney failure risk assessment model** outperforms standalone LLMs, reducing hallucinations and improving clinical reliability. Its modular design supports scalability to other renal diseases and integration into real-world healthcare systems.  

---

## 🛠️ Tech Stack

- **Python, Flask** (backend)  
- **ChromaDB** (vector database)  
- **nomic-embed-text** (embeddings)  
- **Ollama LLaMA2** (LLM for generation)  
- **HTML/CSS** (frontend)  

---
