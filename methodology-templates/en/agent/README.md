# 📁 agent — Operational Policy and Human–Agent Coordination

This folder defines the rules, permissions, and controls of the AI agent operating within the project.  
It determines what the agent is allowed to do independently, what requires human approval, and how full traceability of every action is maintained.  
Each file in this folder covers a different aspect of the workflow, and together they form a complete documentation system that enables full control over the agent’s activity.

---

## Purpose of the Folder

- Create a clear and secure operational framework for the AI agent.  
- Define the interaction between the agent and the human (review, approval, documentation).  
- Maintain full transparency across planning, execution, and validation.  
- Ensure every agent action can be monitored, paused, and audited.  

---

## File Structure

| File | Description |
|------|-------------|
| **AGENT_CONFIG_TEMPLATE.yaml** | Configuration file defining paths, permissions, branches, commit policy, and logging rules. |
| **AGENT_OPERATIONAL_POLICY_TEMPLATE.md** | The official operational policy of the agent: allowed actions, approval requirements, and documentation rules. |
| **HUMAN_OPERATIONAL_POLICY_TEMPLATE.md** | Guide for the human supervising the agent: how to review outputs, when to stop a run, and how to approve changes. |
| **SECURITY_CHECKLIST_TEMPLATE.md** | Security checklist to be completed before and after each workflow cycle, including both automated and manual checks. |
| **VALIDATION_REPORT_TEMPLATE.md** | Validation report generated at the end of each BY_CYCLE workflow, summarizing performance, issues, and test results. |

---

## Recommended Workflow

1. **Agent environment setup:** Fill in `AGENT_CONFIG.yaml` according to the structure of the organization and project.  
2. **Activate operational policy:** Review `AGENT_OPERATIONAL_POLICY.md` to define what the agent performs independently and what requires approval.  
3. **Human oversight:** Use `HUMAN_OPERATIONAL_POLICY.md` for guidance on review and approval responsibilities.  
4. **Security checks:** Execute the items in `SECURITY_CHECKLIST.md` at every critical stage.  
5. **Validation report:** Generate `VALIDATION_REPORT.md` at the end of each workflow cycle and add it to the cycle log (`IMPLEMENTATION_LOG_SUMMARY_BY_CYCLE.md`).  

---

## Integration with Other Layers

- **planning/** — Provides business and technical requirements guiding the agent.  
- **architecture/** — Defines system structure and technical relationships.  
- **logs/** — Receives all agent and human records for auditing and tracking.  
- **automation/** — Executes testing and deployment processes according to the policies defined in this folder.

---

## Core Principle

> The agent executes → the human approves → the system documents.  
>
> This is the foundation of **Docs-as-System**:  
> A combination of smart automation and human accountability within a documentation-driven, real-time system.

---

>© 2025 Tomer Kedem. Part of the official **Docs-as-System** template suite.
