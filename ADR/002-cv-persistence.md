# ADR-002: CV Persistence

## Date:
2024-09-25

## Status:
Accepted

## Context:
We are designing an application that requires storing and retrieving CVs in a scalable and performant manner.

## Decision:
The decision has been made to utilize Amazon S3 as an external storage for uploading the CVs and PostgreSQL as a RDBMS for storing files metadata (name, size, URL). This ensures scalability, resilience and reliability of our system.

## Consequences:

### PROS:
- **Increased scalability:** S3 is highly scalable, allowing us to store unlimited files without worrying about capacity or infrastructure management. PostgreSQL allows for easy indexing and querying, which scales well with increasing amounts of metadata.
- **High performance:** Designed for fast, reliable file retrieval with high availability, S3 can handle massive file sizes efficiently and supports parallel downloads and uploads.
- **Cost Efficiency:** Pay only for the storage and bandwidth used. There's no need to invest in physical hardware for storing high amounts of files. Storing just metadata in PostgreSQL keeps the database lightweight, reducing costs compared to storing large binary data directly in the database.
- **Built-in features:** like replication, encryption, and CDN.

### Cons:
- **Increased complexity:** due to management of two different systems.
- **External costs:** associated with storage and data transfer: S3 charges for storage, data retrieval, and bandwidth. These costs can grow if you have high traffic, frequent file access, or store many large files.
- **Consistency Issues:** Deleting a file from S3 but failing to update the corresponding metadata in PostgreSQL (or vice versa) can lead to data inconsistency issues. Implementing a robust file lifecycle management system is necessary to avoid stale or orphaned entries.
- **Increased latency:** compared to local storage.