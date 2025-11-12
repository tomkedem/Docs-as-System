# SECURITY_CHECKLIST_TEMPLATE.en.md

This document serves as an official template for security validation as part of the development lifecycle.  
It belongs to the **Validation** layer of Docs-as-System and clearly defines what is verified by the agent, what requires human approval, and what is checked jointly.

**Related files:**  
`COMPLIANCE_POLICY.md` | `AGENT_OPERATIONAL_POLICY.md` | `IMPLEMENTATION_LOG.md`

---

## Quick Guide

| Type | Meaning | Performed by |
|------|----------|--------------|
| AUTO | Automatically verified by the Agent | Agent |
| HUMAN | Requires human review and approval only | Human |
| HYBRID | Verified by the Agent and approved by a Human | Both |

This checklist must be updated whenever code, configuration, or deployment processes change.  
Before every merge to the main branch, all relevant items must be marked as *completed*.

---

## 1. Access and Permissions

| Type | Item | Status | Evidence / Notes |
|------|-------|---------|------------------|
| AUTO | No secrets or passwords are found in code (scanned by Agent) | | |
| AUTO | Access control mechanisms exist in code (Authorization) | | |
| HYBRID | Only required users have access to DB or services | | |
| HUMAN | Manual review of admin privileges before deployment | | |

---

## 2. Sensitive Data

| Type | Item | Status | Evidence / Notes |
|------|-------|---------|------------------|
| AUTO | Personal data is not written to logs | | |
| AUTO | All communication between services is encrypted (HTTPS / TLS) | | |
| HYBRID | Configuration files contain no sensitive values | | |
| HUMAN | Manual review of data retention and privacy policy | | |

---

## 3. Inputs and APIs

| Type | Item | Status | Evidence / Notes |
|------|-------|---------|------------------|
| AUTO | All external inputs are validated and sanitized | | |
| AUTO | Secure parameterized SQL or ORM queries are used | | |
| HYBRID | Public endpoints are properly authenticated | | |
| HUMAN | Manual review of risky or unexpected API behavior | | |

---

## 4. Dependencies

| Type | Item | Status | Evidence / Notes |
|------|-------|---------|------------------|
| AUTO | Libraries are scanned for vulnerabilities | | |
| AUTO | Lock file or pinned versions exist (`package-lock.json` / locked `csproj`) | | |
| HYBRID | Documentation for new dependencies is updated | | |
| HUMAN | License compliance verified manually | | |

---

## 5. Logging and Monitoring

| Type | Item | Status | Evidence / Notes |
|------|-------|---------|------------------|
| AUTO | Logs do not contain personal or sensitive information | | |
| HYBRID | Critical events (access, exceptions, failures) are logged | | |
| HUMAN | Security alerts or anomaly detection rules are configured | | |

---

## 6. Deployment and CI

| Type | Item | Status | Evidence / Notes |
|------|-------|---------|------------------|
| AUTO | Build configuration contains no secrets | | |
| HYBRID | Deployment pipeline runs with minimal permissions | | |
| HUMAN | Production environment manually verified before release | | |

---

## 7. AI Agents and LLMs

| Type | Item | Status | Evidence / Notes |
|------|-------|---------|------------------|
| AUTO | The agent does not send sensitive data to external models | | |
| HYBRID | Agent actions are logged and traceable | | |
| HUMAN | Manual review of agent prompts and outputs | | |

---

## Exceptions

All exceptions require explicit human approval.

| Item | Description | Risk | Approved by | Valid until | Notes |
|------|--------------|------|--------------|--------------|--------|

---

## Signatures

| Role | Name | Date | Notes |
|------|------|------|-------|
| Agent |  |  |  |
| Human approver |  |  |  |

---

**Final Note:**  
This checklist is not a regulatory or compliance document.  
It is a living validation record that enables teams to build securely, transparently, and collaboratively between humans and agents.

---

© 2025 Tomer Kedem. Part of the official **Docs-as-System** template collection.
