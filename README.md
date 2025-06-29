# -LLM-Powered-Document-Query-System-using-RAG-and-LangChain-Description:
This project demonstrates a retrieval-augmented generation (RAG) pipeline using LangChain, Groq-hosted LLMs (Mixtral and LLaMA3), and Streamlit to enable question-answering over unstructured data from web sources and PDFs. It leverages embeddings, vector stores, and a retrieval chain to provide context-aware answers.

Features:

Query understanding with Mixtral or LLaMA3 via the Groq API

PDF and web document ingestion and embedding

Document chunking using recursive character splitter

FAISS-based semantic vector retrieval

Contextual question-answering with streaming support in Streamlit

Interactive document similarity viewer with Streamlit expanders

Technologies Used:

Python

LangChain

FAISS

Groq API (Mixtral-8x7b-32768 and LLaMA3-8b-8192)

OpenAI Embeddings (for LLaMA3 pipeline)

Streamlit (UI)

dotenv (environment config)

How It Works:

Documents are loaded from either the web (WebBaseLoader) or a PDF directory (PyPDFDirectoryLoader).

Text is split into chunks with overlap using RecursiveCharacterTextSplitter.

Embeddings are created using OllamaEmbeddings (for Mixtral) or OpenAIEmbeddings (for LLaMA3).

Chunks are embedded and stored in a FAISS vector store.

On user input, the most relevant document chunks are retrieved using vector similarity.

A ChatGroq model generates an answer using the retrieved context.

The answer and the supporting document chunks are displayed.

How to Run:

Clone the repository

Install dependencies using pip or requirements.txt

Set your Groq and OpenAI API keys in a .env file

Run either of the two apps:

For Mixtral-based web Q&A:
streamlit run app.py

For LLaMA3-based PDF Q&A:
streamlit run llama3.py

Environment Variables Required:

GROQ_API_KEY

OPENAI_API_KEY (only for llama3.py)

Project Structure:

app.py: Main app for Mixtral with web-based document loading

llama3.py: PDF-based RAG using LLaMA3 and OpenAI embeddings

us_census/: Directory for PDF ingestion (user-provided)

.env: Environment variables file (not included)
