---
description: "TAGS: [global,workflow,context,rules,discovery] | TRIGGERS: rule,context,understand,project,setup | SCOPE: global | DESCRIPTION: Defines the systematic process an AI assistant must follow to discover and select relevant rules and context before starting any task."
alwaysApply: true
---
# Master Rule: Context Discovery Protocol

## 1. Systematic Rule Discovery Process

**[STRICT]** Before executing any code or command, the Agent **MUST** imperatively follow these steps in this exact order to build its operational context.

### Step 1: Full Inventory
- **[STRICT]** **Action:** The AI must have a way to list all available rule files (e.g., `.md` or `.mdc` files in a `.cursor/rules` directory). This can be done via `find` or by reading from a cached list.
- **[GUIDELINE]** **Goal:** To create an exhaustive list of all rule files present in the entire repository.

### Step 2: Core System Initialization (Kernel Loading)
- **[STRICT]** Immediately after the inventory, you **MUST** load the `2-master-rule-ai-collaboration-guidelines.mdc` rule. This rule governs your fundamental interaction behavior (doubt, conflict) and must be active for all subsequent steps, including the rest of the discovery process itself. This ensures a deterministic and safe boot sequence.

### Step 3: Intelligent Contextual Analysis
**[STRICT]** FOR EACH RULE FOUND (excluding the already-loaded `2-master-rule-ai-collaboration-guidelines.mdc`):

1.  **Attempt to Parse Metadata:** Read the YAML frontmatter block.
2.  **If Metadata is Well-Formed:**
    *   Use `TAGS`, `TRIGGERS`, and `SCOPE` for relevance evaluation.
3.  **If Metadata is Missing or Malformed (Fallback Protocol):**
    *   **MUST NOT** read the entire file.
    *   **MUST** read only the first ~15 lines.
    *   **MUST** infer purpose from the title and first paragraph.
    *   *Note: In this case, the `[CLARIFICATION QUESTION]` protocol from the collaboration rule should be used if the inference is ambiguous.*

### Step 4: Weighted Relevance Evaluation Algorithm
**[STRICT]** The AI Agent **MUST** use the following weighted algorithm to assess the relevance of each rule:
(The sub-steps for Level 1-4 remain the same)
1.  **Level 1: Absolute Directives (`alwaysApply`)**
2.  **Level 2: Scope Matching (`SCOPE`)**
3.  **Level 3: Keyword Matching (`TRIGGERS`)**
4.  **Level 4: Concept Matching (`TAGS`)**

### Step 5: Report and Application
**[BLOCKING AND MANDATORY ACTION]**

After selecting the relevant rules, your VERY FIRST action **MUST** be to announce the loaded rules to the user. You **MUST NOT** start any other action, explanation, or write any code before producing this announcement.

The announcement format is **NON-NEGOTIABLE**:
> *"I have loaded the `{rule-name-1}` and `{rule-name-2}` rules, which cover {relevant_domain} for your request. I am ready to begin."*

---

## 🏷️ Standardized Tagging System (For Metadata)
... (The rest of the file remains the same)
...
