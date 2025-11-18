> ⚙️ **Template Notice:**  
> This file is an official **Docs-as-System** template.  
> Do not edit it directly inside the main repository.  
> When creating a new project, the agent copies it into `docs/automation/`  
> under the name `VALIDATION_PIPELINE.md` and updates it with the checks and stages relevant to the actual project.

# 🧪 Validation Pipeline Template

**In-project file:** `docs/automation/VALIDATION_PIPELINE.md`  
**Template location:** `templates/automation/VALIDATION_PIPELINE_TEMPLATE.md`  
**Created by:** Agent (under human guidance)  
**Approved by:** Human (Architect / Quality Lead / Tech Lead)  
**Purpose:** Define the automatic validation sequence that ensures the correctness of the system, documentation and logs for the current work cycle (BY_CYCLE).

---

## 🎯 Purpose of this Document

Describe the pipeline that ensures all system layers — code, documentation and logs —  
are fully consistent with each other.  
This is the **Validation Layer** of Docs-as-System,  
ensuring the agent, the code and the documents are aligned and approved before closing a cycle.

---

## 🧩 Core Principles

1. **Automatic cycle-end validation:**  
   Every work cycle (`BY_CYCLE`) ends with a full execution of the Validation Pipeline.  

2. **Transparency:**  
   Every result is recorded in `VALIDATION_REPORT.md` and preserved in the log.  

3. **Self-Check:**  
   The agent performs preliminary checks on itself to detect inconsistencies.  

4. **No deletion:**  
   Previous reports are never rewritten or removed — only new entries are added.  

5. **Human approval:**  
   A cycle is closed only after a human review and approval.

---

## 🧱 Pipeline Stages

| Step | Check Name | Purpose | Check Type | Executed By |
|------|-------------|----------|-------------|----------------|
| 1 | **Schema Validation** | Validate Markdown/YAML structure | Static | Agent |
| 2 | **Log Consistency** | Ensure all actions appear in the log and link to the cycle | Logical | Agent |
| 3 | **Agent Self-Verification** | Compare performed actions with log entries | Behavioral | Agent |
| 4 | **Security Review** | Detect tokens, passwords and access keys | Static | Agent |
| 5 | **Documentation Diff Check** | Validate file changes against official documentation | Semantic | Agent |
| 6 | **Human Review Required** | Send summary of exceptions to a human reviewer | Manual | Human |

---

## ⚙️ Example Pipeline Flow

[Schema Validation] → [Log Consistency] → [Self-Verification]  
↓  
[Security Review] → [Documentation Diff] → [Human Approval]

> The agent executes all automatic stages only.  
> The human approval stage is completed only after a human signs `VALIDATION_REPORT.md`.

---

## 🧾 Example Pipeline Output (Auto-Generated)

```yaml
CycleId: CY-2025-Q4-A
StartedAt: 2025-11-10T08:30Z
FinishedAt: 2025-11-10T08:34Z
TriggeredBy: Agent-A01
ValidatedFiles:
  - docs/project/PROJECT_OVERVIEW.md
  - docs/architecture/ARCHITECTURE_BLUEPRINT.md
  - docs/logs/IMPLEMENTATION_LOG.md
Results:
  SchemaValidation: Passed
  LogConsistency: Passed
  SecurityReview: Passed
  SelfVerification: Passed
  HumanReview: Pending
Summary: |
  All automated checks passed successfully. Awaiting human approval.
```
---
## 🧮 Agent Instruction — Saving Output File

After each Pipeline run,  
the agent must save the validation results as a standalone **YAML** file  
with a deterministic name based on the current cycle.

**Saving location:**  
`docs/automation/results/VALIDATION_RESULT_<CycleId>.yaml`

**Full example:**  
`docs/automation/results/VALIDATION_RESULT_CY-2025-Q4-A.yaml`

---

## 🧩 Rules

- If the folder `docs/automation/results/` does not exist — create it.  
- The file must always be saved in readable **YAML** format with the exact output fields.  
- Results from previous cycles must never be overwritten — every cycle has its own file.  
- The file is added automatically to the next commit with tag `VALIDATION_RESULT`.  
- At the same time, the agent adds a log entry (`PIPELINE_EXECUTION`) into `IMPLEMENTATION_LOG.md`.

> This ensures each cycle receives a fully independent, fully restorable  
> validation record.

---

## 🔍 Handling Failures

| Failure Type | Log Tag | Required Action | Risk Level |
|--------------|---------|------------------|------------|
| Missing critical file | `MISSING_DOC` | Agent recreates the missing document | Medium |
| Log/document mismatch | `LOG_MISMATCH` | Automatic analysis + human review | High |
| Invalid YAML structure | `SCHEMA_ERROR` | Agent fixes the formatting | Low |
| Security violation | `SECURITY_FLAG` | Immediate halt + CISO approval | Critical |

Any additional failure is recorded in `IMPLEMENTATION_LOG.md`  
under `VALIDATION_EXCEPTION`.

---

## 🔁 Integration with Guardrails

- The Validation Pipeline runs **after** all Guardrails mechanisms.  
- Guardrails enforce real-time rules; the Pipeline validates at cycle-end.  
- This combination ensures all actions are documented, safe and human-approved.  
- Pipeline results become the basis for the periodic `VALIDATION_REPORT.md`.

---

## 🧭 Summary

`VALIDATION_PIPELINE.md` is where documentation, code and humans meet.  
It ensures every system change is documented, tested and approved before release.  
This pipeline is the engine that keeps the methodology consistent, trustworthy  
and fully traceable — without sacrificing speed or efficiency  
when working with AI agents.

>© 2025 Tomer Kedem. Part of the official **Docs-as-System** template set.
