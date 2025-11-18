> ⚙️ **Template Notice:**  
> This file is an official template of Docs as System.  
> It must not be edited directly inside the methodology repository.  
> When initializing a new system it should be copied into `docs/project/`  
> and saved as `PROJECT_OVERVIEW.md` with updates that match the actual project.

# Project Overview Template

**Actual project file:** `docs/project/PROJECT_OVERVIEW.md`  
**Template file:** `templates/project/PROJECT_OVERVIEW_TEMPLATE.md`  
**Author:** Human (initial guidance for the agent)  
**Approver:** Product manager, architect or development manager  
**Document type:** Project definition file

---

## Opening note – universal usage

This document is part of the generic Docs as System template set  
and serves as a basic definition file for any software project  
regardless of technology, domain or system type including web, cloud, data, AI or embedded.

It is intended to act as the starting point of the documentation  
and to ensure that any human or AI agent understands the purpose, boundaries and values of the project.

> Core principle: every action in the project must come from clear and documented definition.

---

## Purpose of this document

To describe the project at a high level  
explaining what it is meant to achieve, why it exists, what its area of responsibility is  
and who the key stakeholders are in planning and oversight.

This document acts as a reference point for all other documents in the system  
for example business requirements, architecture blueprint and plan  
and keeps conceptual consistency throughout development and maintenance.

---

## Project metadata

| Field | Value |
|------|--------|
| Project name | (to fill) |
| Project identifier | (to fill) |
| Current version | (to fill, for example v1.0.0) |
| Start date | (to fill) |
| Initial target date | (to fill) |
| Project manager | (to fill) |
| Lead architect | (to fill) |
| Project type | (product, internal system, infrastructure, proof of concept, etc) |

---

## Executive summary

A concise description of the project purpose, its rationale  
and the value it provides to the organization, users or customers.

**Example:**  
> The system is designed to improve internal event flow management  
> using automation powered by AI agents with continuous documentation and real time monitoring.

---

## Scope and boundaries

A clear definition of what is included in the project scope and what is outside of it.

**In scope:**  
* (to fill)

**Out of scope:**  
* (to fill)

> The purpose of this section is to prevent confusion about responsibility and development boundaries.

---

## Objectives and goals

| Goal type | Description | Success metric |
|-----------|-------------|----------------|
| Business | (to fill) | (to fill) |
| Technological | (to fill) | (to fill) |
| Operational | (to fill) | (to fill) |

---

## Guiding principles

* Full transparency between human and agent  
* Documentation is an integral part of development  
* No automated action without a trace in the log  
* Every decision must be explained in an ADR  
* Every change must be reproducible  
* Every cycle begins and ends with documentation

---

## Stakeholders

| Role | Name | Main responsibility | Level of involvement |
|--------|--------|-------------------------|------------------------|
| Product manager | (to fill) | Business objectives definition | High |
| Architect | (to fill) | Technical planning and structural decisions | High |
| AI agent | (to fill) | Execution and continuous documentation | Scheduled |
| Developer | (to fill) | Implementation and code review | High |

---

## Integration with Docs as System layers

| Layer | Role description |
|-------|-------------------|
| **planning** | Defines the intent and purpose of the solution |
| **architecture** | Defines the way the system is built and the development patterns |
| **logs** | Documents every action in real time including cycles |
| **automation** | Produces reports, summaries and periodic validations |
| **agent** | Manages the agent, its policies and automated control |

---

## Operational scope

* Supported environments such as production, staging and local  
* Maintenance and support scope  
* Responsibility for updates and security  
* Coordination between development, DevOps and control teams  
* Integration with task management and CI CD tools  

---

## Management and version policy

* Every version is linked to a single work cycle identifier  
* The agent does not overwrite previous versions but creates a new folder under `docs/history`  
* Every change is documented in `IMPLEMENTATION_LOG.md`  
* Version tracking is maintained both in Git and in the documentation log  

---

## Human agent collaboration

The project operates under a controlled collaboration model:

| Stage | Main executor | Control |
|--------|----------------|----------|
| Writing code or documentation | Agent | Human review |
| Report generation | Agent | Human validation |
| Structure or configuration changes | Human | Agent checks consistency |
| Version release approval | Human | Agent documents and summarizes |

---

## Summary

`PROJECT_OVERVIEW.md` is the identity document of the project  
defining its purpose, boundaries, operational domain and policy.  
All other documents in the system rely on it as the source of truth  
and it acts as the foundation for alignment between human, agent and code.

---

© 2025 Tomer Kedem. Part of the official template collection of Docs as System.
