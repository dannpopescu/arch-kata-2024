# ADR-006: Persistence

## Date:
2024-09-26

## Status:
Accepted

## Context:
We are designing an application that requires persisting information about the companies, jobs, candidates, orders, etc. for achieving the business needs.

## Decision:
The decision has been made to utilize PostgreSQL as the relational database management system (RDBMS) for storing all required information, allowing for efficient querying and data aggregation.

## Consequences:

### PROS:
- **Open-Source and Cost-Effective:** PostgreSQL is free and open-source, making it a cost-effective solution for a wide range of applications.
- **Scalability:** It is well-suited for scaling vertically with large datasets and supports partitioning and replication for distributing data across multiple servers.
- **Advanced Features and Extensibility:** PostgreSQL supports complex queries, full ACID compliance, advanced indexing (GIN, GiST), and JSONB for handling JSON data, making it highly versatile.
- **Strong Data Integrity and Concurrency:** Offers superior data integrity features, including strict adherence to SQL standards and support for foreign keys, joins, and triggers. Supports multi-version concurrency control (MVCC), ensuring transactions are isolated and concurrent, without locking conflicts.

### Cons:
- **Performance with Write-Heavy Workloads:** PostgreSQL can experience performance issues in very high write-heavy workloads or where large amounts of data are written simultaneously, though it can be tuned to mitigate this.
- **Complex Setup and Configuration:** While PostgreSQL is powerful, setting it up and tuning for performance in complex environments may require advanced expertise.
- **Lacks Native Sharding:** PostgreSQL doesn’t have built-in native sharding support, which can limit its scalability for extremely large datasets without relying on third-party tools or extensions.