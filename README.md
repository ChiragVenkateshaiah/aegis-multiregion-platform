# 🛡 AEGIS — Cloud-Native Resilient Platform

> A production-grade, cloud-native infrastructure platform built on AWS to simulate real-world distributed systems, multi-region resilience, and internal developer enablement.

---

## 📌 Overview

AEGIS is a cloud-native, event-driven infrastructure platform designed to demonstrate:

- Production-ready cloud networking
- Kubernetes-native service deployment
- Distributed systems resilience
- Multi-region failover strategy
- Observability and reliability engineering
- Cost-aware architectural tradeoffs

This project simulates the responsibilites of Platform Engineering team inside a product company, where internal teams depend on reliable infrastructure foundations.

---

## 🎯 Vision

> Design for failure. Operate for resilience. Optimize for cost.

AEGIS models how modern distributed systems should be architected under real-world constraints:

- Infrastructure failure is inevitable
- Regional outages are possible
- Latency and scale are unpredictable
- Cost constraints are real

The system evolves from a single-region deployment to a multi-region resilient architecture.

---

## 🏗 High-Level Architecture
(*Insert architecture diagram image here once created*)

Core Flow:

- Application Load Balancer
- API Service (Go)
- SQS (Async Processing)
- Worker Service
- RDS (PostgreSQL)


Future Evolution:

- Kubernetes (EKS)
- Autoscaling
- Observability stack
- Cross-region replication
- Route53 failover

---

## 🧱 Tech Stack

### Cloud Provider

- AWS

### Infrastructure

- VPC
- EC2
- RDS
- SQS
- ALB
- Route53 (Phase II+)
- EKS (Phase II)

### Language

- Go

### Containerization

- Docker
- Kubernetes (EKS)

### Infrastructure as Code

- Terraform

### Observability

- Prometheus
- Grafana
- CloudWatch

---

## 📈 Architecture Evolution Roadmap

### Phase I - Single Region (Free-Tier Compatible)

- VPC networking
- EC2-hosted Go services
- RDS Single AZ
- SQS-based async processing
- Basic observability

### Phase II - Kubernetes Native

- EKS deployment
- Horizontal Pod Autoscaling
- Rolling updates
- Centralized logging
- SLO definition

### Phase III - Multi-Region Resilience

- Cross-region RDS replication
- Route53 DNS failover
- Region promotion strategy
- RPO / RTO measurement
- Chaos testing

---

## 🛡 Design Principles

- Failure is normal
- Stateless compute
- Asynchronous first
- Observability by default
- Infrastructure as Code
- Cost-aware scalability

---

📁 Repository Structure

```bash
aegis-cloud-platform/
├── docs/
├── infra/
├── services/
├── k8s/
├── observability/
└── scripts/
```
See `docs/architecture.md` for detailed system design.

---

🧪 Reliability & Testing

Planned simulations:

- Pod failure
- Node failure
- Database outage
- Regional failover
- Network partition scenarios

Postmortems and incident reports will be documented under:

```bash
docs/incident-reports/
```

---

## 📊 Metrics & SLOs (Planned)

- Availability target: 99.9%+
- Error rate thresholds
- Latency percentile tracking
- MTTR measurement
- Replication lag monitoring


---

💰 Cost Considerations

AEGIS is initially designed to operate within AWS Tier constraints.

Future phases will include:

- Cost optimization analysis
- High availability vs cost tradeoff modeling
- Infrastructure right-sizing

---

🧠 Why This Project Exists

AEGIS is built as:

- A distributed systems learning laboratory
- A cloud platform engineering case study
- A resilience-first infrastructure blueprint
- A portfolio demonstration for product-company infrastructure roles

---

🚀 Current Status

> Project Initialized - v0.1
> AWS Account configured
> Architecture design drafted

---

📚 Related Articles

(*Will link Medium posts here as they are published*)

---

👤 Author

Chirag Venkateshaiah

Cloud-Native Platform Engineering Track

Remote-first infrastructure focus