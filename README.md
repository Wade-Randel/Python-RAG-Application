# PDF RAG (Retrieval-Augmented Generation) System
A comprehensive document question-answering system that processes PDF and DOCX files using ChromaDB vector storage and local LLM inference with Ollama.

# Features
Multi-format Support: Process both PDF and DOCX documents \
Local LLM Integration: Uses Ollama with Llama 3.1 for privacy-focused inference \
Vector Database: ChromaDB for efficient similarity search and document retrieval \
Incremental Updates: Add new documents without rebuilding the entire database \
Interactive Q&A: Command-line interface for real-time document querying \
Similarity Filtering: Advanced retrieval with configurable similarity thresholds \
Source Attribution: Automatic citation of source documents and page numbers \
Automatic Setup: Database initialization with error handling and status checking

# Prerequisites
Required Software \
Python 3.8+ \
Ollama installed and running locally \
Required Python packages (see Installation section) \
Ollama Models

# Install the LLM model (instruct = GPU Optimized models)
ollama pull llama3.1 \
ollama run llama3.2:1b-instruct-q4_0 \
ollama run llama3.2:3b-instruct-q4_0


# Install the embedding model (Light, Medium, Heavy)
ollama pull all-minilm \
ollama pull nomic-embed-text \
ollama pull mxbai-embed-large

# Installation
Clone or download the project files \
Install Python dependencies: \
In a virtual environment run:

py -3 -m venv .venv  \
.venv \Scripts \activate

pip install -r requirements.txt

# Setting up React/Node.js
Install React dependencies: \
cd frontend

Intall Node.js dependencies: \
npm install


# Quick Start 
1. Add Your Documents \
Place your PDF and DOCX files in the documents/ directory:

documents/ \
├── research_paper.pdf \
├── manual.docx \
└── report.pdf

# First, set up the database
python db_setup.py

# Terminal 1 - Start the backend
python server.py

# Terminal 2 - Start the frontend  
cd frontend \
npm start

# Access the application at 
http://localhost:5000

# Configuration
Found in config.py

# Advanced Features
Adding New Documents \
The system automatically detects new files

# Add new files to docs/ directory, then run:
python db_setup.py


# Performance Optimization
Memory Management \
Uses garbage collection (gc.collect()) after processing \
Processes documents in configurable batches \
Efficient text splitting with overlap \
Speed Optimization \
ChromaDB for fast vector similarity search \
Configurable similarity thresholds \
Optimized LLM parameters for faster inference \
Storage Efficiency \
Incremental database updates \
Persistent vector storage \
Metadata-based file tracking

# Privacy & Security
Fully Local: No data sent to external services \
Ollama Integration: Local LLM inference only \
Document Privacy: Files processed and stored locally \
No API Keys: No external API dependencies \

# License
This project is provided as-is for educational and research purposes.

# Support
For issues and questions:

Check the troubleshooting section above \
Verify all dependencies are installed correctly \
Ensure Ollama is running with required models \
Check file paths and permissions \
Note: Make sure to adjust the file paths in the configuration files to match your system setup before running the application.

