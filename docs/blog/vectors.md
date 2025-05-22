# Vectors Databases

A vector database is what allows for semantic search in your document detabase, which means that it can find the most similar or same documents for a given query. Or in other words, it is the magical element that makes it possible for your chatbot to find the information a user is querying for, whether or not they are using the exact right words or complete ideas. This is because vectors are mathematical representations of concepts aranged in multi-dimensional space, so the correct meaning is taken based on the closeness of the vectors in space instead of merely fething keyword matches. 

Here is an excellent video from IBM Technology that explains the big picture of vectors and embeddings. [What is a Vector Database?](https://www.youtube.com/watch?v=gl1r1XV0SLw)

You can also read a thorough explanation of vectors and embeddings from [IBM](https://www.ibm.com/think/topics/vector-embedding)

Or here from Pinecone [What are Vector Embeddings](https://www.pinecone.io/learn/vector-embeddings/)
I like the diagrams in this one.

### Popular Vector Databases
There are several vector databases available, each with its own strengths and weaknesses. Here are some of the most popular options:
- pgvector
- Weaviate
- Qdrant
- Chroma
- Milvus
- Pinecone

Your chosen vector database might tell you which embeddig model to use, or it might not specify. Either way, you will need an embedding model to pair with your vector database. 

## Embedding Models 
Embedding models are neural networks trained to convert text into dense numerical vectors that capture semantic meaning. They are essentially translators that turn human language into a machine language (in our case, vectors). 

### Popular Embedding Models
Here is a short list of popular embedding models, the main technical difference being the dimension of the vector space they operate in. The size of the model is important because it will affect the amount of memory required to store the embeddings and the amount of time it takes to generate them. 
- OpenAI Embeddings: Several variants available from 1536 to 3072 dimensions
- Open Source Options: 
    - Sentence Transformers (384 to 768 dimensions)
    - BGE Models (1024 dimensions)
    - E5 Models (1024 dimensions)
- Specialized Models:
    - Cohere (good for multilingual cases)
    - Voyage AI (Optimized retreival with long documents)


**How many dimensions are enough?**

More dimensions (Roughly 1024 or more) help with nuanced understanging, but need more storage and memory space, have slower searches, and are more expensive.

Lower dimensions (Roughly 800 or fewer) use less storage, are faster, and less expensive, but will miss subtle semantic differences.


## Considerations for Pairing Embedding Models with Vector Databases
The embedding model and vector database need to be matched on three main criteria:
- Dimensionality (If your model outputs 1536-dimensional vectors, your database index must be configured for exactly 1536 dimensions)
- Same Model for storing and searching (If you use a different model for storing and searching, you will need to convert the stored embeddings to the search model's format)
- Version Consistency (Updates to the model need to be reflected in the vector database, otherwise your searches will break down) We might write more on this in the future, as it is an important issue to consider for production use cases with a large document collection.

### Most vector databases work with any embedding model, but some offer optimizations:

- Pinecone: Works with everything, has starter templates for popular models
- Weaviate: Has built-in integration with OpenAI, Cohere, and Hugging Face
- Qdrant: Excellent for custom/local models
- Chroma: Great for prototyping with different models

What next? Well, you will need to look into the vector databases and embedding models that sound good for your use cases (and budget), but we hope this blog post gives you a head start on your journey to a document chatbot! 

---

**Date:** May 16, 2025
**Author:** Emma Casey
