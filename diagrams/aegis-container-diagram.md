# Container Diagram (C4 Level 2)

```mermaid
flowchart LR

    client["Client Applications"]

    dns["Route53 DNS"]

    lb["Application Load Balancer"]

    api["Payment API Service Go + Gin"]

    queue["Kafka Event Stream"]

    worker["Transaction Processor Go Workers"]

    ledger["Ledger Service"]

    db[("PostgreSQL Ledger DB")]

    prom["Prometheus Metrics"]

    grafana["Grafana Dashboards"]

    client --> dns
    dns --> lb
    lb --> api

    api --> queue

    queue --> worker

    worker --> ledger
    ledger --> db

    api --> prom
    worker --> prom
    ledger --> prom

    prom --> grafana
```

## What Each Container Represents

#### Payment API

Handles:

- payment requests
- validation
- authentication

Publishes events to Kafka.

---

#### Kafka Event Stream

Responsible for:

- decoupling API and workers
- buffering transactions
- enabling event replay


#### Transaction Processor

Consumes events and:

- validates transactions
- processes payments
- updates ledger


#### Ledger Services

Responsible for:

- account balances
- transaction recording
- financial consistency


#### PostgreSQL Ledger DB

Stores:

```bash
accounts
transactions
ledger_entries
```

#### Observability Stack

Prometheus collects:

```bash
API latency
transaction throughput
queue depth
error rates
```

Grafana visualizes dashboards.


