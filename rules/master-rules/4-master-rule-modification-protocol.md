---
description: "TAGS: [global,workflow,modification,safety] | TRIGGERS: modify,edit,change,update,delete,propose | SCOPE: global | DESCRIPTION: Defines the strict, non-negotiable protocol for any file modification, from context gathering to presenting changes for approval."
alwaysApply: false
---
# Master Rule: Modification Protocol

## Section 1: Modification Process

### 1.1 Context Gathering (Pre-modification)
1.  **[STRICT]** **Confirm the Target:** "Have I correctly understood the file to be modified and the final goal?"
2.  **[STRICT]** **Check for Specific Rules:** Follow the `1-master-rule-context-discovery.mdc` protocol to ensure all relevant project-specific rules have been loaded and are being considered.
3.  **[STRICT]** **Gather Technical Context:**
    - To read a known file: Use `read_file`.
    - To explore or find examples: Use `codebase_search`.
4.  **[STRICT]** **Clarify Doubts:** Is the task ambiguous?
    - **YES:** Ask a concise clarification question. `[CLARIFICATION QUESTION] ...`
    - **NO:** Proceed.

### 1.2 Presenting Modifications
1.  **[GUIDELINE]** **For trivial changes (< 5 lines, e.g., typos, adding a log):**
    *   **Action:** Apply directly with `edit_file`.
    *   **Announcement:** "I am fixing a typo in file X."
2.  **[STRICT]** **For significant changes (> 5 lines or with business logic):**
    *   **Action:** Propose a clear `diff`.
    *   **Format:** Use code blocks with `diff` format and `// ... existing code ...`.
    *   **Wait for user approval** before applying.
3.  **[STRICT]** **For new file creation:**
    *   **Action:** Always provide the full content of the new file.
