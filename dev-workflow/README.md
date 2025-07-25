# AI Development Workflow

This directory contains the sequential workflow protocols that structure the entire development process, from idea to review. They are designed to be used in order, ensuring a comprehensive and well-documented implementation cycle.

## The 4-Step Workflow

The framework operates on a clear, 4-step loop. The AI assistant should be prompted to execute each protocol in sequence. Below is a guide on how to initiate each phase.

---

### 1️⃣ **Phase 1: PRD Creation (`1-create-prd.md`)**

-   **Role:** Product Manager
-   **Goal:** To transform a user request into a detailed Product Requirements Document (PRD).
-   **How to start:** To begin, use a prompt like the following in your AI assistant:
    ```
    Apply the instructions from @ai-dev-assistant-framework/dev-workflow/1-create-prd.md.

    I want to create a new feature: [Describe your feature, its goal, and its target users].
    ```
    The AI will then ask targeted questions to build the PRD.

---

### 2️⃣ **Phase 2: Task Generation (`2-generate-tasks.md`)**

-   **Role:** Tech Lead
-   **Goal:** To break down the PRD into a granular, actionable checklist of technical tasks.
-   **How to start:** Once the PRD is created (e.g., in `tasks/prd-my-feature.md`), use a prompt like this:
    ```
    Apply the instructions from @ai-dev-assistant-framework/dev-workflow/2-generate-tasks.md to the content of the PRD in @tasks/prd-my-feature.md to generate the technical execution plan.
    ```

---

### 3️⃣ **Phase 3: Task Processing (`3-process-tasks.md`)**

-   **Role:** Paired Developer
-   **Goal:** To execute the task list step-by-step with user validation.
-   **How to start:** With the task list generated (e.g., in `tasks/tasks-my-feature.md`), kick off the execution:
    ```
    Now, apply all instructions from @ai-dev-assistant-framework/dev-workflow/3-process-tasks.md to the content of the task file @tasks/tasks-my-feature.md. Please start with the first task.
    ```

---

### 4️⃣ **Phase 4: Implementation Retrospective (`4-implementation-retrospective.md`)**

-   **Role:** QA & Process Improvement Lead
-   **Goal:** To audit the implementation for quality and improve the framework itself.
-   **How to start:** After all tasks are complete, initiate the final review:
    ```
    The implementation is complete. Please initiate an implementation retrospective by applying the instructions from @ai-dev-assistant-framework/dev-workflow/4-implementation-retrospective.md.
    ``` 