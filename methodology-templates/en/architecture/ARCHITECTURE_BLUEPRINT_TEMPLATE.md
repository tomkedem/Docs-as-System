> ⚙️ **Template Notice:**  
> This file is an official Docs-as-System template.  
> Do not edit it directly inside the project — when initializing a new system,  
> copy it into the `docs/architecture/` directory  
> and save it as `ARCHITECTURE_BLUEPRINT.md`, then adapt it to the actual project.

# Technical Design Template — Architecture Blueprint

**In-project file:** `docs/architecture/ARCHITECTURE_BLUEPRINT.md`  
**Template location:** `templates/architecture/ARCHITECTURE_BLUEPRINT_TEMPLATE.md`  
**Created by:** AI agent (with human guidance)  
**Approved by:** Human (Architect / Tech Lead)  
**Specification type:** Technical specification  

---

## Introductory note – universal usage

This document is part of the generic template set of **Docs-as-System**,  
and serves as a basis for documentation, control and development in any software domain —  
Web, Mobile, Backend, Cloud, Data, AI, Embedded or Multi-Agent.

It assumes a working model where the **agent (AI) executes**,  
and the **human owns authority, approval and control**.  
The agent operates under documented policy, logs every action,  
and performs local commits only in the version control system (Git or similar).  
The human approves the changes and performs the final merge.

> Core principle: **the human defines the intent, the agent executes it, and the system documents everything.**

---

## Document purpose

**At this point, we already know what needs to be built.**  
Now comes the system-level thinking — drawing the technical structure that will deliver the requirements.

This document translates the logical specification (`PROJECT_SPEC.md`)  
into a detailed, implementable technical design.  
It acts as **the bridge between the specification and the implementation plan** —  
defining how the system will actually be built, and ensuring the agent develops in the right direction.

### This document includes:

✅ **Choice of architecture style** – Monolith, Microservices, Modular Monolith, Serverless, Event-Driven, etc.  
✅ **Layered structure** – clear separation between system components (Presentation, Application, Domain, Infrastructure)  
✅ **Component list** – who is responsible for what, and how components depend on each other  
✅ **Responsibility boundaries** – what each component does (and what it explicitly does not do)  
✅ **Data flow mapping** – how information flows between parts of the system  
✅ **Integration points** – connections to external systems, APIs, queues  
✅ **Technology selection** – languages, databases, frameworks, communication tools, cloud/infrastructure  
✅ **Key design decisions** – why specific architectures and technologies were chosen, and when to reconsider them  

### Architectural and technological choices defined here:

In this document **you decide** the concrete architecture and technologies to be used:

**System architecture:**
- **Architectural style** – Monolithic, Microservices, Modular Monolith, Serverless, Event-Driven, Layered, Hexagonal, Clean Architecture, etc.  
- **Communication patterns** – REST, GraphQL, gRPC, Message Queue, Event Bus, WebSockets, etc.  
- **Deployment strategy** – Single Server, Multi-Service, Containerized, Cloud-Native, etc.  

**Technology stack:**
- **Programming language** – Python, C#, TypeScript, Java, Go, Rust, etc.  
- **Databases** – PostgreSQL, MongoDB, Redis, SQL Server, MySQL, DynamoDB, etc.  
- **Frameworks** – FastAPI, .NET, Express, Spring Boot, Django, NestJS, etc.  
- **Messaging / communication tools** – RabbitMQ, Kafka, Redis Pub/Sub, Azure Service Bus, AWS SQS, etc.  
- **Infrastructure** – Docker, Kubernetes, Azure, AWS, GCP, On-Premise, etc.  
- **Monitoring and logging tools** – Grafana, ELK, Prometheus, Application Insights, DataDog, etc.  

These choices **guide the agent** during implementation and ensure architectural and technological consistency across the project.

> **Neutrality note:**  
> The template itself does not recommend any specific technology.  
> Any example in this document is for illustration only.  
> **You** decide what fits your project; this document simply records those decisions.

### How to create it effectively

It is **strongly recommended** to create this document with the help of a conversational model  
(such as ChatGPT, Claude, Gemini).

A conversational model lets you:
- Ask clarifying questions about project requirements  
- Explore alternative architectures based on collective experience  
- Check alignment between technologies and requirements (performance, security, cost)  
- Iterate on the structure until it is clear and coherent  
- Get recommendations for good combinations of tools  

**At the end of the conversation**, copy the content into  
`docs/architecture/ARCHITECTURE_BLUEPRINT.md` in the project,  
and from there move on to the next step: the **detailed implementation plan** (`IMPLEMENTATION_PLAN.md`).

### Why is this document so critical?

This document acts as a **single source of truth for long-term planning, control and documentation**.  
It defines the technical direction, and through it the agent understands:
- Which architecture it must implement  
- Which technologies to use (and not deviate from without approval)  
- What it is allowed to change, and what requires human approval  
- How to analyze and validate consistency between code and documentation  

In addition, the document defines the **agent’s boundaries** — what it is allowed to create, modify or suggest,  
and what requires human approval before implementation.  

This is a core principle of Docs-as-System: documentation as an operational boundary.

This keeps a real continuum between **Intent → Architecture → Execution → Validation**.

---

## System overview

High-level description of the system’s core components and how they relate:

- Interface layer (Frontend / API Gateway / Web Client)  
- Service and business logic layer (Application Layer / Service Layer)  
- Domain layer (Domain Layer / Entities / Business Rules)  
- Data layer (Data Layer / Repositories / ORM / Caching)  
- Queues, messages and events (Messaging / Event Bus / Queue Consumers)  
- External integrations (External APIs / Third-Party Systems)  
- Monitoring and security (Monitoring / Identity / Security Enforcement)  

