# Configuration Guide: Using the Settings System


This guide explains how to configure the application through the settings system and environment variables.

## Overview

Our application uses a configuration system based on Pydantic that allows for:
- Sensible defaults for all settings
- Configuration via environment variables or `.env` file
- Type validation to prevent configuration errors

## The Settings Module

The `app/config/settings.py` module defines all application settings in a structured way. Settings are organized into categories like database settings, API keys, file paths, etc.

## Using the `.env` File

The easiest way to configure the application is by creating a `.env` file in the project root. This file contains environment variables that override default settings.

### Basic `.env` Example

```
# Database Configuration

LOCAL_DB_ADMIN_NAME=postgres
LOCAL_DB_ADMIN_USER=postgres
LOCAL_DB_ADMIN_PASSWORD=postgres
LOCAL_DB_ADMIN_HOST=localhost
LOCAL_DB_ADMIN_PORT=5432


LOCAL_DB_NAME=myapp
LOCAL_DB_USER=postgres
LOCAL_DB_PASSWORD=mysecretpassword
LOCAL_DB_HOST=localhost
LOCAL_DB_PORT=5432

# OpenAI API Configuration
OPENAI_API_KEY=sk-your-api-key
LOGFIRE_TOKEN=pylf-your-token

# Neon Database String
NEON_DB_URL=postgresql://neondb_owner:full-neon-url
USE_NEON=true

# File Paths (optional)
DATA_BASE_DIR=data
DATA_ORIGINAL_DOCS_DIR=original_docs
DATA_CONVERTED_DOCS_DIR=converted_docs
DATA_CHUNKING_RESULTS_DIR=chunking_results
```

## Settings Categories

### File Path Settings

Controls where the application stores and processes documents.

| Setting | Environment Variable | Default | Description |
|---------|---------------------|---------|-------------|
| Base Data Directory | `DATA_BASE_DIR` | `data` | Root directory for all data files |
| Original Documents | `DATA_ORIGINAL_DOCS_DIR` | `original_docs` | Where uploaded documents are stored |
| Converted Documents | `DATA_CONVERTED_DOCS_DIR` | `converted_docs` | Where processed documents are stored |
| Chunking Results | `DATA_CHUNKING_RESULTS_DIR` | `chunking_results` | Where document chunks are stored |

### Database Settings

Controls database connection parameters.

| Setting | Environment Variable | Default | Description |
|---------|---------------------|---------|-------------|
| Database Name | `LOCAL_DB_NAME` | | Name of the database |
| Database User | `LOCAL_DB_USER` | | Database username |
| Database Password | `LOCAL_DB_PASSWORD` | | Database password |
| Database Host | `LOCAL_DB_HOST` | | Database server address |
| Database Port | `LOCAL_DB_PORT` | | Database server port |

### OpenAI API Settings

Controls OpenAI API integration.

| Setting | Environment Variable | Default | Description |
|---------|---------------------|---------|-------------|
| API Key | `OPENAI_API_KEY` | | Your OpenAI API key |
| Model | `OPENAI_MODEL` | `gpt-4o` | Model to use for completions |
| Embedding Model | `OPENAI_EMBEDDING_MODEL` | `text-embedding-3-small` | Model for embeddings |
| Temperature | `OPENAI_TEMPERATURE` | `0.0` | Controls randomness in responses |

## Configuration Priority

Settings are loaded in the following order of precedence (highest to lowest):

1. Environment variables
2. Variables in the `.env` file
3. Default values from `settings.py`

This means that environment variables will always override `.env` file settings, which in turn override defaults.

## Accessing Settings in Code

To use these settings in your code:

```python
from app.config.settings import settings

# Database connection parameters
db_params = settings.local_db.get_connection_dict()

# File paths
original_docs_path = settings.file_paths.get_original_docs_path()
converted_docs_path = settings.file_paths.get_converted_docs_path()

# API Settings
openai_key = settings.openai.api_key
```

## Directory Structure

When you first run the application, the system will automatically create all necessary data directories based on your settings. The default structure is:

```
project_root/
└── data/
    ├── original_docs/
    ├── converted_docs/
    └── chunking_results/
```

You can customize these locations using the environment variables listed above.

## Reloading Settings

If you need to reload settings at runtime (after changing environment variables):

```python
from app.config.settings import reload_settings

# Reload all settings
reload_settings()
```

This will recreate all required directories with the updated paths.
