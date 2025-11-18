# ⚙️ automation — Controls, Validation and Workflows

This folder contains all **automation components** used in a Docs-as-System–based project.  
It is responsible for running guardrails, executing validation pipelines, generating cycle summaries,  
and orchestrating scheduled or manually triggered workflows.

---

## 🎯 Purpose of this folder

- Manage all automated processes in the project (controls, validation, summaries).  
- Ensure every agent action is executed under Guardrails and fully logged.  
- Coordinate agent–human workflows at the end of each cycle (`BY_CYCLE`).  
- Maintain consistency, security and full traceability across the entire system.

---

## 🧩 Folder structure

| File | Description |
|------|-------------|
| **GUARDRAILS_TEMPLATE.md** | Defines real-time safety rules, boundaries and operational limits for the agent. |
| **VALIDATION_PIPELINE_TEMPLATE.md** | Describes the automated validation sequence that powers the Validation Layer. |
| **WORKFLOWS_GUIDE_TEMPLATE.md** | Explains how validations and controls combine into automated work cycles. |
| **README.md** | This file — explains the purpose of the automation folder and how it connects to other layers. |

---

## 🔄 Position within the Docs-as-System structure

| Layer | Role |
|-------|-------|
| **agent/** | Executes actions under Guardrails and logging requirements. |
| **logs/** | Receives real-time results and aggregates them by cycle. |
| **automation/** | Runs all automated validations and cycle summaries. |
| **project/** | Defines the governance and compliance framework. |
| **architecture/** | Provides the system blueprint used for validation. |

---

## 🧠 How this layer operates

1. The agent performs actions according to the defined policies.  
2. **Guardrails** monitor every step in real time.  
3. At the end of each cycle, the **Validation Pipeline** verifies consistency and compliance.  
4. **Workflows** orchestrate everything into a scheduled process: Guardrails → Validation → Summary.  
5. Every stage is logged in `IMPLEMENTATION_LOG.md` with an appropriate tag.

---

## ⚙️ Configuration file

> The configuration file `automation/workflows.yaml` is generated automatically  
> and updated according to project policy and human approval.  
> It defines the scheduling for Guardrails, Validation and Summary processes.

---

## 🧭 Summary

The `automation/` folder is **the operational engine of Docs-as-System**.  
It ensures order, quality and consistency in every development cycle  
and guarantees that every action — human or automated —  
is executed with monitoring, logging and real-time oversight.

© 2025 Tomer Kedem. Part of the official **Docs-as-System** template collection.
