# 🧰 git — safe operational scripts for Docs as System

This folder contains controlled scripts for executing Git operations in projects managed by the methodology.  
The following rules are always enforced:

* No automatic merging into protected branches  
* Pushing by the agent is blocked by default  
* Every commit is tagged with the current cycle identifier `CYCLE_ID` and recorded in the execution log  

---

## Files

| File | Purpose |
|------|---------|
| `CREATE_BRANCH.sh` | Creates a new branch from the default branch with safety checks. |
| `STAGE_AND_COMMIT.sh` | Stages files according to policy and creates a tagged commit message. |
| `PUSH_BRANCH.sh` | Pushes a branch to origin. Blocked for the agent unless explicitly permitted. |
| `OPEN_PULL_REQUEST.sh` | Opens a draft pull request for human approval through `gh`. |
| `MERGE_AFTER_APPROVAL.sh` | Merges a PR only after human approval and passing all validation checks. |

---

## Useful environment variables

* `DEFAULT_BRANCH` default is `main`  
* `ALLOW_AGENT_PUSH` default is `false`. When set to true, allows pushing in the push script according to project policy  
* `CYCLE_ID` identifier of the current work cycle. Based on date plus a unique daily sequence for example `2025_11_13_001`. Required for commit tagging and consistent documentation  
* `ALLOWED_PATHS` file patterns the agent is permitted to stage in a commit. Default is `docs/** src/**`

---

## Safety principles

* No creation of branches using protected names  
* No automatic pushing without explicit approval  
* No deletion or rewriting of history  
* No merging performed by the agent  
* Every significant action is documented in the execution log and linked to `CYCLE_ID`

---

## Using CYCLE_ID with the logs

* Every commit created through `STAGE_AND_COMMIT.sh` includes the `CYCLE_ID` tag inside the commit message  
* Summary files such as `IMPLEMENTATION_LOG_SUMMARY_*.md` can be generated based on `CYCLE_ID` or date ranges aligned with the same identifier  
* This allows an easy reconstruction of all changes and events that belong to a single work cycle

© 2025 Tomer Kedem. Part of the official template collection of Docs as System.
