# ADR-009: BI Tool

## Date:
2024-09-27

## Status:
Accepted

## Context:
We are designing an application that aggregates lots of data in a Data Warehouse platform, and we need to efficiently aggregate all that information for analysis and reports.

## Decision:
The decision has been made to utilize Looker, a powerful BI Tool for reporting and visualization.

## Consequences:

### PROS:
- **BigQuery Integration:** Looker connects seamlessly with BigQuery and leverages BigQuery’s scalability to analyze massive datasets without the need for data extraction, ensuring the BI tool can handle even large queries efficiently.
- **Speed and Performance:** Looker operates in a real-time fashion by querying BigQuery directly instead of working with extracted datasets, giving users up-to-date information with each query.
- **Powerful Analytics:** Looker uses its LookML language to model data, allowing data analysts to define relationships and logic once, which can be reused across the organization for consistent reporting. Looker has pre-built blocks for Google BigQuery, allowing for faster deployment of analytics and reducing the time needed for custom data modeling.

### Cons:
- **Looker License:** Looker is a premium BI tool with enterprise-level pricing.
- **Learning Curve:** Looker’s LookML requires some learning for data teams to define and manage models. While Looker simplifies reporting, setting up complex data models may require considerable expertise in LookML and data architecture.
- **Latency and Performance Optimization:** Since Looker runs queries directly on BigQuery, the performance of Looker dashboards and reports is directly dependent on how well the underlying queries are optimized. Poor query design can result in slow dashboards and a poor user experience.
- **Limited Cross-Platform Capabilities:** Looker is tightly integrated within the Google Cloud Platform (GCP) ecosystem, which might lead to vendor lock-in. Switching to another cloud provider or platform could involve significant migration efforts and cost.