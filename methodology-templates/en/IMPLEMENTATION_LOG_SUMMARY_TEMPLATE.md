# IMPLEMENTATION_LOG_SUMMARY_TEMPLATE.md

**Document Type:** Action Summary Template  
**Purpose:** Serves as the base template for creating the `summary-LATEST.md` file in any real project.  
This file provides an up-to-date view of the development state, recent actions, and active exceptions.  
It is generated and updated automatically by the agent based on data from `IMPLEMENTATION_LOG.md`.

---

## General Information

Updated: YYYY-MM-DD  
Total Commits: 0  
Human-Approved Percentage: 0%  
Active Exceptions: 0  

---

## Recent Actions

| Date | Action | Status | Approved By |
| --- | --- | --- | --- |
| YYYY-MM-DD | Commit | Passed | Agent |
| YYYY-MM-DD | Merge | Passed | Human |
| YYYY-MM-DD | Test | Warning | Agent |

> Only the last 10 records are displayed.  
> The agent refreshes this table with every CI run or new PR.

---

## Active Exceptions

| ID | Description | Status | Created By | Last Updated |
| --- | --- | --- | --- | --- |
| EXC-000 | Security issue in communication module | Open | Agent | YYYY-MM-DD |
| EXC-001 | Integration tests failed | Fixed | Human | YYYY-MM-DD |

> Closed exceptions are automatically archived.  
> Only active exceptions are displayed here.

---

## General Metrics

| Metric | Current Value | Target | Notes |
| --- | --- | --- | --- |
| Commits performed by Agent | 0 | - | Automatically updated |
| Human-Approved Commits (%) | 0% | ≥ 90% | Quality metric |
| Average PR Approval Time | 0 minutes | - | Calculated by CI |
| Number of Active Exceptions | 0 | 0 | Target: no active exceptions |

---

## Data Source

- Logs are retrieved from files in `docs/logs/IMPLEMENTATION_LOG-YYYY-MM.md`
- Data is updated by the agent during runtime and at the end of each pipeline.
- This file is never edited manually.

---

## Usage Guidelines

- This file provides a current snapshot of the project status.  
- Do not edit it manually.  
- Any manual change will be overwritten by the agent.  
- For historical tracking, refer to archived logs (`IMPLEMENTATION_LOG-YYYY-MM.md`).

---

© 2025 Tomer Kedem. Part of the official **Docs-as-System** template suite.
