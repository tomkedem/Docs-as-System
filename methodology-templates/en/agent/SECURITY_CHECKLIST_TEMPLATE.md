> ⚙️ **Template Notice:**  
> This file is an official Docs-as-System template.  
> Do not edit it directly inside the project. When initializing a new system, copy it into a folder named `docs/security/`  
> and save it as `SECURITY_CHECKLIST.md`, adapting it to the organization.

# Security Checklist

**File in the actual project:** `docs/security/SECURITY_CHECKLIST.md`  
**Template in the templates folder:** `templates/agent/SECURITY_CHECKLIST_TEMPLATE.md`  

**Related files:**  
- `docs/agent/AGENT_OPERATIONAL_POLICY.md`  
- `docs/logs/IMPLEMENTATION_LOG.md`  
- `docs/compliance/COMPLIANCE_POLICY.md`  

---

## Purpose of the Document

This document serves as the official template for security checks as part of the development process.  
It is part of the Validation layer of **Docs-as-System**, enabling the team to clearly document  
what is tested automatically by the agent, what requires human judgment, and what is performed by both.

The file is updated whenever code, configuration, or deployment processes change.  
Before any merge into a main environment, all relevant items must be marked as “Completed”.

---

## Quick Guide

| Type | Meaning | Performed By |
|------|---------|---------------|
| **AUTO** | Checked automatically by the agent | Agent |
| **HUMAN** | Requires human judgment and approval only | Human |
| **HYBRID** | Automatically checked but also requires human approval | Both |

---

## 1. Access and Permissions

| Type | Item | Status | Evidence / Notes |
|------|-------|---------|--------------------|
| AUTO | No secrets or passwords in code (automated scan) | | |
| AUTO | Authorization controls exist in the code | | |
| HYBRID | Only required users hold DB / services permissions | | |
| HUMAN | Admin permissions reviewed manually before deployment | | |

---

## 2. Sensitive Data

| Type | Item | Status | Evidence / Notes |
|------|-------|---------|--------------------|
| AUTO | No personal data written to logs | | |
| AUTO | Inter-service communication uses HTTPS / TLS | | |
| HYBRID | Configuration files do not contain sensitive data | | |
| HUMAN | Data retention policy reviewed manually | | |

---

## 3. Inputs and API

| Type | Item | Status | Evidence / Notes |
|------|-------|---------|--------------------|
| AUTO | All inputs undergo basic validation | | |
| AUTO | Secure SQL / ORM parameters are used | | |
| HYBRID | External endpoints are protected with proper authentication | | |
| HUMAN | API behavior manually reviewed for risky or unusual cases | | |

---

## 4. Dependencies

| Type | Item | Status | Evidence / Notes |
|------|-------|---------|--------------------|
| AUTO | Vulnerability scan on libraries | | |
| AUTO | Version lock file exists (`package-lock.json` / locked `.csproj`) | | |
| HYBRID | Documentation for new libraries updated | | |
| HUMAN | Library licenses reviewed manually | | |

---

## 5. Logs and Monitoring

| Type | Item | Status | Evidence / Notes |
|------|-------|---------|--------------------|
| AUTO | Logs do not contain personal or sensitive data | | |
| HYBRID | Critical events (access, exceptions, failures) are logged | | |
| HUMAN | Alert rules for detecting unusual activity defined | | |

---

## 6. Deployment and CI/CD

| Type | Item | Status | Evidence / Notes |
|------|-------|---------|--------------------|
| AUTO | Build files do not contain secrets | | |
| HYBRID | Deployment process runs with minimal required permissions | | |
| HUMAN | Production environment manually verified before deployment | | |

---

## 7. AI Agents and LLMs

| Type | Item | Status | Evidence / Notes |
|------|-------|---------|--------------------|
| AUTO | Agent does not send sensitive data to external models | | |
| HYBRID | Agent actions are logged in dedicated logs | | |
| HUMAN | Agent inputs and outputs manually reviewed | | |

---

## Exceptions

Every exception requires explicit human approval.

| Item | Exception Description | Risk | Approved By | Expiration Date | Notes |
|--------|--------------------------|---------|-------------------|-------------------|---------|

---

## Signatures

| Role | Name | Date | Notes |
|--------|---------|---------|----------|
| Agent | | | |
| Human Approver | | | |

---

## Final Note

This file should not be considered a regulatory document,  
but rather a working tool that helps the team maintain security, transparency,  
and shared documentation between human and agent within the Docs-as-System  
BY_CYCLE workflow.

---

>© 2025 Tomer Kedem. Part of the official **Docs-as-System** template suite.
