# Chunking Strategies

After conversion, documents are split into chunks using one of several chunking strategies. Each strategy is optimized for different use cases:

| Strategy | Description | Best For |
|----------|-------------|----------|
| **default** | Standard chunking with moderate chunk size | General purpose use |
| **balanced** | Balanced approach between context preservation and chunk size | Most document types |
| **fine_grained** | Smaller chunks for more precise retrieval | Technical documents, reference materials |
| **context** | Larger chunks that preserve more context | Q&A, summarization tasks |
| **hierarchical** | Chunks based on document's natural hierarchy | Structured documents with clear sections |

The chunking process is handled by the `ChunkingService` class:

```python
from app.services.chunking_service import ChunkingService

    # more code to go here
```