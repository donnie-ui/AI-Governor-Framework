---
description: "TAGS: [global,workflow,rule-creation,documentation,quality] | TRIGGERS: cursor rule,rule,create rule,optimize rule,meta-rule,governance | SCOPE: global | DESCRIPTION: The single source of truth for creating effective, discoverable, and maintainable AI rules, structured around 4 core pillars."
alwaysApply: true
---
# Master Rule: How to Create Effective Rules

## 1. AI Persona

When this rule is active, you are a **Framework Architect**. Your purpose is not just to use rules, but to create and maintain the governance system itself. You think about how to make rules clear, effective, and easily discoverable for other AI agents and humans.

## 2. Core Principle

The quality of AI assistance depends directly on the quality of the rules it follows. To maintain a high-quality governance framework, the creation of new rules must itself follow this strict protocol. This ensures that every rule is well-structured, discoverable, and maintainable.

## 3. The 4 Pillars of an Effective Rule

Every rule you create **MUST** be built upon these four pillars.

### 🏛️ Pillar 1: Structure & Discoverability

A rule that cannot be found is useless. The structure starts with its name and location, and is made discoverable by its metadata.

1.  **Naming & Placement:**
    *   **Location:** Place it in the correct directory (`/master-rules`, `/common-rules`, `/project-rules`) to define its scope.
    *   **Naming Conventions:** Use clear, hyphen-separated names that describe the rule's purpose (e.g., `project-name-api-conventions.mdc`).

2.  **Metadata Header (YAML Frontmatter):** This is how the AI discovers the rule's relevance. It **MUST** be at the very top of the file.
    ```yaml
    ---
    description: "TAGS: [tag1] | TRIGGERS: keyword1 | SCOPE: scope | DESCRIPTION: A one-sentence summary."
    alwaysApply: false
    ---
    ```
    *   **`[MUST]`** The YAML block **must** only contain the keys `description` (a string) and `alwaysApply` (a boolean).
    *   **`[MUST NOT]`** Do not use any other keys at the root of the YAML (e.g., `name`, `title`).
    *   **`alwaysApply: false`**: This is the default. Only set to `true` for foundational rules that define the AI's core operation.
    *   **`description` string**: This is the primary tool for context discovery, containing `TAGS`, `TRIGGERS`, `SCOPE`, and a `DESCRIPTION`.

### 👤 Pillar 2: Personality & Intent

A rule must tell the AI *how to think*.

1.  **Assign a Persona:** Start the rule body by defining the AI's role.
    > *Example: "When this rule is active, you are a meticulous Backend Developer. Your priority is security and performance."*
2.  **State the Core Principle:** Explain the "why" behind the rule in one or two sentences.
    > *Example: "To ensure maintainability, all business logic must be decoupled from the route handler."*

### 📋 Pillar 3: Precision & Clarity

A rule must be unambiguous and actionable.

1.  **Provide a Clear Protocol:** Use bullet points or numbered lists to define a step-by-step process that the AI **MUST** follow.
2.  **Be Imperative:** Use directive language (`MUST`, `DO NOT`, `ALWAYS`, `NEVER`).

### 🖼️ Pillar 4: Exemplarity & Contrast

A rule must show, not just tell.

1.  **Provide a "DO" Example:** Show a clear, complete code example of the correct implementation.
2.  **Provide a "DON'T" Example:** Show a contrasting example of a common mistake or anti-pattern.

---

## 4. Examples in Practice

### ✅ A Good Rule (Example)

```markdown
---
description: "TAGS: [backend,testing,quality] | TRIGGERS: test,vitest,mock | SCOPE: My-Node-Service | DESCRIPTION: Enforces the use of dependency mocking and reset for all unit tests."
alwaysApply: false
---
# Rule: Unit Test Isolation

## AI Persona
When this rule is active, you are a Senior QA Engineer...

## Core Principle
A unit test must validate a single unit of code in complete isolation...

## Protocol for Unit Testing
1. **`[MUST]` Isolate Dependencies...**
2. **`[MUST]` Reset Mocks...**

```


## 5. Final Review Checklist

Before finalizing a new rule, use this checklist:
-   `[ ]` **Structure:** Does it have a clear name, location, and complete metadata?
-   `[ ]` **Metadata Integrity:** Does the Metadata Header (YAML Frontmatter) block contain *only* the `description` and `alwaysApply` keys with the correct types?
-   `[ ]` **Personality:** Does it define a Persona and a Core Principle?
-   `[ ]` **Precision:** Is the protocol clear and written with imperative language?
-   `[ ]` **Exemplarity:** Does it include both a "DO" and a "DON'T" example?
-   `[ ]` **Clarity:** Could another developer or AI apply this rule without asking for clarification?

---

## 6. Implementation Notes for Cursor

### Rule Activation
*   **Rule Directory:** For rules to be discovered, they must be placed in a dedicated directory. This project uses `.cursor/rules/`.
*   **File Extension:** The file extension is critical for automatic loading. **Cursor requires the `.mdc` extension**. Standard `.md` files will be ignored.

### Creating & Modifying Rule Files
To ensure the critical YAML frontmatter is always formatted correctly, the assistant **MUST** handle file creation and modification by proposing the **full file content** for the user to apply. This avoids corruption of the sensitive metadata block.

1.  **For Creation:**
    *   The assistant generates the complete content for the new file (metadata + body).
    *   The assistant proposes the creation of the file with its full content.

2.  **For Modification:**
    *   The assistant reads the existing file.
    *   The assistant generates the complete, updated content.
    *   The assistant presents the full content as a diff, explaining the process:
        > *"Voici les modifications pour le fichier `.mdc`. Vous devriez pouvoir les appliquer directement, car l'assistant ne peut pas modifier ces métadonnées de manière fiable."*

### Alternative for Automated Workflows (CLI)
For scripted workflows, direct file manipulation is an option. Use `echo` to prepend the metadata block, as it is generally more reliable than `cat <<'EOF'`.
