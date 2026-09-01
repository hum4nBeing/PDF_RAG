# ✨ PDF Assistant AI

A production-ready, Retrieval-Augmented Generation (RAG) chatbot built to allow users to interact and chat with multiple PDF documents simultaneously. 

This project demonstrates a modular architecture for building scalable AI applications using LangChain, Streamlit, and ChromaDB.

---

## 🚀 Key Features

- **Multi-Model Support:** Toggle seamlessly between Groq (e.g., LLaMA) and Google Gemini LLMs.
- **Advanced Document Retrieval:** Upload multiple PDFs, process them into embeddings, and chat with your customized knowledge base.
- **Modular Architecture:** Logic is cleanly separated into specialized handlers (`chat`, `sidebar`, `vectorstore`, `llm`, `pdf_handler`), ensuring maintainability and scalability.
- **Robust Vector Database:** Utilizes ChromaDB for efficient storage and retrieval of vector embeddings.
- **Developer Mode:** Includes a live vectorstore inspector for debugging and optimizing the retrieval process.
- **Session Management:** Robust chat history handling, with options to download conversations as a CSV.

---

## 🏗️ Architecture & Tech Stack

### Tech Stack
- **Frontend / UI:** Streamlit
- **LLM Orchestration:** LangChain
- **Vector Database:** ChromaDB
- **Embeddings:** HuggingFace MiniLM & Google GenAI
- **PDF Processing:** PyPDF

### System Flow
1. **Document Ingestion:** Uploaded PDFs are parsed and split into overlapping text chunks.
2. **Embedding:** Chunks are vectorized using either HuggingFace or Google embedding models depending on the selected LLM provider.
3. **Storage:** Vectors are persisted locally in ChromaDB.
4. **Retrieval:** User queries trigger a semantic search in ChromaDB to retrieve the most relevant document chunks.
5. **Generation:** The retrieved context is passed to the LLM (Groq or Gemini) alongside the user's prompt to generate a highly accurate, context-aware response.

---

## 📦 Installation & Setup

### 1. Clone the repository
```bash
git clone https://github.com/hum4nBeing/PDF_RAG
cd PDF_RAG
```

### 2. Set up a virtual environment
```bash
python -m venv venv
source venv/bin/activate  # On Windows use: venv\Scripts\activate
```

### 3. Install dependencies
```bash
pip install -r requirements.txt
```

### 4. Configure API Keys
Create a `.env` file in the root directory and add your API keys:
```env
GROQ_API_KEY=your_groq_api_key_here
GOOGLE_API_KEY=your_google_api_key_here
```

---

## ▶️ Usage

Start the Streamlit server:
```bash
streamlit run app.py
```

1. Select your preferred **Model Provider** and **Model** from the sidebar.
2. Upload one or more **PDFs**.
3. Click **Submit** to process the documents.
4. Start chatting with your data!

---

## 🧼 Tools & Utilities

The sidebar includes several handy utilities for managing your session:
- **🔄 Reset:** Clears session state and restarts the app.
- **🧹 Clear Chat:** Wipes the current conversation history.
- **↩️ Undo:** Removes the last question and response.
- **📥 Download Chat:** Export your chat history to a CSV file.
