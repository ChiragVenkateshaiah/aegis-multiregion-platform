# System Context Diagram (C4 Level 1)



```mermaid
flowchart TB

    user["Client Applications"]
    merchants["Merchant Systems"]
    admins[Operations Engineers]

    aegis["AEGIS Platform"]

    bank["External Banking Network"]
    monitoring["Monitoring & Alerting Systems"]

    user -->|"Payment Request"| aegis
    merchants -->|Transaction Events| aegis

    aegis -->|"Payment Settlement"| bank
    aegis -->|Metrics & Logs| monitoring

    admins -->|"Monitor System"| monitoring
```

## What this communicates

This diagram explains in one glance:

Actors:

- Client Applications
- Merchant Systems
- Operations Engineers


External systems:

- Banking Network
- Monitoring Systems


Core system:

- AEGIS Platform
