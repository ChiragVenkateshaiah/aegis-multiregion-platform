
# ADR-005: Use Terraform for Infrastructure as Code

Status: Accepted

Date: 2026-03-15

## Context

The AEGIS platform requires repeatable and automated infrastructure provisioning.

Infrastructure components include:

- VPC networking
- compute instances
- database
- load balancers
- security groups

Manual infrastructure setup is error-prone and difficult to reproduce.

## Decision

Terraform will be used as the Infrastructure as Code (IaC) tool for provisioning and managing cloud infrastructure.

## Alternatives Considered

#### AWS CloudFormation

Pros:

- native AWS integration

Cons:

- limited multi-cloud capability
- less flexible module ecosystem


#### Pulumi

Pros:

- infrastructure defined using general-purpose languages

Cons:

- smaller community
- less widespread adoption


## Consequences

Pros

- declarative infrastructure definitions
- reproducible environments
- strong module ecosystem
- widely adopted industry tool

Cons

- requires state management

