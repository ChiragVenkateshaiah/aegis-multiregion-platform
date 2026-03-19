
# Payment Processing -- Sequence Diagram

This sequence diagram illustrates the lifecycle of a payment request through the AEGIS system.

## Diagram

```mermaid
sequenceDiagram

participant Client 
participant API as Payment API 
participant Kafka 
participant Worker as Transaction Processor 
participant Ledger 
participant DB as PostgreSQL 

Client->>API: POST /payments 

API->>API: Validate request 
API->>Kafka: Publish transaction.created event 

Kafka-->>Worker: Deliver event 

Worker->>Worker: Validate transaction 

Worker->>Ledger: Write ledger entry 

Ledger->>DB: Insert transaction record 

DB-->>Ledger: Success 

Ledger-->>Worker: Ledger update confirmed 

Worker-->>Kafka: Commit message offset
```

## Flow Explanation

1. Client sends payment request.
2. Payment API validates request.
3. API publishes event to Kafka.
4. Transaction processor consumes event.
5. Processor validates transaction.
6. Ledger service writes entry to database.
7. Database confirms persistence.
8. Worker commits message offset.

