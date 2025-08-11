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

## 3. Quick Start: Installation & Activation

This guide provides a safe, non-destructive process to integrate the framework into any project.

### Option 1: For a New Project (Recommended)
The simplest way to start. Click the green **"Use this template"** button on the main repository page. This creates a new repository for you, pre-loaded with The Governor Framework, ready for the bootstrap protocol.

### Option 2: For an Existing Project
This process safely integrates the framework's components into their correct locations.

1.  **Download the Framework Blueprints:**
    First, get the framework's files by cloning them into a temporary folder.
    ```bash
    git clone https://github.com/Fr-e-d/The-Governor-Framework.git temp-governor
    ```

2.  **Copy the Components to Your Project:**
    The next step depends on your primary AI assistant.

    #### For Cursor Users (Recommended)
    Cursor needs the rules in a specific `.cursor` directory for automatic detection. The workflows can be placed in a separate directory for clarity.
    ```bash
    # 1. Create the mandatory directory for rules
    mkdir -p .cursor/rules

    # 2. Copy the framework's rule sets (this is safe and will not overwrite your personal rules)
    cp -r temp-governor/rules/master-rules .cursor/rules/
    cp -r temp-governor/rules/common-rules .cursor/rules/

    # 3. Create a separate directory for the manual workflows
    mkdir governor-workflows

    # 4. Copy the workflows into it
    cp -r temp-governor/dev-workflow governor-workflows/
    ```

    #### For Other AI Assistants
    For other tools, you can place all components inside a single `.ai-governor` directory for simplicity.
    ```bash
    # 1. Create a single directory for the framework
    mkdir .ai-governor

    # 2. Copy the rules and workflows into it
    cp -r temp-governor/rules .ai-governor/
    cp -r temp-governor/dev-workflow .ai-governor/
    ```
    *You can now safely delete the temporary `temp-governor` folder.*

### Activating the Governor: The Bootstrap Protocol
Once the framework files are in your project, you need to activate the Governor by running the bootstrap protocol.

Open your project in your editor and give your AI assistant the correct path to the protocol:
```bash
# For Cursor Users:
Apply instructions from governor-workflows/dev-workflow/0-bootstrap-your-project.md

# For Other Users:
Apply instructions from .ai-governor/dev-workflow/0-bootstrap-your-project.md
```

## 4. What: Your Practical Guide to Execution

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
