# Ready-to-Use Prompts

For direct insertion into the prompts library.  
The texts are written so the agent operates **only** through existing files and scripts,  
never through raw commands.

---

## Pre-checks Before Any Logical Operation

* Read `AGENT_CONFIG_TEMPLATE.yaml`
* Validate that all required values exist; if anything is missing, stop and ask for clarification
* Act only according to the prompt matching the task
* Do not run raw Git commands; use only scripts inside `automation/git`
* Update only files inside paths allowed by `allowedPaths`

---

## Execution Prompt: Open a New Cycle and Create Cycle-Based Logs

> Must run first: Pre-checks Before Any Logical Operation

### Purpose  
Opening a new work cycle and preparing logs and summaries  
according to the settings in `AGENT_CONFIG_TEMPLATE.yaml`.

### Instructions
1. Read `AGENT_CONFIG_TEMPLATE.yaml` and locate  
   `logging.basePath`, `logging.rotationPolicy`, and `logging.summaryTemplatePath`.
2. If `rotationPolicy` is not `by_cycle`, stop and ask for approval.  
   If the value is `by_cycle`, continue.
3. Generate a new cycle identifier.  
   If a known ID exists in planning documents or in the current branch, use it.  
   If not, propose an ID in the form `CYCLE_YYYYMMDD_HHMM`.
4. Create a new log file inside `logging.basePath` with the name:
   `IMPLEMENTATION_LOG_<cycle_id>.md`  
   If a previous cycle log exists and is still open, leave it unchanged.
5. Add a header to the new log file including the cycle ID, date, and empty fields for  
   operations, results, and references.
6. Generate an initial summary using the template in `summaryTemplatePath`  
   and save it under `docs/logs` with the name:  
   `IMPLEMENTATION_LOG_SUMMARY_<cycle_id>.he.md`  
   Fill only header and metadata fields. Do not invent any content.
7. Report what was created with exact file paths.

### Rules
Do not execute raw Git commands.  
If a commit is needed, use only `automation/git/STAGE_AND_COMMIT.sh`.

---

## Execution Prompt: Manual Log Rotation for an Existing Cycle

> Must run first: Pre-checks Before Any Logical Operation

### Purpose  
Closing the current cycle log and opening a new one when  
`rotationPolicy` is `by_cycle` or `manual`.

### Instructions
1. Read `AGENT_CONFIG_TEMPLATE.yaml`.  
   If `rotationPolicy` is `monthly`, stop and ask for approval.
2. Determine the current cycle based on the open log file name  
   or by reading the latest log in the logs directory.
3. Close the current log by adding a timestamp and a `Status: Closed` field.
4. Generate an updated summary into  
   `IMPLEMENTATION_LOG_SUMMARY_<cycle_id>.he.md`  
   Fill only status and date fields.  
   Do not summarize technical content without sources.
5. Open a new log for the next cycle:  
   `IMPLEMENTATION_LOG_<new_cycle_id>.md`  
   Initialize with a header and empty field template.
6. Report which log was closed, which new log was opened,  
   and return the file paths.

### Rules
No direct Git commands.  
For commits, call `automation/git/STAGE_AND_COMMIT.sh`.

---

## Execution Prompt: Register an Action in the Active Cycle Log

> Must run first: Pre-checks Before Any Logical Operation

### Purpose  
Recording a new action in the log of the currently active cycle.

### Instructions
1. Locate the latest `IMPLEMENTATION_LOG_<cycle_id>.md` in the logs directory.
2. Append a new entry at the bottom in the following structure:
   - Date and time  
   - Actor (Agent or Human)  
   - Affected files (paths relative to repo root)  
   - Short action description  
   - Result (success or failure)  
   - Commit IDs if available  
3. Do not create fields that do not exist in the log template.
4. Save the file and return the modified path.

### Rules
If a summary update is required, do not update it manually.  
Use the dedicated summary-update prompt.

---

## Execution Prompt: Update Cycle Summary Based on the Log

> Must run first: Pre-checks Before Any Logical Operation

### Purpose  
Updating the cycle summary file using data from `IMPLEMENTATION_LOG_<cycle_id>.md`.

### Instructions
1. Locate the cycle summary file:  
   `IMPLEMENTATION_LOG_SUMMARY_<cycle_id>.he.md`  
   If it does not exist, generate it using the template in `summaryTemplatePath`.
2. Summarize data strictly according to fields that exist in the template.  
   No new fields may be added.
3. Report how many actions were performed, how many succeeded, failed,  
   and how many items remain open.
4. Save the file and return the modified path.

### Rules
Do not write content not present in the log.  
Every statement must be backed by existing log entries.

---

## Execution Prompt: Commit With Link to Cycle Log

> Must run first: Pre-checks Before Any Logical Operation

### Purpose  
Creating a standards-compliant commit that links to the current cycle log.

### Instructions
1. Read `AGENT_CONFIG_TEMPLATE.yaml` and locate  
   `git.allowedPaths` and `commitMessage.includeCycleLogLink`.
2. Validate that all changed files are inside allowed paths.  
   If not, stop and request approval.
3. Build a short commit message with tags if `includeTags` is `true`.
4. If `includeCycleLogLink` is `true`, append the trailer:  
   `Relates-to-log docs/logs/IMPLEMENTATION_LOG_<cycle_id>.md`
5. Call only `automation/git/STAGE_AND_COMMIT.sh` with the constructed message.
6. Report the commit message used and list included files.

### Rules
No direct Git commands.  
No push.  
No opening of PRs in this prompt.

---

© 2025 Tomer Kedem. Part of the official **Docs-as-System** template collection.
