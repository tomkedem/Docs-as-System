> ⚙️ **Template Notice:**  
> This file is an official Docs as System template.  
> It must not be edited directly inside the project.  
> When initializing a new system, copy it into `docs/planning/`  
> and save it as `BUSINESS_REQUIREMENTS.md`, then adapt it to the project.

# Business Requirements Document (BRD) Template

**Actual project document:** `docs/planning/BUSINESS_REQUIREMENTS.md`  
**Template location:** `templates/planning/BUSINESS_REQUIREMENTS_TEMPLATE.md`  
**Created by:** Human (with linguistic support from the AI agent)  
**Approved by:** Business stakeholder, product manager or management  
**Document type:** Business requirements

---

## Purpose of the document

To describe the business need, the rationale behind it, the boundaries of the solution and the success criteria.  
This is the stage where we clarify why the system is being built, for whom and what will be considered a successful outcome.

---

## Executive Summary

A short and clear description of the project’s purpose, the need it addresses and the expected value for the organization or users.  
It should be written in non technical business language so that every stakeholder understands why the project matters.

**Example:**  
> “The system aims to improve customer update speed on shipment status in real time by moving from a daily batch mechanism to an event driven architecture.”

---

## Problem Statement

A description of the current situation, operational or business pain points and their impact on customers or the organization.

* What does not work today  
* What opportunities are being missed  
* What the cost is (financial, reputational or operational)

**Example:**  
> “Customers learn about shipment delays too late which creates overload for the customer support center.”

---

## Objectives and goals

What outcomes the project aims to achieve.  
Define quantitative (measurable) and qualitative goals.

| Goal type | Description | Success metric |
|-------------|--------------|--------------------|
| Business | Increase customer satisfaction | NPS above 80 |
| Operational | Reduce support center calls | 40 percent decrease |
| Technical | Real time update latency | SLA ≤ 3 seconds |

---

## Scope

Precise boundaries of what the project includes and what is out of scope.  
The scope must be feasible, measurable and clear to prevent “scope creep” during development.

**In scope:**  
* (to fill)

**Out of scope:**  
* (to fill)

---

## Stakeholders and users

Project stakeholders and their needs.

| Role | Description | Primary interest |
|--------|---------------|------------------------|
| (to fill) | (to fill) | (to fill) |

**Example:**  
> “Customer service manager wants real time visibility into customer issues.”

---

## Business value and KPIs

The value the project will create for the organization and how success will be measured.  
Metrics should reflect real change rather than just technical completion.

* Cost savings (ROI, cost reduction)  
* Performance or satisfaction improvements  
* Response time or availability  
* Reduction of human errors  

---

## High level business requirements

A list of general requirements strictly from a business perspective.

| Requirement ID | Description | Priority | Notes |
|-------------------|------------------|-----------|----------|
| BR 001 | (to fill) | High | (to fill) |
| BR 002 | (to fill) | Medium | (to fill) |

---

## Constraints and assumptions

Organizational, technical or regulatory constraints that limit the solution  
and the assumptions on which the planning is based.

**Constraints:**  
* (to fill)

**Assumptions:**  
* (to fill)

---

## Risks

Identification of business or operational risks that may impact the success of the project.

| Risk type | Description | Likelihood | Impact | Required response |
|--------------|----------------|----------------|--------------|--------------------------|
| Business | (to fill) | High | Medium | (to fill) |
| Operational | (to fill) | Medium | High | (to fill) |

---

## Sustainability and long term business maintenance

How to ensure the business value is preserved over time:

* Monitoring KPIs after launch  
* Knowledge maintenance and user training  
* Adjusting policies according to business changes  

---

## Approvals

| Role | Name | Signature | Date |
|--------|---------|--------------|-----------|
| Business stakeholder | (to fill) | (to fill) | (to fill) |
| Product manager | (to fill) | (to fill) | (to fill) |
| Final approver | (to fill) | (to fill) | (to fill) |

---

## Summary

At this stage the **business purpose** is documented the reason the project exists.  
This document functions as the compass for the next stage (`PROJECT_SPEC`)  
and defines the direction every technical phase must follow.

---

## Guidance principles

* Maintain business language, not technical.  
* Each section is evaluated based on value, not tasks.  
* The agent can help formulate text and compare metrics but the human defines the goals themselves.

---

## Expected outcome

A clear approved document with measurable business goals and defined boundaries.  
It serves as the **single source of business truth** for all subsequent development stages.

© 2025 Tomer Kedem. Part of the official template collection of Docs as System.
