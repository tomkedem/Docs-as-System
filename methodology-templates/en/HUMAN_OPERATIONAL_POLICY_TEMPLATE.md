# HUMAN_OPERATIONAL_POLICY_TEMPLATE.en.md

**Document type:** Human Operational Policy Template  
**Purpose:** Define the scope, responsibilities, and operational conduct of human participants in projects that include AI Agents, according to the principles of **Docs-as-System**.  
**Related files:** `AGENT_OPERATIONAL_POLICY.md`, `HUMAN_OPERATIONAL_POLICY.md`, `IMPLEMENTATION_LOG.md`  

---

## 1. Purpose of this Template

This template provides a standard structure for defining human operational policy within any documented project.  
It describes how humans interact with automated agents, maintain accountability, and ensure full traceability of decisions.

It is fully adaptable to any organization, team, or technology stack.

---

## 2. Core Principles

- Final accountability for decisions, outputs, and releases always remains **human**.  
- Every human action or approval must be **documented and explainable**.  
- The Agent may act independently, but never replaces human judgment.  
- Code, documents, and logs must remain synchronized at all times.  
- Transparency and traceability are fundamental requirements.

---

## 3. Possible Roles

| Role | General Responsibility | Example |
|------|------------------------|----------|
| **Creator** | Defines the project intent and boundaries. | Writes and approves `PROJECT_SPEC.md`. |
| **Reviewer / Approver** | Reviews outputs of both humans and agents before merge. | Checks `VALIDATION_REPORT.md` or `SECURITY_CHECKLIST.md`. |
| **Maintainer** | Ensures long-term consistency of documentation and compliance. | Updates `COMPLIANCE_POLICY.md`. |
| **Auditor** | Verifies traceability between intent, code, and documentation. | Compares commits with `IMPLEMENTATION_LOG.md`. |

> The list may be expanded or simplified according to team structure.

---

## 4. Human Responsibilities in the Process

Humans are responsible for:
- Reviewing and approving any file generated or modified by an Agent.  
- Maintaining accurate and up-to-date documentation for every change.  
- Providing human sign-offs at key validation points.  
- Initiating, pausing, or resuming agent activity when needed, with proper documentation.  
- Ensuring compliance with organizational and data security policies.

---

## 5. Interaction with AI Agents

| Action Type | Human Responsibility | Notes |
|--------------|----------------------|--------|
| **Output Review** | Verify correctness, clarity, and compliance of the Agent’s output. | May edit directly in the same branch. |
| **Override** | Use only when correction or redirection is required. | Must include reasoning in `IMPLEMENTATION_LOG.md`. |
| **Training / Adjustment** | Update prompts or policies to refine Agent behavior. | All modifications must be logged. |
| **Pause Agent** | Suspend during sensitive or uncertain operations. | Document reason and resume upon approval. |

---

## 6. Commits and Merge Policy

- Only human participants may **approve or merge** to protected branches.  
- Every merge must include explicit confirmation of human validation.  
- Ensure that all relevant validation documents (e.g., `SECURITY_CHECKLIST.md`, `TEST_COVERAGE.md`) are up to date.  
- Each commit should include a message describing the **intent** behind the change, not just the technical action.  
- When approving Agent-generated work, include:  
  - A comment such as “Approved by Human”  
  - Date and identity of approver  
  - Reference to the reviewed log or validation report  

---

## 7. Uncertainty and Escalation Protocol

When uncertainty arises regarding agent behavior or output:
1. **Pause the agent** on the active branch.  
2. Record the issue in `IMPLEMENTATION_LOG.md` under the “Escalation” section.  
3. Briefly describe the concern and context.  
4. Assign a human reviewer for analysis.  
5. Resume automation only after review and documented approval.

---

## 8. Compliance and Traceability

- All human approvals must be auditable through commits and logs.  
- Each decision must be linked to a documented intent or validation checkpoint.  
- Any deviation from this policy requires justification and documentation in the project repository.

---

## 9. Sign-off

| Role | Name | Date | Notes |
|------|------|------|-------|
| Project Owner |  |  |  |
| Human Approver |  |  |  |
| Auditor |  |  |  |

---

**Note:**  
This template can be adapted or shortened to match the team’s size and workflow.  
It is not a regulatory document but a practical governance tool to ensure clear, safe, and documented collaboration between humans and agents.

---

© 2025 Tomer Kedem. Part of the official **Docs-as-System** template collection.
