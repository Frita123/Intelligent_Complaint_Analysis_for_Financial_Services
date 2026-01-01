CrediTrust Financial – Intelligent Complaint Analysis
Overview

This project transforms raw customer complaints into actionable insights using RAG (Retrieval-Augmented Generation). It focuses on five product categories:

Credit Cards

Personal Loans

Buy Now, Pay Later (BNPL)

Savings Accounts

Money Transfers

Tasks covered here: Task 1 (EDA & Preprocessing) and Task 2 (Chunking & Embedding).

Task 1: EDA & Preprocessing

Load and explore the CFPB complaint dataset (filtered_complaints.csv).

Analyze complaint distribution and narrative lengths.

Filter for the five target products and remove empty narratives.

Clean text (lowercase, remove special characters).

Create a stratified sample (~12,000 complaints) to balance product representation.

Output: complaints_sampled.csv

Task 2: Chunking & Embedding

Split long complaint narratives into 500-character chunks with 50-character overlap.

Use SentenceTransformer (all-MiniLM-L6-v2) to generate embeddings for each chunk.

Build a FAISS vector store for efficient semantic search.

Store metadata (complaint_id, product, chunk_index) for retrieval.

Outputs:

vector_store/faiss_index.bin (FAISS index)

vector_store/metadata.pkl (chunk metadata)