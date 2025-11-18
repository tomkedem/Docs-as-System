> ⚙️ **Template Notice:**  
> This file is an official template of Docs as System.  
> It must not be edited directly inside the project.  
> When initializing a new system it should be copied into `docs/planning/`  
> and saved as `PROJECT_SPEC.md` with updates that match the actual project.

# Logical Specification Template

**Actual project file:** `docs/planning/PROJECT_SPEC.md`  
**Template file:** `templates/planning/PROJECT_SPEC_TEMPLATE.md`  
**Author:** AI agent with human guidance  
**Approver:** Human product manager, architect or tech lead  
**Specification type:** Logical specification

---

## Purpose of the document

This document translates the business requirements into the “what” of the system.  
It describes the logical behavior of the system from the perspective of users and external systems.  
It does not contain technical decisions. It only defines processes, scenarios, flows and inputs or outputs.  
It is the bridge between the business need and the technical architecture.

---

## General summary

A short and clear description of the proposed solution  
what the system does, who it is designed for  
and how it addresses the business requirements defined in `BUSINESS_REQUIREMENTS.md`.

*(To be filled by a human or by the agent with human guidance.)*

---

## Actors

Every entity that interacts with the system such as a human user, external system, AI agent or another API.

| Actor name | Type | Role description | Interaction with the system |
|------------|-------|---------------------|-------------------------------|
| (to fill) | (human, system or AI agent) | (to fill) | (input, output or both) |

---

## Main use cases

Description of the main processes the system performs as experienced by users or external systems.

**Recommended structure for each use case:**

* **Name:** (to fill)  
* **Actors:** (to fill)  
* **Goal:** what the actor is trying to achieve  
* **Basic flow:**  
  1. (first step)  
  2. (second step)  
  3. (expected outcome)  
* **Exception scenarios:** what happens in case of failure  
* **Success conditions:** when the use case is considered complete

---

## Logical data flow

Description of the general flow of information between system components.  
A diagram or textual description may be included.

**Recommended structure:**  
Data source → input point → logical processing → data target → result or alert

**Example:**  
Client sends request → Web API receives → validation → database save → confirmation sent

---

## Logical data schema

Description of the main entities, their attributes and their relationships  
without technical implementation details such as SQL or exact field names.

| Entity | Description | Main fields | Relationships |
|--------|--------------|----------------|-------------------|
| (to fill) | (to fill) | (to fill) | (to fill) |

---

## Events and conditions

Description of the main system events and the behavior that follows each one.

| Event | Trigger source | Logical response | Expected result |
|--------|-------------------|---------------------|---------------------|
| (to fill) | (to fill) | (to fill) | (to fill) |

---

## Business rules

The set of rules that define the internal behavior of the system.

| Rule identifier | Rule description | Activation conditions | Notes |
|-------------------|----------------------|--------------------------|--------|
| BR 001 | (to fill) | (to fill) | (to fill) |
| BR 002 | (to fill) | (to fill) | (to fill) |

---

## Edge cases and exceptions

Unusual or unexpected scenarios that may break the normal flow.

* (Example: message arrives twice or timeout from external system)  
* (Describe how the system behaves in each case)

---

## Non functional requirements

General requirements that define how the system behaves rather than what it does.

| Category | Requirement description | Success metric |
|-----------|-----------------------------|-------------------|
| Performance | (example response time less or equal to two seconds) | (metric) |
| Security | (authentication, encryption, permissions) | (metric) |
| Accessibility | (language support, accessible interface) | (metric) |
| Compliance | (regulation, external interfaces) | (metric) |

---

## Interfaces and external systems

Details about the interfaces between the system and external services.

| System or service | Interface type | Communication direction | Frequency or trigger |
|----------------------|------------------|-----------------------------|--------------------------|
| (to fill) | (API, queue, webhook, etc) | (inbound or outbound) | (to fill) |

---

## Assumptions and constraints

**Assumptions:**  
* (to fill)

**Constraints:**  
* (example: no real time integration with system X)

---

## Validation criteria

Conditions that must be met to approve that the system matches its logical definition.

| Area | Success metric | Measurement method |
|--------|-------------------|-------------------------|
| User experience | (to fill) | (to fill) |
| Data processing | (to fill) | (to fill) |
| Data consistency | (to fill) | (to fill) |

---

## Human agent logic

If the system includes an AI agent component the autonomy boundaries must be defined:

* When the agent is activated and what triggers its activation  
* Its level of autonomy such as suggestion, execution or analysis only  
* How it passes data to a human or another system  
* Which actions require explicit human approval  

**Example:**  
When an exception event is received from a DLQ the agent generates a correction proposal report  
but does not perform code changes on its own.

---

## Summary

This document describes the **what** of the system before deciding **how** to build it.  
It represents the transition step between the business definition (BRD) and the architecture blueprint.  
Its purpose is to ensure that the logical behavior is understood, documented and implementable in any technology.

---

## Expected output

A clear and detailed document that explains the logical behavior of the system  
including flows, processes, rules and responses to every scenario  
so every developer, tester or agent knows what to build before writing code.

---

## Final principle

Every document in the project is part of a single living documentation system  
from business intent through logical specification  
through technical structure and up to planning, implementation and validation.

The agent executes and documents.  
The human defines and approves.  
And the system is built and maintained from **one living documentation source** based on Git.

---

© 2025 Tomer Kedem. Part of the official template collection of Docs as System.
