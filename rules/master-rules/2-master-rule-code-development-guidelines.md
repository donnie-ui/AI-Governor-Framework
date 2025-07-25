---
description: "TAGS: [global,quality,development,workflow,best-practices] | TRIGGERS: code,develop,modify,refactor,implement,fix | SCOPE: global | DESCRIPTION: A foundational directive for all code development, defining checklists for quality, reliability, and clarity, as well as a strict process for making modifications."
alwaysApply: true
---
# Master Rule: Code Development Directive

## Section 1: Code Quality (Implementation Checklist)
For any new code or modification, the Agent **MUST** validate every point on this checklist.

### 1.1 Robustness and Reliability
- **Error Handling:**
    - Any I/O operation, API call, or parsing action (e.g., `JSON.parse`) **MUST** be wrapped in a `try...catch` block.
    - The `catch` block **MUST** log the error informatively and **MUST NOT** be left empty.
- **Input Validation:**
    - Any function exposed to an external source (API, user input) **MUST** begin with a guard-clause block to validate arguments.
    - **NEVER** trust external data.
- **Non-Regression:**
    - Before modifying an existing function, use `codebase_search` to find its usages.
    - **Ask yourself:** "Could my change break any of these usages?" If yes, inform the user.

### 1.3 Security & Non-Regression Protocol
-   **`[MUST]` Perform a Regression Check:** Before modifying an existing function, you **MUST** use `codebase_search` to find all its call sites.
-   **`[MUST]` Announce Potential Impact:** If there are multiple call sites or if the change affects a critical function, you **MUST** announce the risk and seek validation using this exact format:
    > `[REGRESSION RISK] The function {function_name} is used in {N} places. Modifying it could impact: {list of files or modules}. Do you want to proceed with this modification?`
-   **`[MUST NOT]` Proceed Without Approval:** Do not proceed with the modification until the user gives explicit approval.

### 1.2 Simplicity and Clarity
- **Single Responsibility Principle (SRP):**
    - A function **SHOULD NOT** exceed 20-30 lines (excluding comments/whitespace). If it does, propose a refactor to break it down into smaller functions.
- **Naming Conventions:**
    - Variable and function names **MUST** be explicit (e.g., `userList` instead of `data`).
    - Booleans **MUST** start with a prefix like `is`, `has`, or `can` (e.g., `isUserAdmin`).
- **Nesting:**
    - The nesting depth of `if`/`for` blocks **SHOULD NOT** exceed 3 levels. Use guard clauses to reduce complexity.

## Section 2: Modification Process

### 2.1 Context Gathering (Pre-modification)
1.  **`[MUST]` Confirm the Target:** "Have I correctly understood the file to be modified and the final goal?"
2.  **`[MUST]` Check for Specific Rules:** Follow the `4-master-rule-context-discovery.md` protocol to ensure all relevant project-specific rules have been loaded and are being considered.
3.  **`[MUST]` Gather Technical Context:** 
    - To read a known file: Use `read_file`.
    - To explore or find examples: Use `codebase_search`.
4.  **`[MUST]` Clarify Doubts:** Is the task ambiguous?
    - **YES:** Ask a concise clarification question. `[CLARIFICATION QUESTION] ...`
    - **NO:** Proceed.

### 2.2 Presenting Modifications
1.  **For trivial changes (< 5 lines, e.g., typos, adding a log):**
    *   **Action:** Apply directly with `edit_file`.
    *   **Announcement:** "I am fixing a typo in file X."
2.  **For significant changes (> 5 lines or with business logic):**
    *   **Action:** Propose a clear `diff`.
    *   **Format:** Use code blocks with `diff` format and `// ... existing code ...`.
    *   **Wait for user approval** before applying.
3.  **For new file creation:**
    *   **Action:** Always provide the full content of the new file.

## Section 3: High-Level Project Standards (To be adapted by the user)

This section provides a template for enforcing project-specific rules. Users of this framework should adapt this section to point to their own concrete rules.

### 3.1 Backend Example (`@project-rules/project-rule-api-conventions.md`)
- **`[MUST]` Validate ALL External Inputs:** Enforce the project's data validation rule (e.g., `@api-validation-rule`) and **only** use the sanitized result.
- **`[MUST]` Follow Established Patterns:** For a new API endpoint, strictly follow the established handler pattern (e.g., `@route-handler-pattern`).
- **`[MUST]` Perform a Security Review:** Before committing, systematically check for secret leaks, overly verbose error responses, and proper authorization logic.

### 3.2 Frontend Example (`@project-rules/project-rule-ui-component-standards.md`)
- **`[MUST]` Scope Styles:** All CSS styles must be scoped to the component's root class to prevent side effects.
- **`[MUST]` Use Theme Variables:** For all colors, fonts, and spacing, **MUST** use the global CSS theme variables.
- **`[MUST]` Handle All API States:** Always handle and provide user feedback for `loading`, `success`, and `error` states of network calls.

## Section 4: Examples and Anti-Patterns

<example>
**VALID Error Handling**
```javascript
async function getUser(userId) {
  if (!userId) {
    console.error("User ID is required.");
    return null; // Guard clause
  }
  try {
    const response = await fetch(`/api/users/${userId}`);
    if (!response.ok) {
        throw new Error(`HTTP error! status: ${response.status}`);
    }
    return await response.json();
  } catch (error) {
    console.error("Failed to fetch user:", error);
    return null;
  }
}
```
</example>

<example type="invalid">
**INVALID Error Handling (too vague)**
```javascript
// AVOID
async function getUser(userId) {
  try {
    const data = await fetch(`/api/users/${userId}`);
    return data.json();
  } catch (e) {
    // This catch is empty or too generic, information is lost
    return null;
  }
}
```
</example> 