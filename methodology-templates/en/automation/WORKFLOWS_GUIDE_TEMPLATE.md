> ⚙️ **Template Notice:**  
> This file is an official **Docs-as-System** template.  
> Do not edit it directly inside the methodology repository.  
> When creating a new system, copy it into `docs/automation/`  
> under the name `WORKFLOWS_GUIDE.md` and adapt it to the actual project workflows.

# 🔄 Workflows Guide Template

**In-project document:** `docs/automation/WORKFLOWS_GUIDE.md`  
**Template location:** `templates/automation/WORKFLOWS_GUIDE_TEMPLATE.md`  
**Created by:** Human (guided by the agent)  
**Approved by:** Development Manager / Architect / DevOps Lead  
**Purpose:** Define the automated workflows that bring the methodology to life.

---

## 🎯 Purpose of the document

To describe how automated development processes operate in the project  
when the agent acts, which processes run in each work cycle (`BY_CYCLE`)  
and how the system performs guardrails, validations, reports and summaries  
in a scheduled, consistent and fully reproducible way.

> The document is designed for both humans and agents:  
> it defines *what happens when* across the entire work cycle.

---

## ⚙️ Core workflow components

| Component | Description | Triggered by | Frequency |
|-------------|-------------|---------------|--------------|
| **Guardrails Check** | Real time enforcement of safety constraints on agent actions | Agent | On every action |
| **Validation Pipeline** | Automated consistency, log and security checks | Agent | End of each cycle |
| **Log Summary Generator** | Creates the cycle summary (`IMPLEMENTATION_LOG_SUMMARY_BY_CYCLE.md`) | Agent | End of cycle |
| **Human Review Request** | Sends an exception report for human review | Agent | Automatic on exception |
| **Compliance Sync** | Syncs compliance policies with updated documents | Human | Weekly |
| **Documentation Update** | Refreshes README and Blueprint pages | Agent | Daily or as needed |

---

## 🧩 General workflow diagram

Start Cycle  
↓  
Guardrails Enforcement  
↓  
Agent Actions → Logging  
↓  
Validation Pipeline  
↓  
Human Review (if needed)  
↓  
Cycle Summary Generation  
↓  
End Cycle

> Each step is documented in the implementation log (`IMPLEMENTATION_LOG.md`)  
> with an appropriate action tag (`GUARDRAILS_CHECK`, `VALIDATION_RUN`, `SUMMARY_CREATED`, etc.).

---

## 🧮 Agent instructions — workflow management

1. At every cycle start, generate a new identifier (`CycleId`).  
2. Add the matching `CycleId` field to every documented action.  
3. At the end of each cycle:  
   - Run **Guardrails**  
   - Execute the **Validation Pipeline**  
   - Generate the cycle summary (`IMPLEMENTATION_LOG_SUMMARY_BY_CYCLE.md`)  
   - Update the main log with the `CYCLE_COMPLETED` tag  
4. In case of any exception — stop the sequence, document the exception and send for human approval.

---

## 🔁 Possible workflow types

| Workflow type | Purpose | Initiator | Required documentation |
|------------------|------------|-------------|------------------------------|
| **Manual Workflow** | Triggered manually by a human (checks or special cycles) | Human | Action entry required |
| **Scheduled Workflow** | Recurring execution (daily or weekly) based on configuration | Agent | Automated report (`SCHEDULE_RUN`) |
| **Event-Driven Workflow** | Triggered by system events (commit, merge, etc.) | Agent | Log trigger entry (`EVENT_TRIGGERED`) |
| **Recovery Workflow** | Automatic rollback after failure | Agent | Mandatory entry with `ROLLBACK_EXECUTED` |

---

## 🧠 Managing workflow dependencies

- Each workflow depends on the outputs of the previous one (Guardrails → Validation → Summary).  
- No partial workflow should run unless explicitly allowed in `AGENT_CONFIG.yaml`.  
- Logs must be locked before running a new Validation.  
- The agent performs a Self-Check before every run to prevent duplicate execution.

---

## 🔔 Example workflow scheduler

```yaml
workflows:
  daily_validation:
    trigger: "0 6 * * *"  
    tasks:
      - run_guardrails
      - run_validation_pipeline
      - generate_summary

  weekly_compliance_sync:
    trigger: "0 7 * * 0"
    tasks:
      - compliance_check
      - documentation_update
```
The configuration file (`automation/workflows.yaml`) is generated automatically  
and updated based on project policy and human approval.

## 📄 Related documents

| Document | Purpose in context |
|----------|--------------------------|
| **GUARDRAILS.md** | Defines real-time operational boundaries and safety rules |
| **VALIDATION_PIPELINE.md** | Defines validation stages at the end of each cycle |
| **IMPLEMENTATION_LOG.md** | Central log containing all workflow records |
| **COMPLIANCE_AND_GOVERNANCE.md** | Provides the governance and approval framework |

---

## 🧭 Summary

`WORKFLOWS_GUIDE.md` is the process map of Docs-as-System.  
It connects humans, agents and documentation into a synchronized, controlled flow.  
Thanks to this guide, it becomes clear what happened, when and why during every cycle.

Every workflow is a documented expression of human intent —  
and the agent is the one who executes it precisely and transparently.

© 2025 Tomer Kedem. Part of the official Docs-as-System template collection.
