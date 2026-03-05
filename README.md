# 🛡 AEGIS — Cloud-Native Resilient Platform

> A production-grade, cloud-native infrastructure platform built on AWS to simulate real-world distributed systems, multi-region resilience, and internal developer enablement.

---

## 🌎 Project Overview

AEGIS is an infrastructure engineering project designed to simulate a **resilient cloud platform** operating under real-world distributed system constraints.

The project explores how modern cloud platforms are designed to handle:

- Regional failures
- Distributed workloads
- Service scalability
- Infrastructure automation
- Observability and reliability engineering

The goal is to explore how **modern cloud platforms are architected and operated in production **environments.**

---


AEGIS is a cloud-native, event-driven infrastructure platform designed to demonstrate:

- Production-ready cloud networking
- Kubernetes-native service deployment
- Distributed systems resilience
- Multi-region failover strategy
- Observability and reliability engineering
- Cost-aware architectural tradeoffs

This project simulates the responsibilites of Platform Engineering team inside a product company, where internal teams depend on reliable infrastructure foundations.

---

## ✍🏼 Engineering Blog Series

The engineering journey behind AEGIS is documented as a technical blog series.

Part 1 - Development Environment Setup
Part 2 - Multi-Region Architecture Design *(coming next)*
Part 3 - AWS Network Topology
Part 4 - Infrastructure as Code

---


## 🎯 Vision

> Design for failure. Operate for resilience. Optimize for cost.

AEGIS explores how modern distributed systems are designed under real-world constraints:

- Infrastructure failure is inevitable
- Regional outages are possible
- Latency and scale are unpredictable
- Cost constraints influence architecture decisions

The system evolves from a single-region deployment to a multi-region resilient architecture.

---

## 🏗 High-Level Architecture
![AEGIS Architecture](/diagrams/v0.1_architecture_diagram.png)

Core request flow:

User Request
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
- Application Load Balancer
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
- AWS CloudWatch

---

## 📈 Architecture Evolution Roadmap

### Phase I - Single Region (Free-Tier Compatible)

- VPC networking
- EC2-hosted Go services
- RDS (Single AZ)
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
- Asynchronous processing first
- Observability by default
- Infrastructure as Code
- Cost-aware scalability
- Automation over normal operations

---

📁 Repository Structure

```bash
aegis-multiregion-platform/
├── docs/
├── infra/
├── services/
├── observability/
├── simulations/
└── scripts/
```
See `docs/architecture.md` for detailed system design.

---

🧪 Reliability & Testing

Planned failure simulations include:

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

Availability target: **99.9%+**

Key reliability metrics:

- Error rate thresholds
- Request latency percentiles (p50 / p95 / p99)
- Mean Time To Recovery (MTTR)
- Replication lag monitoring
- Queue backlog depth


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
- A portfolio project for infrastructure engineering roles

---

🚀 Current Status

> Project Status: **Early Development (Phase I)**

Completed:

- AWS Account configured
- Initial architecture designed
- Repository initialized

---

## ⚙ Local Development Setup

Clone the repository

git clone https://github.com/ChiragVenkateshaiah/aegis-multiregion-platform

Initialize Terraform

terraform init

Plan infrastructure

terraform plan

Apply infrastructure

terraform apply

