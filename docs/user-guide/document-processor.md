# Document Processor

## Overview

The document processor is a versatile tool that processes documents and loads them into a database. It handles the entire pipeline from document extraction to chunking and database storage, with support for both local PostgreSQL and Neon database options.

## Features

- Process a single document with configurable chunking strategies
- Batch process all documents in a specified directory
- Automatic database creation and initialization
- Support for multiple chunking strategies for different use cases
- Compatible with both local PostgreSQL and Neon cloud databases

## Prerequisites

- Python environment with required dependencies
- PostgreSQL database or Neon database access
- OpenAI API key for document processing
- Environment configuration in a `.env` file

## Usage Instructions

### Basic Commands

Process a single file with the default chunking strategy:
```bash
python -m document_processor file.pdf
```

Process a single file with a specific chunking strategy:
```bash
python -m document_processor file.pdf --strategy balanced
```

Process all files in the default directory with the default chunking strategy:
```bash
python -m document_processor --all
```

Process all files with a specific chunking strategy:
```bash
python -m document_processor --all --strategy fine_grained
```

### Available Chunking Strategies

- **default**: Standard chunking with moderate chunk size
- **balanced**: Balanced approach between context preservation and chunk size
- **fine_grained**: Smaller chunks for more precise retrieval
- **paragraph**: Chunk by paragraphs regardless of size

### Example Workflow

1. Configure your database and API settings in `.env`
2. Place your documents in the appropriate directory
3. Run the document processor with your preferred strategy
4. The tool will:
   - Create a database if it doesn't exist (for local PostgreSQL)
   - Initialize tables and extensions
   - Process documents according to the selected strategy
   - Store document chunks in the database

## How It Works

1. **Database Setup**: The tool checks if the specified database exists and creates it if necessary
2. **Document Processing**: Documents are processed using the selected chunking strategy and OpenAI's embedding capabilities
3. **Data Storage**: Processed document chunks are stored in the database with vector embeddings
4. **Reporting**: The tool reports on the number of chunks created and stored

## Configuration

The document processor uses environment variables for configuration. Ensure your `.env` file contains the necessary parameters:

### Database Configuration

For local PostgreSQL:  

- `LOCAL_DB_NAME`: Database name  
- `LOCAL_DB_USER`: Database username  
- `LOCAL_DB_PASSWORD`: Database password  
- `LOCAL_DB_HOST`: Database host  
- `LOCAL_DB_PORT`: Database port  

For admin operations (creating databases):  

- `LOCAL_DB_ADMIN_NAME`: Admin database name  
- `LOCAL_DB_ADMIN_USER`: Admin username  
- `LOCAL_DB_ADMIN_PASSWORD`: Admin password  
- `LOCAL_DB_ADMIN_HOST`: Admin host  
- `LOCAL_DB_ADMIN_PORT`: Admin port  

For Neon database:  

- `NEON_DB_URL`: Complete connection URL for Neon database  
- `USE_NEON`: Set to "true" to use Neon instead of local PostgreSQL  

For API Keys:  

- `OPENAI_API_KEY`: Your OpenAI API key for document processing and embeddings  
- `OPENAI_MODEL`: (Optional) The OpenAI model to use (defaults to "gpt-4o")  
 
## Switching Between Local and Neon Databases  

To use a Neon database instead of local PostgreSQL:  

1. Ensure your `.env` file contains a valid `NEON_DB_URL`  
2. Set `USE_NEON=true` in your `.env` file  

## Troubleshooting

If you encounter database connection issues:  

- Verify your database credentials in the `.env` file  
- Ensure PostgreSQL is running (for local database)  
- Check that the Neon database URL is correct (for Neon database)  
- Check that the user has appropriate permissions  

For processing errors:  

- Verify that document files are accessible and not corrupted  
- Check that required Python dependencies are installed  

For OpenAI API issues:  

- Verify your API key is correct  
- Check for rate limiting or quota issues  
- Ensure you have access to the specified models  
