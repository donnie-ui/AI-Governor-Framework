# The Governor Workflow: From Idea to Production

## 1. Why: A Structured Workflow for Predictable Results

Working with AI can sometimes feel unpredictable. The AI Governor Framework provides a development workflow designed to fix that, for both new and existing projects.

It provides a structured, sequential process that transforms your AI from a simple code generator into a reliable engineering partner. By following these protocols, you ensure that both you and the AI are always aligned, moving from a high-level idea to a well-implemented feature with clarity, control, and consistency.

The goal is to make AI-powered development:
-   **Predictable:** Each step has a clear purpose and output.
-   **Controllable:** You are always in the loop for key decisions.
-   **Efficient:** The AI does the heavy lifting, while you provide the strategic direction.

## 2. How it Works: The 5-Protocol Development Lifecycle

This workflow guides you through the entire development process, from initial setup to continuous improvement. Each protocol assigns a specific role to the AI, ensuring a structured and predictable collaboration with intelligent session management.

### Step 0: Bootstrap Your Project (One-Time Setup)
**Role:** The AI acts as a **Project Analyst**.

First, the AI analyzes your entire codebase to build a "Context Kit"—a set of foundational `READMEs` and project-specific rules. This is a one-time protocol that turns a generic AI into a project-specific expert.

```
Apply instructions from dev-workflow/0-bootstrap-your-project.md
```

### Step 1: Create a Product Requirements Document (PRD)
**Role:** The AI acts as a **Product Manager**.

Next, you define the "what" and "why" of your feature. The AI interviews you to create a detailed Product Requirements Document (PRD), ensuring all requirements are captured before any code is written.

```
Apply instructions from dev-workflow/1-create-prd.md

Here's the feature I want to build: [Describe your feature in detail]
```

### Step 2: Generate Your Task List
**Role:** The AI acts as a **Tech Lead**.

The AI then transforms the PRD into a granular, step-by-step technical execution plan. This ensures that both you and the AI are aligned on the implementation strategy.

```
Apply instructions from dev-workflow/2-generate-tasks.md to @prd-my-feature.md
```
*(Note: Replace `@prd-my-feature.md` with the actual filename of your PRD.)*

### Step 3: Execute Tasks with Integrated Quality Gates
**Role:** The AI acts as a **Paired Developer** with built-in quality validation.

Here, the AI implements the plan one parent task at a time, within a dedicated chat session. Each session includes implementation, a quality audit, and a retrospective for optimal context preservation.

**🔄 Per Parent Task (New Chat Session):**

1.  **Start a parent task in a fresh session:**
    ```
    Apply instructions from dev-workflow/3-process-tasks.md to @tasks-my-feature.md. Start on task 1.
    ```
    *(Note: Replace `@tasks-my-feature.md` with the actual filename of your task list.)*

2.  **Implementation with Quick Reviews:**
    - The AI implements sub-tasks with integrated validation.
    - You review and approve the changes by replying with **"yes"** or **"continue"**.

3.  **Protocol 4: Unified Quality Review (Same Session)**
    Once the parent task is complete, use the unified review system:
    
    ```
    Apply instructions from dev-workflow/review-protocols/review.md
    ```
    *(Note for Cursor and Claude Code users: you can simply type `/review` to trigger this protocol.)*
    
    This protocol acts as an interactive menu. Based on your selection, it will trigger the powerful `4-quality-audit.md` protocol to perform the actual review. It will present you with the following options:
    - ☐ **Code Review**
    - ☐ **Comprehensive Review**
    - ☐ **Security Check**
    - ☐ **Architecture Review**
    - ☐ **Design System Compliance**
    - ☐ **UI/UX & Accessibility**
    
    Alternatively, if you know which review mode you need, you can call the audit protocol directly:
    ```
    Apply instructions from dev-workflow/4-quality-audit.md --mode security
    ```
    
4.  **Protocol 5: Implementation Retrospective (Same Session)**
    Capture learnings while the context is fresh:
    ```
    Apply instructions from dev-workflow/5-implementation-retrospective.md
    ```

5.  **Start the next parent task in a new chat:**
    ```
    Apply instructions from dev-workflow/3-process-tasks.md to @tasks-my-feature.md. Start on task 2.
    ```

---

### A Note on the Streamlined Workflow

This 5-protocol workflow with a unified review system is designed to be tool-agnostic and efficient. Key improvements include:

- **Fewer steps** with a single, unified review interface.
- **Tool-agnostic design** that works across different AI development environments.
- **Context optimization** through intelligent session management.
- **Interactive selection** for reviews, preventing tool-specific confusion.
- **6-layer validation** including Design and UX coverage.

The initial structured approach pays off exponentially as the AI learns your codebase patterns and becomes a true expert companion for your project, delivering predictable, high-quality output.
