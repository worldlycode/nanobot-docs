# Document Conversion and Chunking

This guide explains how NanoBot processes documents, from initial conversion to chunking and embedding.

## Supported Document Types

NanoBot supports various document types through its document conversion pipeline:

- **PDF (.pdf)**: Full support for text extraction, including tables and basic formatting
- **Microsoft Word (.docx)**: Support for text, tables, and document structure
- **Text files (.txt)**: Plain text processing
- **Web Pages (URLs)**: Extract content directly from web pages


### Document Conversion

The first step in processing a document is converting it to a structured format that preserves the document's content and structure. This is handled by the `DocumentService` class using the Docling library.

```python
from app.services.document_service import DocumentService

# Initialize the service
document_service = DocumentService()

# Convert a document
converted_doc = document_service.convert_document("path/to/document.pdf")
```

During conversion, NanoBot:  

- Extracts text content  
- Preserves document structure (headings, paragraphs)  
- Identifies metadata (title, author, etc.)  
- Optionally saves intermediate formats for debugging  

