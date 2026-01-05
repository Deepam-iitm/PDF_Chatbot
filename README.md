# 💬 Chat with Multiple PDFs using Groq

This project is a **Streamlit-based Retrieval-Augmented Generation (RAG) application** that allows users to upload multiple PDF documents and ask natural language questions about their content.

The system extracts text from PDFs, splits it into chunks, embeds them using a sentence-transformer model, stores them in a FAISS vector database, and uses a **Groq-hosted LLM** to generate accurate answers based strictly on the retrieved context.

---

## 🚀 Features

- 📂 Upload **multiple PDF files**
- 🔍 Semantic search using **FAISS**
- 🧠 Context-aware answers using **Groq LLM**
- ❌ Avoids hallucinations when answers are not present
- ⚡ Fast inference with Groq
- 🖥️ Simple and interactive **Streamlit UI**

---

## 🧠 How It Works (Architecture)

1. **PDF Upload**  
   Users upload one or more PDF documents via Streamlit.

2. **Text Extraction**  
   Text is extracted from all pages using `PyPDF2`.

3. **Text Chunking**  
   Large text is split into overlapping chunks using `RecursiveCharacterTextSplitter`.

4. **Embedding & Vector Store**  
   - Embeddings generated using `all-MiniLM-L6-v2`
   - Stored locally using **FAISS**

5. **Retrieval + Generation (RAG)**  
   - Relevant chunks retrieved via similarity search
   - Groq LLM generates answers **only from retrieved context**

---

## 🔧 Libraries & Tools Used

- **Streamlit** – Web UI for interaction
- **LangChain** – RAG pipeline, prompts, and chaining
- **Groq** – Powers fast LLM inference for question answering
- **FAISS** – Vector database for semantic search
- **HuggingFace Embeddings** – Text embeddings using sentence transformers
- **PyPDF2** – PDF text extraction
- **Python-dotenv** – Environment variable management

---

## ⚙️ Installation & Setup

1. Clone the repository
2. Create and activate a virtual environment
   * `python -m venv venv`
   * `source venv/bin/activate`        # macOS/Linux
   * `venv\Scripts\activate`           # Windows
3. Install dependencies
   * `pip install -r requirements.txt`
4. Create a .env file in the root directory
   * `GROQ_API_KEY=your_groq_api_key_here`
5. Run the application
   * `streamlit run app.py`



