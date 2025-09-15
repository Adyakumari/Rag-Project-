# Personal Knowledge Assistant

This project is a **Personal Knowledge Assistant** that allows you to chat with your own PDF documents using Retrieval-Augmented Generation (RAG) and the Llama 3 model via Ollama. The assistant leverages modern LLMs and vector search to answer your questions based on the content of uploaded documents.

## What is RAG?

**Retrieval-Augmented Generation (RAG)** is an approach that combines information retrieval with generative AI models. Instead of relying solely on the model's internal knowledge, RAG retrieves relevant context from external sources (like your PDFs) and uses it to generate more accurate and context-aware answers.

**How it works in this project:**
- Your PDF is split into chunks and embedded into a vector database (ChromaDB).
- When you ask a question, the assistant retrieves the most relevant chunks using semantic search.
- The retrieved context is passed to the Llama 3 model (via Ollama) to generate a concise answer.

## Features
- Upload multiple PDF documents
- Chat with your documents using natural language
- Answers are grounded in your uploaded content
- Powered by Llama 3 (Ollama) and LangChain

## Setup Instructions

Follow these steps to get started:

1. **Install Ollama**
	- Download and install Ollama from [https://ollama.ai/](https://ollama.ai/)

2. **Pull the Llama 3 model**
	- Open your terminal and run:
	  ```zsh
	  ollama pull llama3:latest
	  ```

3. **Install Python dependencies**
	- In your project directory, run:
	  ```zsh
	  pip install -r requirements.txt
	  ```

4. **Run the Streamlit app**
	- Start the assistant with:
	  ```zsh
	  streamlit run main.py
	  ```

5. **Usage**
	- Open the Streamlit app in your browser.
	- Upload one or more PDF documents.
	- Start chatting! Ask questions about your documents and get answers powered by RAG and Llama 3.

## Project Structure

- `main.py` — Streamlit app UI and chat logic
- `rag.py` — RAG pipeline: PDF ingestion, vector store, retrieval, and LLM integration
- `requirements.txt` — Python dependencies

## Technologies Used
- [Streamlit](https://streamlit.io/) — UI for chat and document upload
- [LangChain](https://python.langchain.com/) — RAG pipeline and LLM orchestration
- [Ollama](https://ollama.ai/) — Local LLM serving (Llama 3)
- [ChromaDB](https://www.trychroma.com/) — Vector database for document retrieval

## Notes
- This app only supports PDF documents.
- Make sure Ollama is running and the Llama 3 model is available before starting the app.
- All processing is done locally; your documents are not sent to external servers.

## License

MIT License
