> ⚙️ **Template note:**  
> This file is an official template of **Docs as System**.  
> It must not be edited directly inside the methodology repository.  
> When a new project is created the agent copies this file into the project root as `README.md`  
> and updates it with the project details, folder structure and actual instructions.

# 📘 Project README Template

This is the **official landing page of every project** based on **Docs as System**.  
Its purpose is to present in a clear, concise and consistent way  
the goal of the project, how it is structured and how to begin working with it.

The document is written so that anyone developer, tester, manager or external user  
can immediately understand the full picture of the project and its place within the methodology.

---

## 🎯 Project purpose

A short and clear explanation in one or two paragraphs  
describing why the project exists and what it is intended to achieve.

**Example:**  
> The system is designed to improve organizational data flow  
> using living documentation and an AI agent operating under human oversight.

---

## 🏗️ Repository structure

A general description of the project folders and their roles.

docs/
├── project/ ← identity, compliance and project policy
├── planning/ ← business requirements, logical design and work planning
├── architecture/ ← architecture blueprint and engineering decisions
├── agent/ ← operational policy and configuration for human and agent
├── logs/ ← logs and tracking by work cycle
└── automation/ ← scripts, reports and automated processes

src/ ← system source code
tests/ ← unit tests, integration tests and validation


---

## ⚙️ Run instructions

A short explanation of how to install and run the project according to the chosen technology.

**Example:**

```bash
# clone the repository
git clone https://github.com/organization/project-name.git
cd project-name

# run workspace setup
bash setup.sh

# run the system
dotnet run   # or npm start / python main.py depending on the project
```
⚠️ The commands above are only an example.  
They must be updated according to the actual project.

---

## 🔗 Links to key documents

| Area | File | Description |
|------|-------|-------------|
| **Project details** | `docs/project/PROJECT_OVERVIEW.md` | Identity, purpose and boundaries of the project. |
| **Compliance and control** | `docs/project/COMPLIANCE_AND_GOVERNANCE.md` | Policy for compliance, control and responsibility. |
| **Business requirements** | `docs/planning/BUSINESS_REQUIREMENTS.md` | Business goals, KPIs and required outcomes. |
| **Architecture blueprint** | `docs/architecture/ARCHITECTURE_BLUEPRINT.md` | System structure and development patterns. |
| **Agent policy** | `docs/agent/AGENT_OPERATIONAL_POLICY.md` | Rules and documentation guidelines for the agent. |
| **Execution log** | `docs/logs/IMPLEMENTATION_LOG.md` | Real time record of human and agent actions. |

---

## 🧩 Docs as System project lifecycle

Each project in this methodology follows a consistent and transparent structure of layers:

### **Intent (planning)**  
Definition of the business intent and goals.

### **Design (architecture)**  
System structure, diagrams and key decisions.

### **Execution (agent and logs)**  
Real time documented execution.

### **Validation (automation)**  
Automated checks and verification.

### **Governance (project)**  
Oversight, compliance and version control.

> Every change human or automated must be documented, reviewed and approved  
> before it reaches a protected branch.

---

## 🔄 Versioning and control

- Versioning follows Semantic Versioning.  
- Every version is linked to a work cycle identifier.  
- The agent performs local commits only.  
- A human reviewer approves merges into release branches.  
- Every change is recorded in `IMPLEMENTATION_LOG.md`.

---

## 🧠 Human and agent collaboration

The project follows the Human Agent Partnership principle:

- The agent performs actions according to the intent and planning documents.  
- The human reviews, approves and makes strategic decisions.  
- Every action is documented and monitored.  

This ensures transparency, traceability and trust between code, documentation and people.

---

## 🧭 Summary

This README file is the gateway into a living and documented project.  
It links the human, the agent and the system through clear intent,  
consistent documentation and execution that can be reviewed at every stage.

This file is created and updated automatically by the agent when the project is initialized.  
Any manual modification must be reviewed and approved according to the control policy.

---

© 2025 Tomer Kedem. Part of the official template collection of **Docs as System**.

