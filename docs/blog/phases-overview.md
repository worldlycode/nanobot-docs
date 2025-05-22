**Date:** May 16, 2025
**Author:** Emma Casey


# Overview of Project Phases
With a big project like this, especially one with collaborators accustomed to working alone, it is important to have a clear overview of the project phases. In this post, I will outline the phases of the project and provide a high-level overview of each phase. There will be separate posts for each phase with more information and helpful resources

## Phase 1: Document Collection and Processing
Set up a document storage system that works for you. For us, this started as a Google Sheet where we collected the name, category, file type, and url for each document. We had to gather our documents by hand off our organization's website when we were getting started, but there are other methods to be aware of.

### Methods for collecting documents
- Folder monitoring: System watches specific directories for new files
- Manual uploads: Web interface where users upload files
- API-based ingestion: Documents submitted via API calls
- Integrations with existing document management systems
     - Email attachments via IMAP/POP3 protocols
     - Cloud storage connectors (Google Drive, OneDrive, Dropbox)
     - SharePoint or network file shares
     - CRM systems (Salesforce, HubSpot)

Whichever method(s) you choose, remember to check for password protection, copywrite issues, and file corruption. This is sometimes refered to as "document triage" and is essentially a reminder to think about what metadata you will want from how your documents are stored and that those documents are in good shape for processing.

### Create a Document Processing Pipeline
Once you have your documents collected, you are ready to start building the processing pipeline. The pipeline has three main components: 
- Extract text from the file format in use
- Chunk the document text into smaller  and or logical segments (use a library for this, we like Docling)
- Create metadata for each document (this is the file name, type, url etc. you collected in the document collection phase)

Look for our blog post on Document Conversion Tools where we compare a few popular document parsing tools for their document parsing quality, formatting preservation, chunking strategies (semantic and structural), and Python ecosystem integration.

## Phase 2: Vector Database Setup
In order for your documents to be searchable, you need to create a vector database. A vector database is a database that stores and retrieves data in the form of vectors, which are mathematical representations of the contents of the documents that can be used to perform similarity search. There are three main steps to this phase:
- **Choose a vector database** that works for you. Options include pgvector, Weaviate, Qdrant, Chroma, Milvus, and Pinecone.
- **Generate embeddings** for the chunked document text (this is the process of converting the text into a vector representation using an AI model)
- **Index the embeddings** alongside their metadata in the vector database.

## Phase 3: LLM Integration
The LLM integration serves as the "brain" of your document chatbot system, connecting user queries with your document knowledge base. When a user asks a question, the system converts their query into an embedding vector, searches the vector database for relevant document chunks, then sends these chunks as context to the LLM along with the original query. The LLM synthesizes this information to generate a coherent, informative response that directly addresses the user's question while citing specific documents as sources, creating a seamless experience where users can interact with your entire document collection through natural conversation.
- **Choose an LLM** that works for you. Options include OpenAI's GPT-4, Anthropic's Claude, Cohere, or Mistral

## Phase 4: User Interface
The user interface is the front-end component where team members interact with your document chatbot, typically built as a web application with a familiar chat-style design. This interface includes a message input area, conversation history that maintains context between exchanges, clear attribution showing which documents were referenced in responses, and administrative controls for document management.

- **Build a chat interface** check out frameworks like React, Vue, or Angular for ideas.

## Phase 5: Deployment and Permissions
Once you have your document chatbot built, you will need to deploy it to a server and set up permissions for team members to access it. This will vary depending on your specific needs, but here are some general steps to consider:

- **Deploy to a server** using a cloud provider like AWS, Google Cloud, or Azure.
- **Set up permissions** for team members to access the document chatbot to troubelshoot and update documents.


Be sure to look for additional blog posts that will cover each of these phases in more detail.

---


