# RAG Project

This project is a simple **Retrieval-Augmented Generation (RAG)** pipeline.  
It combines a local document store with a language model to let you query PDFs and other text sources in natural language.

### How it works
1. **Define embeddings** → The embedding model is configured in `get_embedding_function.py`.  
2. **Populate the database** → Run `populate_database.py` to process PDFs/text files from the `data/` folder, split them into chunks, create embeddings, and store them in a local Chroma database.  
3. **Query the data** → Use `query_data.py` to embed a user question, retrieve the most relevant chunks, and pass them to a language model (via LangChain + Ollama/OpenAI) for a contextual response.

### Features
- Drop PDFs into the `data/` folder and build your own searchable knowledge base.  
- Local persistence with **ChromaDB** (fast + lightweight vector store).  
- Modular design: swap out embeddings or language models easily.  
- Command-line interface for querying your knowledge base.

### Usage
```bash
# activate your venv
source .venv/bin/activate  

# install dependencies
pip install -r requirements.txt  

# step 1: populate the database with your PDFs
python populate_database.py  

# step 2: query the data
python query_data.py "What are the main rules mentioned in the PDFs?"
