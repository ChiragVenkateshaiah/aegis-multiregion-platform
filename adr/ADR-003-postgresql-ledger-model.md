# ADR-003: Use PostgreSQL for Ledger Storage

Status: Accepted

Date: 2026-03-14

## Context

The AEGIS platform maintains a financial ledger that records all transactions and account balances.

The system requires:

- strong consistency
- transactional guarantees
- reliable relational modeling
- support for complex queries


## Decision

PostgreSQL will be used as the primary database for the ledger system.

## Alternatives Considered

### MySQL

Pros:
- widely used relational database

Cons:
- fewer advanced features compared to PostgreSQL

### DynamoDB

Pros:
- fully managed
- high scalability

Cons:
- eventual consistency
- limited relational capabilities

### CockroachDB

Pros:
- distributed SQL database

Cons:
- operational complexity
- heavier resource requirements

## Consequences

Pros
- ACID-compliant transactions
- strong consistency guarantees
- mature ecosystem
- well suited for financial ledger models

Cons
- horizontal scaling requires careful design
