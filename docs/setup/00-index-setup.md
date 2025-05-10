# Getting Started with NanoBot

This guide will help you set up and start using NanoBot.


## Installation Prerequisites

- Python 3.10+ (I am using 3.12.x)
- PostgreSQL with pgvector extension in 1 of the following configurations:
      - Local Pastgres Installation
      - Neon database URL (neon.tech)
- OpenAI API key
- Logfire token (for logging LLM calls)

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/worldlycode/nanobot-dev.git
   cd nanobot-dev
   ```

2. Create a virtual environment:
   ```bash
   python -m venv .venv
   source .venv/bin/activate  # On Windows: .venv\Scripts\activate
   ```

3. Install dependencies:  
   ```bash
   pip install -r requirements.txt
   ```
   the current `requirements.txt` file includes the following:
   ```bash
   # Database
   psycopg2-binary

   # Configuration
   pydantic-settings
   python-dotenv

   # Template Engine
   jinja2

   # Logging
   logfire

   # Data Processing
   pandas
   matplotlib

   # Document Processing
   docling
   docling-core

   # OpenAI
   openai

   # Tokenization
   tiktoken

   # Web UI
   streamlit

   # if you use Jupyter notebooks
   ipykernel

   #testing
   pytest
   ```
   Note this make take severl minute as the Docling library installs several ML models from hugging face, and also pytorch packages to run these locally

## Setup

See more details in the following setup files

1. Set up environment variables:  
   > **NOTE:** This section is under development  
   Create a `.env` file with the following variables:
   ```
   OPENAI_API_KEY=your_openai_api_key
   LOCAL_DB_NAME=nanobot
   LOCAL_DB_USER=postgres
   LOCAL_DB_PASSWORD=your_password
   LOCAL_DB_HOST=localhost
   LOCAL_DB_PORT=5432
   LOGFIRE_TOKEN=your_logfire_token
   NEON_URL=your_neon_db_url
   USE_NEON=False (defaults to using local db)
   ```

2. Initialize the database:  
   > **NOTE:** This section is under development
   ```bash
   python -m app.database.db_setup
   ```

3. Run the test files:  
   Run the following command:
   ```bash
   pytest tests
   ```

## Running the Application

Start the Streamlit web interface from the root directory:

```bash
streamlit run nanobot.py
```

This will open a web browser with the NanoBot interface.