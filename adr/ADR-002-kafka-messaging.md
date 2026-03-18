# ADR-002: Use Kafka for Transaction Processing

Status: Accepted

Date: 2026-03-14

## Context

The AEGIS platform processes financial transactions asynchronously to ensure high throughput and reliability.

A messaging system is required to:

- decouple API services from transaction processing
- provide durable event storage
- allow reply of events
- support horizontal scaling

## Decision

Apache Kafka will be used as the primary messaging for transaction processing.

The Payment API publishes transaction events to Kafka topics, which are consumed by Transaction Processor services.

## Alternatives Considered

### AWS SQS

Pros:
- Fully managed
- Simple to operate

Cons:
- Limited event replay capability
- Less flexible event streaming model

### RabbitMQ

Pros:
- Mature message broker
- Flexible routing

Cons:
- Less suitable for event streaming
- Limited long-term event retention


## Consequences

Pros
- High throughput event streaming
- Durable distributed log
- Ability to replay events
- Horizontal scalability

Cons
- Higher operational complexity
- Requires cluster management