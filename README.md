# RAG Project

This project is a simple **Retrieval-Augmented Generation (RAG)** pipeline.  
It combines a local document store with a language model to let you query PDFs and other text sources in natural language.

### How it works
1. **Ingest documents** → PDFs/text files are split into chunks and embedded into a vector database (ChromaDB).  
2. **Ask questions** → User queries are embedded and matched against the database.  
3. **Generate answers** → The most relevant chunks are passed into a language model (via LangChain + Ollama/OpenAI) to produce a contextual response.

### Features
- Easy document ingestion (drop PDFs into the data folder).  
- Local vector store persistence with Chroma.  
- Query interface (`query_data.py`) for asking natural language questions.  
- Modular structure so you can swap embeddings/models as needed.

### Usage
```bash
# activate your venv
source .venv/bin/activate  

# install dependencies
pip install -r requirements.txt  

# ingest PDFs
python ingest.py  

# query your data
python query_data.py "What are the main rules mentioned in the PDFs?"
