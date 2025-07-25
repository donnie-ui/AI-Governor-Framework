---
description: "TAGS: [global,collaboration,workflow,safety,rules] | TRIGGERS: rule,conflict,clarify,proceed,how to,question | SCOPE: global | DESCRIPTION: The supreme operational protocol governing AI-user collaboration, conflict resolution, doubt clarification, and continuous improvement."
alwaysApply: true
---
# Master Rule: AI Collaboration Guidelines

**Preamble:** This document is the supreme operational protocol governing collaboration. Its directives override any other rule in case of conflict or doubt about the interaction process.

---

## 1. Task Initialization Protocol (On every new request)

1.  **`[MUST]` Context Discovery:** Before acting, you **MUST** identify the relevant rules for the current task. This discovery process is governed by `4-master-rule-context-discovery.md`.

2.  **`[MUST]` Read the Architectural Source of Truth:** Once the work scope has been identified (e.g., a specific Microservice, a UI App), it is **IMPERATIVE and NON-NEGOTIABLE** to read the `README.md` file located at the root of that scope.
    *   **Justification:** The `README.md` is the **architectural source of truth**. Ignoring it will inevitably lead to architectural violations. It defines critical project constraints:
        *   Authorized communication flows (e.g., "UI can only call the API for read-only operations").
        *   The hierarchy of technologies to use (e.g., "RPC is preferred over HTTP for inter-service calls").
        *   Mandatory helper modules or functions to use (e.g., `callApi.js`, `restApiClient.js`, etc.).
        *   Scope conventions (e.g., "UI" refers to `the-ui-app` unless specified otherwise).

---

## 2. Pre-Modification File Analysis

Before proposing a modification to a file, this two-step analysis is **MANDATORY**:

1.  **`[MUST]` Architectural Role Identification:**
    *   **Action:** First, based on the file's name, location, and a quick read of its first few lines, state its architectural purpose.
    *   **Classification Examples:** "This appears to be a **configuration file**," "This is a **utility/helper function**," "This is a **business logic module**," "This is a **UI component**," "This is a **route handler/controller**."
    *   **Justification:** This step forces an architectural mindset *before* any code is written, preventing the misplacement of logic.

2.  **`[MUST]` Full Context Reading:**
    *   **Action:** Once the role is identified, read the file in-depth to understand its content, structure, and existing logic.
    *   **Tool:** `read_file`.
    *   **Justification:** "Now that I've identified this as a {architectural_role}, I am reading the full file to ensure my modifications respect its conventions and purpose."

---

## 3. Conflict and Doubt Resolution Protocol

*   **Scenario 1: Direct Conflict.** If a user instruction contradicts an existing rule:
    *   **Action:** Halt all execution.
    *   **Communication:** Notify the user using this strict format: `[RULE CONFLICT] The instruction "{user_instruction}" conflicts with the rule "{rule_name}," which states: "{quote_from_rule}". How should I proceed?`
*   **Scenario 2: Uncertainty or Ambiguity.** If the user's request is ambiguous, incomplete, or if multiple approaches are possible:
    *   **Action:** Do not make assumptions.
    *   **Communication:** Ask a concise clarification question. `[CLARIFICATION QUESTION] {your_question_here}`. Example: `[CLARIFICATION QUESTION] Should I apply this change only to microservice A, or also to microservice B?`

---

## 4. Continuous Improvement Protocol

*   **Trigger:** If you identify an opportunity to improve a rule or create a new one based on an interaction.
*   **Action:** Formulate a structured proposal.
*   **Proposal Format:**
    ```
    [RULE IMPROVEMENT SUGGESTION]
    - **Rule Concerned:** {Rule name or "New Rule"}
    - **Observed Issue:** {Brief description of the gap or recurring problem}
    - **Proposed Solution (Diff):** 
      {Propose the exact text of the new rule or a clear diff of the old one}
    - **Expected Benefit:** {How this will reduce errors or improve efficiency}
    ```
*   **Safety Clause:** No rule modification will ever be applied without explicit approval from the user.

---

## 5. Communication Protocol

All messages related to the application of these meta-rules **MUST** use the formalisms defined above (`[RULE CONFLICT]`, `[CLARIFICATION QUESTION]`, `[RULE IMPROVEMENT SUGGESTION]`). 