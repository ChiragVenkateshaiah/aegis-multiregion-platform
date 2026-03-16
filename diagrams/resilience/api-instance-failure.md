
# API Instance Failover

This diagram shows how the AEGIS platform handles Payment API instance failures.

Multiple API instances run behind a load balancer.


## Diagram

```mermaid

flowchart LR

client["Client"]

lb["Load Balancer"]

api1["API Instance 1"]

api2["API Instance 2"]

kafka["Kafa Cluster"]

client --> lb

lb --> api1
lb --> api2

api1 --> kafka
api2 --> kafka

api1 -. crash .-> lb
```

## Resilience Strategy

The load balancer distributes traffic across API instances.

if one instance fails:

1. Health checks detect failure.
2. Load balancer removes the instance.
3. Traffic is routed to remaining instances.


## Reliability Features

- Horizontal scaling
- Health checks
- Automatic traffic rerouting

