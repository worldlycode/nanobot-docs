# Nanobot Overview

## Architecture

Nanobot is a RAG (Retrieval-Augmented Generation) system with a layered architecture:

1. **Presentation Layer**: Streamlit UI (`nanobot.py`)
2. **Service Layer**: Core business logic (`app/services/`)
3. **Data Access Layer**: Database interactions (`app/database/`)
4. **Utility Layer**: Helper functions (`app/utils/`)

## Document Processing Pipeline

Documents flow through the system in these stages:

1. Document conversion (Docling)
2. Text chunking with configurable strategies
3. Embedding generation (OpenAI)
4. Vector storage (PostgreSQL with pgvector)
5. Similarity-based retrieval
6. LLM integration for response generation

## Key Features

- Modular codebase with clean separation of concerns
- Multiple document chunking strategies
- Vector similarity search
- Interactive Streamlit interface
- Enterprise-ready database with transaction support
- Extensible framework for AI integrations

## Core Components:
1. **app/** - Main application code
   - **services/** - Service layer with document processing, chunking, and API integrations
     - `document_service.py` - Complete pipeline for document processing
     - `chunking_service.py` - Document chunking strategies
     - `openai_service.py` - OpenAI API integration
     - `prompt_loader.py` - For loading prompt templates
   - **database/** - Database interactions
     - `setup.py` - Database initialization
     - `common.py` - Shared database utilities
     - `insert.py` - Database insertion operations
     - `retrieval.py` - Vector search and retrieval
     - `transaction.py` - Transaction management
     - `maintenance.py` - Database maintenance tasks
   - **models/** - Data models and validators
   - **utils/** - Utility functions
     - File handling, tokenization, logging, etc.
   - **config/** - Configuration settings
   - **prompts/** - Prompt templates

2. **Main Scripts**:
   - `nanobot_poc.py` - Main Streamlit application with UI
   - `process_and_load.py` - CLI tool for processing documents

### Supporting Directories:
- **data/** - Document storage
- **tests/** - Comprehensive test suite
- **examples/** - Example code 
- **sandbox/** - For experimentation and notebooks
- **logs/** - Log files





