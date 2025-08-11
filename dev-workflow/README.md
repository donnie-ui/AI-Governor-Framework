# The Governor Workflow: From Idea to Production

## 1. Why: A Structured Workflow for Predictable Results

Working with AI can sometimes feel unpredictable. The Governor Framework provides a development workflow designed to fix that, for both new and existing projects.

It provides a structured, sequential process that transforms your AI from a simple code generator into a reliable engineering partner. By following these five protocols, you ensure that both you and the AI are always aligned, moving from a high-level idea to a well-implemented feature with clarity, control, and consistency.

The goal is to make AI-powered development:
-   **Predictable:** Each step has a clear purpose and output.
-   **Controllable:** You are always in the loop for key decisions.
-   **Efficient:** The AI does the heavy lifting, you provide the strategic direction.

## 2. How it Works: The 5-Step Development Lifecycle

This workflow guides you through the entire development process, from initial setup to continuous improvement. Each step assigns a specific role to the AI, ensuring a structured and predictable collaboration.

### Step 0: Bootstrap Your Project (One-Time Setup)
**Role:** The AI acts as a **Project Analyst**.

First, the AI analyzes your entire codebase to build a "Context Kit"—a set of foundational `READMEs` and project-specific rules. This is a one-time protocol that turns a generic AI into a project-specific expert.

```
Apply instructions from .ai-governor/dev-workflow/0-bootstrap-your-project.md
```
*(For best results, Cursor users should use Max Mode for this step.)*

### Step 1: Create a Product Requirements Document (PRD)
**Role:** The AI acts as a **Product Manager**.

Next, you define the "what" and "why" of your feature. The AI interviews you to create a detailed Product Requirements Document (PRD), ensuring all requirements are captured before any code is written.

```
Apply instructions from .ai-governor/dev-workflow/1-create-prd.md

Here's the feature I want to build: [Describe your feature in detail]
```
*(For best results, Cursor users should use Max Mode for this step.)*

### Step 2: Generate Your Task List
**Role:** The AI acts as a **Tech Lead**.

The AI then transforms the PRD into a granular, step-by-step technical execution plan. This ensures that both you and the AI are aligned on the implementation strategy.

```
Apply instructions from .ai-governor/dev-workflow/2-generate-tasks.md to @prd-my-feature.md
```
*(Note: Replace `@prd-my-feature.md` with the actual filename of your PRD.)*

*(For best results, Cursor users should use Max Mode for this step.)*

### Step 3: Execute Tasks Sequentially
**Role:** The AI acts as a **Paired Developer**.

Here, the AI implements the plan one task at a time, presenting the changes for your approval at each step. This gives you full control over the code while delegating the heavy lifting.

1.  **Start the first task:**
    ```
    Apply instructions from .ai-governor/dev-workflow/3-process-tasks.md to @tasks-my-feature.md. Start on task 1.1
    ```
    *(Note: The protocol itself guides the AI for subsequent tasks.)*

2.  **Review and Approve:**
    As the AI completes each task, it will present the changes for your review.
    -   If the changes are correct, reply with **"yes"** or **"continue"**.
    -   If changes are needed, provide corrective feedback.

### Step 4: Conduct a Retrospective
**Role:** The AI acts as a **QA Lead**.

Finally, the AI helps you audit the completed work and reflect on the process. This is where you refine the framework's rules, making the AI smarter and more aligned for the next collaboration.

```
Apply instructions from .ai-governor/dev-workflow/4-implementation-retrospective.md
```

## 3. Quick Start: Installation

This guide provides a safe, non-destructive process to integrate the framework into any project.

**1. Clone the Framework**

Open a terminal at the root of your project and run the following command:
```bash
git clone https://github.com/Fr-e-d/The-Governor-Framework.git .ai-governor
```
This downloads the entire framework into a hidden `.ai-governor` directory within your project.

**2. Configure for Your Assistant**

The final step depends on your AI assistant:

#### For Cursor Users
Cursor requires rules to be in a specific `.cursor` directory to load them automatically. Run this command to copy them:
```bash
mkdir -p .cursor/rules && cp -r .ai-governor/rules/master-rules .cursor/rules/
```
The workflows are ready to be used from the `.ai-governor/dev-workflow` directory.

#### For Other AI Assistants
No extra steps are needed. The framework is ready to use. You can point your assistant to the rules and workflows inside the `.ai-governor` directory.

---

### A Note on the Learning Curve

Your first few interactions with this framework might require more corrections. **This is normal and by design.** You are actively *teaching* the AI the nuances of your codebase. The initial investment pays off exponentially as the AI's context gets richer, its proposals become more accurate, and it evolves into a true expert companion for your project.
