# Work Cycle Log  
This file is used to consolidate all actions, decisions and changes performed within a single work cycle — sprint, release, predefined time window or any other cycle definition.

Unlike the main implementation log, which documents all events throughout the lifetime of the project, this file records only the actions relevant to the current cycle.  
It enables focused tracking, effective control and precise reconstruction of everything that occurred during a defined period.

The log serves as a middle layer between the “full log” and the “executive summary” and is intended for developers, testers, architects and project managers who need detailed but time scoped documentation.

---

## Recommended structure for each entry

Each entry should map exactly one action or change.

- Date  
- Time  
- Actor (human or AI agent)  
- Type of action  
- File or component modified  
- Short description of what was done  
- Action result (success, failure, additional work required)  
- Commit or version identifier (if applicable)  
- Relevant link (for example, to a specification document)  
- Notes or important additions  

---

## Main use cases of the cycle log

- Consolidated documentation of cycle progress  
- Tracking actions performed by human or agent  
- Identifying recurring issues or patterns  
- Supporting internal audits  
- Analyzing workloads or bottlenecks  
- Automatic preparation of the executive summary  
- Full reconstruction of the event sequence for a specific cycle  

---

## Usage guidelines

- A new log should be opened at the beginning of each cycle.  
- The log should be formally closed at the end of the cycle.  
- This log does not replace the main implementation log — it sits on top of it.  
- It is recommended to store these files in `docs/logs/cycles/` (or another suitable folder).  
- Only an authorized human should formally sign off the log closure.  

---

© 2025 Tomer Kedem. Part of the official **Docs-as-System** template collection.
