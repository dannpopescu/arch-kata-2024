# ADR-007: Async HR System Integrator

## Date:
2024-09-27

## Status:
Accepted

## Context:
We are designing an application that pushes data to external HR systems which may be down in which case we must be resilient and retry pushing data.
We communicate with external systems we have no control on, meaning we expect those systems to be error-prone and high-latency in which case we must be able to be resilient in case of errors and scale up independently to keep up with the increasing amount of pushes.

## Decision:
The decision has been made to utilize Kafka as an intermediary queueing system for pushing unlocked CVs which allows replaying failing messages after some time.

## Consequences:

### PROS:
- **Increased Resilience:** We can retry requests to external HR systems by replaying failing messages on Kafka.
- **Independent Scalability:** We can scale up the HR System Integrator independently than rest of the ecosystem.

### Cons:
- **Increased Complexity:** Managing an extra service to communicate with HR systems. 