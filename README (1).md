# Mr HelpMate
## Overview

This project implements a semantic search system utilizing the RAG (Retrieval-Augmented Generation) pipeline with a cache layer to enhance performance. The system processes PDF documents, retrieves relevant information, and generates concise responses to user queries.

## Objectives

- Develop a semantic search system using the RAG pipeline (Embedding Layer, Search and Rank Layer, Generation Layer).
- Extract information from PDFs, convert it into vector embeddings, and store it in ChromaDB.
- Implement a cache layer to store and retrieve previous queries and results efficiently.

## Design

### 1. RAG Pipeline

- **Embedding Layer:** 
  - Extract text and tables from PDF documents.
  - Convert the extracted data into a dataframe.
  - Generate vector embeddings using OpenAI's `text-embedding-ada-002` model.
  - Store embeddings in ChromaDB.

- **Search and Rank Layer:** 
  - Perform semantic similarity searches on the knowledge base using user queries.
  - Retrieve the top K closest documents or chunks.

- **Generation Layer:** 
  - Use the retrieved documents and user queries to generate coherent answers with a language model.

### 2. Cache Implementation

- **Threshold Setting:** 
  - Set a threshold of 0.2 for semantic similarity to manage cache effectiveness.

- **Storage and Retrieval:** 
  - Store queries and results in a `cache_collection` in ChromaDB.
  - Use ChromaDB utility functions to add documents, IDs, and metadata to the cache.

## Implementation

- **Development Environment:** 
  - Developed using Google Colab.
  - Utilized libraries: `pdfplumber`, `tiktoken`, `openai`, `chromaDB`, and `sentence-transformers`.

- **Functions Implemented:** 
  - Extract text and tables from PDFs.
  - Generate vector embeddings.
  - Perform semantic searches.
  - Implement caching for query results.

## Search Layer

- **Query Design:** 
  - Created queries that reflect potential questions from the policy document to ensure comprehensive testing.

- **Vector Database Search:** 
  - Embedded queries and performed searches against ChromaDB.
  - Implemented a cache mechanism for efficient query result retrieval.

- **Re-ranking Block:** 
  - Integrated cross-encoding models from HuggingFace to improve search result relevance and accuracy.

## Generation Layer

- **Prompt Design:** 
  - Designed effective prompts to guide the language model in generating concise responses based on the retrieved information.

- **Few-Shot Examples:** 
  - Provided examples to improve the accuracy of the model's responses.

## Conclusion

The project successfully implements a semantic search system with RAG and cache layers, achieving efficient document retrieval and accurate information extraction.

## Usage

1. Install required libraries:
   ```bash
   pip install pdfplumber tiktoken openai chromadb sentence-transformers
