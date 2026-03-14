# ADR-001: Use Go for Core Backend Services

Status: Accepted

Data: 2026-03-14

---

## Context

The AEGIS platform requires backend services capable of handling high concurrency, low latency trnsaction processing, and efficient resource utilization.

The platform includes several services:

- Payment API
- Transaction Processor
- Background Workers

These services must be able to process a large number of concurrent requests and scale horizontally across multiple instances.


## Decision

Go (Golang) will be used as the primary programming language for backend services within the AEGIS platform.


## Alternatives Considered

### Python

Pros:
- Large ecosystem
- Rapid development

Cons:
- Slower runtime performance
- Less efficient concurrency model


### Node.js

Pros:
- Large ecosystem
- Event-driven architecture

Cons:
- Single-threaded runtime limitations
- Less common in infrastructure systems


### Java

Pros:
- Mature ecosystem
- Strong enterprise tooling

Cons:
- Higher operational overhead
- Slower development cycle


## Consequences

Pros
- Efficient concurrency using goroutines
- Fast performance and low memory usage
- Widely used in cloud infrastructure tooling
- Simple deployment with static binaries

Cons:
- Smaller ecosystem compared to some languages
- Less mature web frameworks compared to Java ecosystems

