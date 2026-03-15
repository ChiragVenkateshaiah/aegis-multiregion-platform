
# Transaction Data Flow

This diagram illustrates the lifecycle of transaction data within the AEGIS platform.

## Diagram

```mermaid
flowchart LR

request["Payment Request"]

api["Payment API"]

event["Transaction Event"]

kafka["Kafka Topic"]

worker["Transaction Processor"]

ledger["Ledger Services"]

db[("Ledger Database")]

request --> api

api --> event

event --> kafka

kafka --> worker

worker --> ledger

ledger --> db
```

## Flow Description

1. Client sends a payment request.
2. Payment API converts the request into a transaction event.
3. The event is published to Kafka
4. A transaction processor consumes the event.
5. Processor validates and processes the transaction.
6. Ledger service records the transaction.
7. The database stores the ledger entry.

