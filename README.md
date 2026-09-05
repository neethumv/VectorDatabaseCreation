# Databricks Vector Search Scenarios

This repository demonstrates key Databricks Vector Search capabilities using a Delta table (`company_catalog.company_test.company_docs`) and Unity Catalog governed assets.

## Scenarios Completed

### 1. End-to-End Index Build
- Created a Delta table with Change Data Feed (CDF) enabled.
- Created a Vector Search Endpoint.
- Built a Delta Sync Index.
- Executed a successful `similarity_search()` query.

### 2. Freshness Test
- Inserted new records into the source Delta table after index creation.
- Triggered index synchronization.
- Verified when the new records became searchable.
- Measured indexing latency and documented sync behavior.

### 3. Filtered Search
- Used metadata (`category`) stored alongside document content.
- Executed vector similarity search with metadata filters.
- Demonstrated retrieval restricted to specific document categories.

### 4. Index Type Comparison
Built and compared:

#### Delta Sync Index
- Automatic embedding generation
- Automatic synchronization using CDF
- Lower operational effort

#### Direct Vector Access Index
- Manual embedding generation
- Manual vector upserts
- Greater flexibility and control

### 5. Query Tuning
- Compared retrieval results using `top_k=3` and `top_k=15`.
- Evaluated relevance versus recall tradeoffs.
- Discussed recommended `top_k` values for production RAG systems.
