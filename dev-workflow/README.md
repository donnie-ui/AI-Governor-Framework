
This directory contains a series of numbered protocols that define a structured, repeatable, and AI-powered development workflow.

The process is designed to be sequential. You should always start with Protocol 0 for any new project.

### The Protocols

1.  **`0-bootstrap-your-project.md`**: **(Run this first!)** This is a one-time setup protocol. The AI will analyze your codebase, install the framework's rule structure, and generate a foundational "Context Kit" of `READMEs` and project-specific rules.

2.  **`1-create-prd.md`**: This protocol guides the AI to act as a Product Manager, helping you think through a new feature and generate a clear Product Requirements Document (PRD).

3.  **`2-generate-tasks.md`**: The AI takes the PRD and, acting as a Tech Lead, breaks it down into a detailed, actionable task list for implementation.

### 1️⃣ Create a Product Requirement Document (PRD)

Start by defining the "what" and "why" of your feature. The AI will act as a Product Manager, interviewing you to create a comprehensive specification.

In your AI tool, initiate PRD creation:
```text
Apply instructions from @1-create-prd.md
Here's the feature I want to build: [Describe your feature in detail]
```
*(Pro Tip: For complex features, it's recommended to use your AI tool's most powerful model. For **Cursor users**, using **Max Mode** is highly recommended for better results, especially for this step.)*

### 2️⃣ Generate Your Task List from the PRD

Once the PRD is created (e.g., `prd-my-feature.md`), transform it into a granular, step-by-step technical plan for your AI developer.

```text
Apply instructions from @2-generate-tasks.md to @prd-my-feature.md
```
*(Note: Replace `@prd-my-feature.md` with the actual filename of the PRD you generated in step 1.)*

*(Pro Tip: For **Cursor users**, using **Max Mode** is also recommended for this step to ensure a more detailed and accurate breakdown of the PRD.)*

You'll get a well-structured task list, providing a clear roadmap for implementation.

### 3️⃣ Execute Tasks Sequentially

Now, instruct the AI to work through the generated plan. This protocol ensures the AI tackles one sub-task at a time and waits for your validation before proceeding, giving you full control.

1.  Tell the AI to start with the first task:
    ```text
    Apply instructions from @3-process-tasks.md to @tasks-my-feature.md. Start on task 1.1
    ```
    *(Note: Replace `@tasks-my-feature.md` with the task file generated in step 2. You only need to invoke this protocol for the *first* task; the protocol itself guides the AI for subsequent tasks.)*

2.  **Review, Approve, and Progress ✅**
    As the AI completes each sub-task, it will present the changes for your review.
    *   If the changes are correct, reply with "yes" or "continue" to have the AI mark the task as complete and move to the next one.
    *   If changes are needed, provide corrective feedback before proceeding.

### 4️⃣ Conduct an Implementation Retrospective

Once all tasks are complete, the final step is to reflect on the process to improve future collaborations. The AI will act as a QA Lead, auditing the code and interviewing you to refine the project's rules and workflows.

```text
Apply instructions from @4-implementation-retrospective.md
```
This final step is crucial for evolving your "Context Kit", making the AI smarter and more aligned with your project's standards over time. 


## 💡 A Note on the First Run: The Learning Curve

Your first few interactions with the AI using this framework might require more corrections and clarifications. **This is normal and by design.** You are actively *teaching* the assistant the specific nuances of your codebase.

Think of it as onboarding a new junior developer. The initial investment in teaching pays off exponentially. With each iteration, the AI's context gets richer, its proposals become more accurate, and it evolves from a generic tool into a true expert companion for your project.
