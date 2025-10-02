# ⚽ IFAB Laws of the Game RAG Assistant

An **AI-powered Retrieval-Augmented Generation (RAG) assistant** that answers questions about the **IFAB Laws of the Game (football rules)**.  
It allows referees, coaches, players, and fans to query the official rule book in natural language and receive accurate, grounded responses with citations.

---

## 🚀 Features

- Natural language querying of IFAB football rules
- Retrieval-Augmented Generation (RAG) pipeline:
  - Stores laws in a **ChromaDB vector database**
  - Uses **HuggingFace MiniLM embeddings** for semantic search
  - Generates answers with **Groq-powered LLM**
- Provides **chapter references and sources** for transparency
- Configurable thresholds & retrieval depth
- Persistent storage for embeddings
- CLI interface for interactive queries

---

## 🏗️ How It Works

1. **Preprocessing:**

   - Loads IFAB rule book(s)
   - Splits text into 1000-character chunks with 200 overlap

2. **Embedding & Storage:**

   - Encodes chunks with `sentence-transformers/all-MiniLM-L6-v2`
   - Stores them in a **persistent ChromaDB collection**

3. **Querying:**

   - User enters a natural language question
   - Query is embedded and matched against stored rules
   - Relevant laws are retrieved (with metadata: chapter, source, etc.)

4. **Answer Generation:**
   - A **RAG prompt** is constructed
   - Sent to **Groq LLM** to produce a grounded answer

📊 **Pipeline:**  
`User Query → Embedding → VectorDB Retrieval → RAG Prompt → Groq LLM → Answer + Citations`

---

## 📦 Installation

```bash
# Clone repository
git clone https://github.com/<your-username>/ifab-rag-assistant.git
cd ifab-rag-assistant

# Create virtual environment (optional but recommended)
python -m venv venv
source venv/bin/activate  # Linux/Mac
venv\Scripts\activate     # Windows

# Install dependencies
pip install -r requirements.txt
```
# Laws_of_The_Game_IFAB-RAG-Assistant
