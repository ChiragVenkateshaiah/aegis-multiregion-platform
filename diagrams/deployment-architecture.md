
# AEGIS Deployment Architecture

This diagram shows how the AEGIS platform components are deployed within a cloud infrastructure environment.


## Infrastructure Components

- Route53 DNS
- Application Load Balancer
- Payment API instances
- Transaction worker instances
- Kafka cluster
- PostgreSQL database
- Prometheus monitoring
- Grafana dashboards


## Diagram

```mermaid
flowchart LR

client["Client Applications"]

dns["Route53 DNS"]

lb["Application Load Balancer"]

subgraph AWS VPC

api1["Payment API Instance"]
api2["Payment API Instance"]

worker1["Transaction Worker"]
worker2["Transaction Worker"]

kafka[("Kafka Cluster")]

db[("PostgreSQL Database")]

prom["Prometheus"]

grafana["Grafana"]

end

client --> dns

dns --> lb

lb --> api1
lb --> api2

api1 --> kafka
api2 --> kafka

kafka --> worker1
kafka --> worker2

worker1 --> db
worker2 --> db

api1 --> prom
worker1 --> prom

```

## Infrastructure Behavior

- Load balancer distributes API traffic.
- APIs publish transaction events to Kafka.
- Workers consume events from Kafka.
- Workers update the ledger database.
- Prometheus collects metrics.
- Grafana visualizes system dashboards.

