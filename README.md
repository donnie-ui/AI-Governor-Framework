# AI Dev Agent Framework

A pragmatic, plug-and-play governance framework for AI-assisted software development. It is designed to work with any modern AI coding Agent, from IDE-integrated tools like [Cursor](https://cursor.sh/) and GitHub Copilot to conversational agents like Claude. This framework excels in complex, multi-codebase monorepos, transforming AI agents from simple code generators into structured, context-aware engineering partners.

It provides a set of structured Markdown files—protocols and rules—that guide an AI through the entire development lifecycle, from initial codebase analysis to continuous improvement.

---

## 🌟 The Philosophy: Context is King

Working with AI agents reveals one core truth: **Context is King.** 👑

However, "context" isn't just about dumping more data into the prompt. In complex codebases, that approach is inefficient and prohibitively expensive. 💸

True **Context Engineering** is a strategy. It’s about giving the AI the *right* information, at the *right* time. This framework is built on four core principles to achieve that:

1️⃣ **Decompose Complexity:** Break big features into small, focused tasks to improve AI accuracy.

2️⃣ **Enable Targeted Access:** Build a knowledge base of rules & `READMEs` for precise, on-demand context.

3️⃣ **Keep Humans in the Loop:** Supervise the AI like a brilliant junior developer and validate at key checkpoints.

4️⃣ **Evolve Context Continuously:** Treat context as a living system that grows with your code and makes the AI smarter over time.

This framework shifts the paradigm from simple **prompting** to strategic **governing**, transforming any AI Agent into a true "Companion Expert" that understands your project's unique standards.

## 🚀 Your "Codebase Expert Agent" Workflow: From Idea to Flawless Feature

This structured workflow guides you and your AI Agent from a high-level concept to a fully implemented and compliant feature. Each step uses a specific protocol from the `/dev-workflow/` directory.

*(Note: The examples below use the `@` syntax to reference the protocol files. Depending on your AI tool, you may need to provide the full path, e.g., `@ai-dev-assistant-framework/dev-workflow/1-create-prd.md`)*

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

## 🗂️ Framework Structure

-   **`/dev-workflow/`**: Contains the sequential protocols that guide the development process from idea to retrospective.
-   **`/rules/`**: Contains a starter kit of foundational "Master Rules" that govern the AI's behavior and thinking process.

---

## ❤️ Support This Project

This framework is offered freely to the community. If you find it valuable and it has helped you improve your AI-assisted development workflow, please consider showing your support. It is greatly appreciated!

-   **[Sponsor on GitHub](https://github.com/sponsors/Fr-e-d)**

## 🤝 Attribution & License

This framework is an enhanced and structured adaptation inspired by the foundational work on AI-driven development by [snarktank/ai-dev-tasks](https://github.com/snarktank/ai-dev-tasks).

It is shared under the **Apache 2.0 License**. See the `LICENSE` file for more details. For contribution guidelines, please see `CONTRIBUTING.md`. 