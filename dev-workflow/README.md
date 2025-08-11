# The Governor Workflow: From Idea to Production

## 1. Why: A Structured Workflow for Predictable Results

Working with AI can sometimes feel unpredictable. The Governor Framework provides a development workflow designed to fix that.

It provides a structured, sequential process that transforms your AI from a simple code generator into a reliable engineering partner. By following these five protocols, you ensure that both you and the AI are always aligned, moving from a high-level idea to a well-implemented feature with clarity, control, and consistency.

The goal is to make AI-powered development:
-   **Predictable:** Each step has a clear purpose and output.
-   **Controllable:** You are always in the loop for key decisions.
-   **Efficient:** The AI does the heavy lifting, you provide the strategic direction.

## 2. How: The 5-Step Development Lifecycle

This workflow guides you through the entire development process, from initial setup to continuous improvement.

1.  **`0-bootstrap-your-project.md`**: **(One-Time Setup)** The AI analyzes your codebase and builds a foundational "Context Kit" of `READMEs` and project-specific rules.
2.  **`1-create-prd.md`**: The AI acts as a Product Manager, interviewing you to create a detailed Product Requirements Document (PRD).
3.  **`2-generate-tasks.md`**: The AI acts as a Tech Lead, converting the PRD into a granular, step-by-step technical execution plan.
4.  **`3-process-tasks.md`**: The AI acts as a Paired Developer, implementing the plan one task at a time and waiting for your approval at each step.
5.  **`4-implementation-retrospective.md`**: The AI acts as a QA Lead, auditing the work and helping you refine the framework's rules for the future.

## 3. What: Your Practical Guide to Execution

Here’s how to use the protocols to build your next feature.

> **Pro Tip:** For the best results, especially during the PRD and task generation phases, use your AI tool's most powerful model (e.g., **Max Mode** for Cursor users).

### Step 1: Bootstrap Your Project (One-Time Setup)

This is the very first step. It's a one-time protocol that turns a generic AI into a project-specific expert.

```
Apply instructions from @0-bootstrap-your-project.md
```

### Step 2: Create a Product Requirements Document (PRD)

Define the "what" and "why" of your feature.

```
Apply instructions from @1-create-prd.md

Here's the feature I want to build: [Describe your feature in detail]
```

### Step 3: Generate Your Task List

Transform the PRD into a detailed technical plan.

```
Apply instructions from @2-generate-tasks.md to @prd-my-feature.md
```
*(Note: Replace `@prd-my-feature.md` with the actual filename of your PRD.)*

### Step 4: Execute Tasks Sequentially

Instruct the AI to work through the generated plan with full control.

1.  **Start the first task:**
    ```
    Apply instructions from @3-process-tasks.md to @tasks-my-feature.md. Start on task 1.1
    ```
    *(Note: The protocol itself guides the AI for subsequent tasks.)*

2.  **Review and Approve:**
    As the AI completes each task, it will present the changes for your review.
    -   If the changes are correct, reply with **"yes"** or **"continue"**.
    -   If changes are needed, provide corrective feedback.

### Step 5: Conduct a Retrospective

Reflect on the process to make the AI smarter for the next collaboration.

```
Apply instructions from @4-implementation-retrospective.md
```

---

### A Note on the Learning Curve

Your first few interactions with this framework might require more corrections. **This is normal and by design.** You are actively *teaching* the AI the nuances of your codebase. The initial investment pays off exponentially as the AI's context gets richer, its proposals become more accurate, and it evolves into a true expert companion for your project.
