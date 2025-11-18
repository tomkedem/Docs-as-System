> ⚙️ **Template Notice:**  
> This file is an official **Docs-as-System** template.  
> Do not edit it directly inside the main repository.  
> When creating a new project, the agent copies it into `docs/automation/`  
> under the name `GUARDRAILS.md` and adapts it to the specific policy of that project.

# 🧩 Guardrails Template — Operational Boundaries for the Agent

**In-project file:** `docs/automation/GUARDRAILS.md`  
**Template location:** `templates/automation/GUARDRAILS_TEMPLATE.md`  
**Created by:** Agent (guided by a human)  
**Approved by:** Architect / Security Lead / Tech Lead  
**Purpose:** Define the boundaries and controls within which the agent is allowed to operate.

---

## 🎯 Purpose of the Document

Ensure that every AI agent action in a Docs-as-System project  
is executed under safe, traceable and fully restorable conditions.

This document defines the **Guardrails** —  
the rules, boundaries and safety controls that prevent the agent  
from acting outside its responsibility scope or harming system integrity, code, or data.

---

## 🧠 Core Operating Principles

1. **Complete Transparency:** Every agent action is recorded in `IMPLEMENTATION_LOG.md`.  
2. **No Auto-Merge:** The agent never merges changes into a protected branch.  
3. **Human Gate:** Any significant change requires explicit human approval.  
4. **Self-Validation:** Before executing any action, the agent verifies that it complies with its internal rules.  
5. **Context-Limited:** The agent operates only within the directories and file paths allowed in `AGENT_CONFIG.yaml`.  
6. **Immutable History:** No deletion or alteration of historical documentation.  
7. **Reversible Actions:** Every change must be fully reversible (Rollback-capable).

---

## 🧩 Control Structure

| Control Type | Description | Triggered By | Log Tag |
|--------------|-------------|--------------|---------|
| **Validation Guard** | Ensures consistency between documentation and code | Agent | `SELF_CHECK` |
| **Security Guard** | Detects keys, tokens or sensitive information | Agent + Human | `SECURITY_ALERT` |
| **Scope Guard** | Blocks access outside approved directories | Agent | `ACCESS_DENIED` |
| **Schema Guard** | Validates Markdown/YAML structural integrity | Agent | `DOC_VALIDATION` |
| **Log Guard** | Ensures every action is logged | Agent | `LOG_CHECK` |
| **Approval Guard** | Pauses execution until human approval | Human | `HUMAN_REQUIRED` |

---

## 🧾 Valid Workflow (Flow)

1. **The agent receives a task** from one of the planning documents (`PLAN`, `SPEC`, `ADR`).  
2. **Pre-Check:** The agent verifies the action is allowed and documented.  
3. **Action:** The agent performs only approved operations and logs them.  
4. **Post-Check:** The system verifies consistency, compliance and security.  
5. **Learning:** The agent records outcomes, including exceptions.  
6. **Human Approval:** Required for all “sensitive” category actions.

---

## ⚙️ Exception Handling

| Exception Type | Symbol | Description | Requires Human Approval |
|----------------|--------|-------------|--------------------------|
| **CODE_MOD_OUTSIDE_SCOPE** | 🚫 | Attempt to modify files outside allowed scope | ✅ |
| **SECURITY_VIOLATION** | 🛑 | Sensitive data detected (Token / Password / Key) | ✅ |
| **MISSING_LOG_ENTRY** | ⚠️ | Action executed without a matching log entry | ✅ |
| **CONFIG_CONFLICT** | ⚙️ | Conflict between configuration files | ✅ |
| **VALIDATION_FAILED** | ❗ | Invalid document structure or missing data | ❌ (Auto Fix) |

> Every exception is automatically logged in `IMPLEMENTATION_LOG.md`  
> under tag `EXCEPTION`, and reviewed at the end of each work cycle (`BY_CYCLE`).

---

## 🔁 Integration with BY_CYCLE

- Each work cycle triggers a full Guardrails run.  
- The cycle generates: `GUARDRAILS_REPORT_BY_CYCLE.md`.  
- The agent performs a self-diagnosis and flags issues requiring human review.  
- Only after human approval, the final cycle summary  
  (`IMPLEMENTATION_LOG_SUMMARY_BY_CYCLE.md`) is created.

---

## 🧩 Monitoring and Oversight Principles

- Every guardrail is executed automatically at the start of any agent action.  
- Any change to Guardrails configuration requires a dedicated commit and full documentation.  
- The agent must not disable any active control without managerial approval.  
- Guardrails may be extended using custom scripts inside `automation/scripts/`.

---

## 📄 Related Documents

| Document | Purpose |
|----------|----------|
| `AGENT_OPERATIONAL_POLICY.md` | Defines actual agent behavior and permissions. |
| `HUMAN_OPERATIONAL_POLICY.md` | Describes human oversight responsibilities. |
| `COMPLIANCE_AND_GOVERNANCE.md` | Provides the legal and organizational framework. |
| `IMPLEMENTATION_LOG.md` | Records all actions and exceptions in real time. |
| `VALIDATION_REPORT.md` | Summarizes automated validation results. |

---

## 🧭 Summary

`GUARDRAILS.md` is **the system’s first line of defense**.  
It ensures that every action — by agent or human —  
is executed within clear boundaries, fully documented,  
and completely transparent for audit at any time.

> The agent does not replace human oversight —  
> it simply enforces it at machine speed.

---

© 2025 Tomer Kedem. Part of the official **Docs-as-System** template set.
