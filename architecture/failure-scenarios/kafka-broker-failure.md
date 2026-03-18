# Kafka Broker Failure Handling

This diagram illustrates how the AEGIS platform maintains availability when a Kafka broker fails.

Kafka topics are replicated across multiple brokers. if one broker fails, leadership is transferred to another replica.


## Diagram

```mermaid
flowchart LR


api["Payment API"]

broker1[Kafka Broker 1]
broker2[Kafka Broker 2]
broker3[Kafka Broker 3]

worker["Transaction Worker"]

api --> broker1

broker1 --> broker2
broker1 --> broker3

broker2 --> worker
broker3 --> worker

broker1 -. failure .-> broker2

broker2 --> worker
```

## Resilience Strategy

Kafka maintains replicated partitions across brokers.

### When Broker 1 fails:

1. A replica broker becomes the new leader.
2. Producers automatically redirect to the new leader.
3. Consumers continue processing messages.

## Reliability Features

- Partition replication
- Leader election
- Durable message storage
