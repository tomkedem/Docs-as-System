# 📁 planning — project planning and intent definition

This folder contains all the **planning documents** of the project  
from the business need through the logical definition and up to the practical execution plan.  
This is the layer where the project moves from an idea into a structured and actionable documentation framework.

---

## Purpose of the folder

* Define the **intent** behind the development  
* Document the transition from business requirements into engineering planning  
* Provide a clear and logical sequence of documents that guide every execution phase  
* Enable the agent to understand the purpose of the system, its boundaries and the dependencies between stages  

---

## File structure of the folder

| File | Description |
|-------|--------------|
| **BUSINESS_REQUIREMENTS_TEMPLATE.he.md** | Defines the business requirements and the need the system solves |
| **PROJECT_SPEC_TEMPLATE.md** | Describes the logical behavior of the system what it does and how it behaves |
| **PLAN_TEMPLATE.md** | Describes the execution plan, stage breakdown, dependencies and metrics |
| **README.md** | This document explaining the purpose of the folder and the relationships between the files |

---

## Workflow sequence

1. **Business Requirements** the reason the project exists  
2. **Project Spec** the exact definition of what the system should do  
3. **Plan** how to execute it, who is responsible and how success is measured  

> This is a fixed sequence in the Docs as System method  
> each step creates clarity for the next one and everything is kept in Git to ensure complete traceability.

---

## Integration with other layers

| Layer | Role of the connection |
|--------|--------------------------|
| **agent** | The agent reads these documents to understand what to build |
| **architecture** | Built directly on top of these planning documents |
| **logs** | Every executed action is documented and linked back to the planning documents |
| **automation** | Runs scripts and reports that verify alignment between planning and execution |

---

## Core principle

> “No action without intent and no code without a document that explains why it was written.”

This layer is the **Intent Layer** of Docs as System  
it sets the direction, the purpose and the context for every action that follows.

---

© 2025 Tomer Kedem. Part of the official template collection of **Docs as System**.