You may attach a diagram (Mermaid, Eraser.io, etc.) to show the flow between components.

---

## Architectural principles

- **Separation of Concerns** – each layer owns a single responsibility.  
- **Single Source of Truth** – data is maintained from one authoritative source.  
- **Idempotency** – repeated execution of the same operation yields the same result.  
- **Observability** – every action is logged and measured.  
- **Agent Transparency** – the agent never changes code without a log entry and human review.  
- **Human-in-the-Loop** – every significant change requires human approval.  

---

## Layering

| Layer        | Description                      | Main responsibility                  | Possible technologies         | Agent involvement       |
|-------------|----------------------------------|--------------------------------------|-------------------------------|-------------------------|
| Presentation | Exposing external interfaces / UI | REST / GraphQL / Web UI              | Angular / Blazor / React      | Contract validation     |
| Application  | Business processes and workflows | Orchestration of services and logic  | .NET / Node.js / Python       | Optimization suggestions |
| Domain       | Business entities and rules      | Defining entities and behavior rules | Domain models / Rules engine  | Logic analysis          |
| Infrastructure | Data and communication infra   | DB / Cache / Messaging / APIs        | SQL / RabbitMQ / Redis        | Configuration definition |

---

## Service topology

| Service / module | Role | Dependencies | Communication type | Notes |
|------------------|------|-------------|--------------------|-------|
| (to fill)        | (to fill) | (to fill) | REST / Queue / gRPC | (to fill) |

> The agent may propose service boundaries and dependency structures,  
> but the human approves the final topology.

---

## Technology stack selection

| Area          | Chosen technology          | Reason for choice                            | Owner  |
|---------------|----------------------------|----------------------------------------------|--------|
| Backend       | (e.g.) .NET / Java / Node.js | Performance and maintainability             | Human  |
| Messaging     | (e.g.) RabbitMQ / Kafka / SQS | Reliability and built-in retry mechanisms   | Agent + Human |
| Database      | (e.g.) SQL Server / PostgreSQL / MongoDB | Transactions and scalability           | Human  |
| Frontend      | (e.g.) Angular / React / Blazor | API interaction                            | Agent  |
| Infrastructure| (e.g.) On-Prem / Cloud / Hybrid | Security policy and budget              | Human  |
| Observability | (e.g.) Grafana / ELK / Prometheus | Monitoring and incident detection       | Agent  |

> All technologies above are examples only and do not constrain users of this template.

---

## APIs and contracts

| API name | Description | Method | Input | Output | Approved by |
|----------|-------------|--------|-------|--------|-------------|
| (to fill) | (to fill)  | GET / POST / PUT / DELETE | (Schema) | (Schema) | (to fill) |

> Any change to an API contract requires human approval and an update to this document.  
> The agent can perform consistency checks between the specs and the code.

---

## External integrations

| External system | Integration type | Frequency / trigger | Notes |
|-----------------|------------------|---------------------|-------|
| (to fill)       | API / Queue / Webhook | (to fill)        | (to fill) |

---

## Data architecture

Description of entities, relationships and core data sources in the system.

| Entity | Description | Storage type | Main relationships |
|--------|-------------|--------------|--------------------|
| (to fill) | (to fill) | SQL / NoSQL | (to fill) |

> The agent may propose an ERD diagram, but must not change schemas without approval.

---

## Data flows

Describe the logical flow of data in the system:  
Input → Queue → Consumer → DB → response to user.

**Example:**  
Frontend → API Gateway → Application → Queue → Consumer → DB → Notification Service.

---

## Security architecture

- Authentication and authorization based on the organization’s Identity Provider.  
- Encryption in transit and at rest.  
- Separation of permissions by layers and roles.  
- Secret management using Vault / Key Vault only.  
- Monitoring of anomalies and real-time alerts.  
- Any policy change is recorded in `SECURITY_CHECKLIST.md`.

---

## Observability and logging

- Logs in unified structure (structured JSON).  
- Every action gets a shared trace ID across components.  
- Combination of human logs and agent logs.  
- Metrics: response times, recurring errors, load, security incidents.  
- The agent produces self-diagnosis reports at the end of each cycle (BY_CYCLE).

---

## DevOps and deployment (CI/CD)

- Versioning follows SemVer.  
- Build and tests run before merging into `main`.  
- Smoke tests run after each deployment.  
- Rollback is documented and executable.  
- Controlled rollout strategy (Canary / Blue-Green).  
- Every step is logged in `IMPLEMENTATION_LOG.md`.

---

## Quality and scalability principles

- System can scale horizontally (scale-out).  
- Failures handled via retries and DLQ.  
- Monitoring of bottlenecks.  
- Regular review of SLA / SLO / SLI compliance.  
- Every change is measured and reflected back into logs and reports.

---

## Internal documentation and automation

- Any new component requires an update to planning documents.  
- The agent validates consistency between Blueprint, PLAN and Spec.  
- Validation processes run automatically at the end of each cycle.  
- The human gives final approval in the `VALIDATION_REPORT.md`.

---

## Summary

This document serves as the system’s **engineering roadmap**.  
It bridges business logic and actual implementation,  
and clearly defines the agent’s role as an execution arm inside a documented system.

The Blueprint is the control baseline of Docs-as-System:  
every technical change must originate from it and be documented back into it.  
This preserves a real continuum between **Intent → Execution → Validation**.

---

© 2025 Tomer Kedem. Part of the official **Docs-as-System** template collection.
