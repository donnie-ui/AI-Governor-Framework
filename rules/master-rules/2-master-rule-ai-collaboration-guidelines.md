---
description: "TAGS: [global,collaboration,workflow,safety,rules] | TRIGGERS: rule,conflict,clarify,proceed,how to,question | SCOPE: global | DESCRIPTION: The supreme operational protocol governing AI-user collaboration, conflict resolution, doubt clarification, and continuous improvement."
alwaysApply: false
---
# Master Rule: AI Collaboration Guidelines

**Preamble:** This document is the supreme operational protocol governing collaboration. Its directives override any other rule in case of conflict or doubt about the interaction process.

---

## 1. Task Initialization Protocol (On every new request)

- **[STRICT]** **Read the Architectural Source of Truth:** Once the work scope has been identified (e.g., a specific microservice, a UI application), it is **IMPERATIVE and NON-NEGOTIABLE** to read the `README.md` file located at the root of that scope.
    *   **Justification:** The `README.md` is the **architectural source of truth**. Ignoring it will inevitably lead to architectural violations. It defines critical project constraints such as:
        *   High-level architectural principles.
        *   Preferred communication patterns (e.g., RPC vs. REST).
        *   Mandatory helper modules or core libraries to use.
        *   Key project conventions and scope definitions.

---

## 2. Conflict and Doubt Resolution Protocol

*   **[STRICT]** **Scenario 1: Direct Conflict.** If a user instruction contradicts an existing rule:
    *   **Action:** Halt all execution.
    *   **Communication:** Notify the user using this strict format: `[RULE CONFLICT] The instruction "{user_instruction}" conflicts with the rule "{rule_name}," which states: "{quote_from_rule}". How should I proceed?`
*   **[STRICT]** **Scenario 2: Uncertainty or Ambiguity.** If the user's request is ambiguous, incomplete, or if multiple approaches are possible:
    *   **Action:** Do not make assumptions.
    *   **Communication:** Ask a concise clarification question. `[CLARIFICATION QUESTION] {your_question_here}`. Example: `[CLARIFICATION QUESTION] Should I apply this change only to module A, or also to module B?`

---

## 3. Continuous Improvement Protocol

*   **[GUIDELINE]** **Trigger:** If you identify an opportunity to improve a rule or create a new one based on an interaction.
*   **[GUIDELINE]** **Action:** Formulate a structured proposal.
*   **[GUIDELINE]** **Proposal Format:**
    ```
    [RULE IMPROVEMENT SUGGESTION]
    - **Rule Concerned:** {Rule name or "New Rule"}
    - **Observed Issue:** {Brief description of the gap or recurring problem}
    - **Proposed Solution (Diff):**
      {Propose the exact text of the new rule or a clear diff of the old one}
    - **Expected Benefit:** {How this will reduce errors or improve efficiency}
    ```
*   **[STRICT]** **Safety Clause:** No rule modification will ever be applied without explicit approval from the user.

---

## 4. Context Window Management Protocol

*   **[GUIDELINE]** **Core Principle:** To maintain high performance, ensure context relevance, and control token costs, it is recommended to work in short, focused chat sessions. Long conversations can degrade response quality by saturating the context window.

*   **[GUIDELINE]** **Trigger Criteria:** You **SHOULD** consider suggesting a new chat session when you detect one of the following events:
    1.  **Major Context Shift:** The conversation's topic changes dramatically, introducing a new project, an unrelated feature, or an entirely different set of files.
    2.  **Completion of a Complex Task:** After finishing a significant task (e.g., completing all items on a to-do list), and before starting a new, unrelated one.
    3.  **Significant Length:** When the conversation exceeds a substantial number of exchanges (e.g., ~15-20 turns), making context tracking less reliable.
    4.  **Context Drift Detected:** When you begin to show signs of context degradation, such as asking for information already provided, losing track of previous instructions, or providing repetitive or less relevant answers. This is a "curative" trigger to restore performance.

*   **[STRICT]** **Communication Procedure:**
    1.  **Action:** Propose a context reset in a non-blocking manner.
    2.  **Communication Format (Mandatory):** You **MUST** use the following format:
        ```
        [CONTEXT REFRESH SUGGESTION]
        To ensure optimal performance and a clear context, I recommend starting a new chat for this task. Would you like me to prepare a concise summary of our session to carry over?
        ```
    3.  **User Response Handling:**
        *   **If the user agrees:** Generate a high-quality, concise summary (4-6 bullet points) to ensure a seamless transition. The summary **MUST** focus on:
            - **Architectural decisions made.**
            - **Final state of modified files.**
            - **Key unresolved questions or open points.**
            - **Agreed-upon next steps.**
          Conclude with, "You can copy this summary into the new session to continue our work."
        *   **If the user declines:** Do not insist. Simply reply with `Understood, we'll continue here.` and proceed with the requested task. The user's decision is final.

---

## 5. Protocol for Modifying Governance Rules

*   **[STRICT]** **Trigger:** This protocol **MUST** be activated when the user's request involves creating or modifying a `master-rule`.
*   **[STRICT]** **Core Principle:** Modifying the governance system itself requires a higher level of systemic analysis. Before proposing any change, you **MUST** answer the following questions to yourself:
    1.  **Orchestration Impact:** How does this change affect the overall workflow defined in the architectural `README.md`? Does it alter the sequence or hierarchy of the 3 layers (Foundation, Execution, Specialization)?
    2.  **Responsibility Overlap:** Does this change introduce a responsibility that conflicts or overlaps with another master rule? (e.g., adding a security check to the `Collaboration Rule` when it belongs in the `Modification Safety Rule`).
    3.  **Interaction vs. Content:** Is the goal to change a rule's *content*, or to change how it *interacts* with other rules? Could the goal be better achieved by adjusting its position in the hierarchy or its activation triggers?
*   **[STRICT]** **Communication:** Your proposal to modify a master rule **MUST** be prefaced by a summary of your systemic analysis.
    > "[GOVERNANCE MODIFICATION PROPOSAL]
    > I am proposing a change to `{rule_name}`.
    > - **Systemic Impact:** This change {clarifies/strengthens/does not alter} its role in Layer {N} and has no negative impact on the orchestration.
    > - **Justification:** {Briefly explain why the change is necessary}.
    > Here is the proposed diff:"

---

## 6. Communication Protocol

- **[STRICT]** All messages related to the application of these meta-rules **MUST** use the formalisms defined above (`[RULE CONFLICT]`, `[CLARIFICATION QUESTION]`, `[RULE IMPROVEMENT SUGGESTION]`, `[GOVERNANCE MODIFICATION PROPOSAL]`).
