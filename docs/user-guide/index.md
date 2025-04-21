Welcome to the Nanobot-POC documentation User Guide Pages

## Our Current Selections for Infrastructure

> As of 4/20/2025

The current codebase aims to simplify some of the initial setup and modification of the basic steps of an application.  We have some boilerplate code that organized the steps of a RAG (Retrieval Augmented Generation) Generative AI system, and that has consolidated areas of code where one can modify the parameters of each module, simplyfying the use of the codebase.

### Python as our Language

Pyuthon is the standard language for most Generative AI applications, and is particullary easy to use. This module require `Python 3.12` or above.  

### Document parsing and chunking

We are currently using IBM's [Docling](https://docling-project.github.io/docling/) which can be used to convert most general document formats (and even websites) into a format readable and usable to most Generative AI models.  In particular it is especially good at PDFs, and creates a Docling Document that seperatly identifies and extracts text, tables, pictures, document hierarchy with headers, sections and groups, and understands the content within the context of the page.  

To start, we are extracting all the text and table and the provenance information (such as pages number, file name, and heading the information is part of)

### Database

We currently are using [Neon.tech](https://neon.tech) for our Postgres database.  Postgres is an optimal solution at this early stage as postgres allows, via the [pgvector plugin](https://github.com/pgvector/pgvector-python), semantic similarity searches by vector arithmetic.  

This choice to use [Neon.Tech]() provides a web based solution, using the power of postgres and takes advantage of Neon's capability for data versioning and branching.

### Prompts with Jinja Templates

In this structure, we separate out the prompts for each call to the GenAI model so as to extract this from the working code, to make it more transparent, and to be able to easily modify the prompt for testing.

The prompts are formatted and delivered to the model using Jinja templates, which also allows us to separate the functionality from the other Python code as well.  

### Choice of Generative AI Models

At this point we are using OpenAI for all aspects of our GenAI needs.  This includes using `4o` for the cleaning and formatting of the documents, the embedding of the vectors using , and `4o` for the chat completion steps.  

This choice is currently determined by the quality and output of the model, and the ease of interacting with the API.  
