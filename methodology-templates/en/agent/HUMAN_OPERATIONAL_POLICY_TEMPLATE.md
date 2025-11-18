> ⚙️ **Template Notice:**  
> This file is an official Docs-as-System template.  
> Do not edit it directly inside the project. When initializing a new system, copy it into a folder named `docs/agent/`  
> and save it as `HUMAN_OPERATIONAL_POLICY.md`, adapting it to the organization.

# Human Operational Policy — Template

**File in the actual project:** `docs/agent/HUMAN_OPERATIONAL_POLICY.md`  
**Template in the templates folder:** `templates/agent/HUMAN_OPERATIONAL_POLICY_TEMPLATE.md`  

**Related files:**  
- `docs/agent/AGENT_OPERATIONAL_POLICY.md`  
- `docs/logs/IMPLEMENTATION_LOG.md`  
- `docs/security/SECURITY_CHECKLIST.md`  
- `docs/validation/VALIDATION_REPORT.md`  

**Purpose**  
Define how humans participate, review, and approve work in a project that operates alongside AI agents,  
according to the principles of **Docs-as-System**.

---

## Purpose of the Document

This template defines the human responsibilities within a project where an AI agent operates alongside humans.  
It describes how human control is maintained, how agent actions are approved,  
and how every step is documented so that all changes remain transparent, audited, and fully traceable.

---

## Core Principles

- Final responsibility for every decision and output belongs to humans only.  
- Every action or approval must be documented and clear.  
- The agent supports execution but does not replace human judgment.  
- Continuous synchronization between code, documents, and logs must be maintained.  
- Transparency, consistency, and mutual oversight are inherent to the process.

---

## Human Roles in the Project

| Role | General Responsibility | Example |
|--------|-------------------------|-------------|
| **Creator** | Defines project intent and direction. | Writes and approves `PROJECT_SPEC.md`. |
| **Reviewer / Approver** | Reviews outputs from agent or human and approves before merge. | Reviews `SECURITY_CHECKLIST.md` or `VALIDATION_REPORT.md`. |
| **Maintainer** | Maintains consistency of documents, versioning, and policies. | Updates `AGENT_OPERATIONAL_POLICY.md` or `HUMAN_OPERATIONAL_POLICY.md`. |
| **Auditor** | Verifies consistency between documentation, code, and logs. | Compares commits to `IMPLEMENTATION_LOG.md`. |

> Roles may be added or removed depending on team structure.

---

## Human Responsibility in the Workflow

Humans are responsible for:

- Reviewing and approving outputs created or modified by the agent.  
- Maintaining clear documentation for every change.  
- Providing human signatures on critical checkpoints (Validation Points).  
- Stopping the agent in cases of anomalies, uncertainty, or concern, and documenting the decision.  
- Maintaining security and data privacy procedures.  
- Keeping documents and logs synchronized within the BY_CYCLE workflow.

---

## Human–Agent Interaction

| Action | Human Responsibility | Documentation |
|--------|--------------------------|----------------|
| **Reviewing agent suggestion** | Approves or rejects before Keep / Apply. | Approved actions are logged automatically. |
| **Override** | Comments in the PR with a short explanation. | The agent copies the explanation into `IMPLEMENTATION_LOG.md`. |
| **Updating agent instructions** | Modifies prompts or policies and commits the change. | The commit itself serves as documentation; the agent adds a log entry. |
| **Problematic or risky suggestion** | Responds only through the PR. | The agent marks `Need human review` and updates the log. |

---

## Commits and Merge

- Only a human can approve merges into protected branches (`main`, `release/*`).  
- Every merge must include human review documentation within the PR.  
- Ensure `SECURITY_CHECKLIST.md` and `VALIDATION_REPORT.md` are up to date.  
- Each commit must include a clear intent behind the change.  
- When approving agent-generated work:  
  - Add the note `Approved by Human`  
  - Include approver’s name and date  
  - Add a link to the relevant log or report  

---

## Handling Unclear Situations (Escalation)

If uncertainty arises regarding an agent action or output:

1. The human temporarily pauses the agent’s activity.  
2. Logs the event in `docs/logs/IMPLEMENTATION_LOG.md`.  
3. Describes the issue and the reason for the pause.  
4. Assigns a human reviewer or auditor.  
5. Resumes activity only after documented approval.

---

## Final Approval

| Role | Name | Date | Notes |
|--------|---------|---------|----------|
| Project Owner | | | |
| Human Approver | | | |
| Auditor | | | |

---

This template may be adapted freely for any team or project.  
Its purpose is to preserve clear human responsibility, full transparency, and consistent documentation in any workflow where humans and agents operate together.

---

>© 2025 Tomer Kedem. Part of the official **Docs-as-System** template suite.
