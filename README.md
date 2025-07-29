# AI Dev Agent Framework

A pragmatic, plug-and-play governance framework for AI-assisted software development. It is designed to work with any modern AI coding Agent, from IDE-integrated tools like [Cursor](https://cursor.sh/) and GitHub Copilot to conversational agents like Claude Code. This framework excels in complex, multi-codebase monorepos, transforming AI agents from simple code generators into structured, context-aware engineering partners.

It provides a set of structured Markdown files—protocols and rules—that guide an AI through the entire development lifecycle, from initial codebase analysis to continuous improvement.


## 🌟 The Philosophy: Context is King

Working with AI agents reveals one core truth: **Context is King.** 👑

However, "context" isn't just about dumping more data into the prompt. In complex codebases, that approach is inefficient and prohibitively expensive. 💸

True **Context Engineering** is a strategy. It’s about giving the AI the *right* information, at the *right* time. This framework is built on four core principles to achieve that:

1️⃣ **Decompose Complexity:** Break big features into small, focused tasks to improve AI accuracy.

2️⃣ **Enable Targeted Access:** Build a knowledge base of rules & `READMEs` for precise, on-demand context.

3️⃣ **Keep Humans in the Loop:** Supervise the AI like a brilliant junior developer and validate at key checkpoints.

4️⃣ **Evolve Context Continuously:** Treat context as a living system that grows with your code and makes the AI smarter over time.

This framework shifts the paradigm from simple **prompting** to strategic **governing**, transforming any AI Agent into a true "Companion Expert" that understands your project's unique standards.

---

## 🗂️ Framework Structure

-   **`/dev-workflow/`**: Contains the sequential protocols that guide the development process. See the `README.md` in this directory for detailed instructions.
-   **`/rules/`**: Contains a starter kit of foundational "Master Rules" that govern the AI's behavior and thinking process.

---

## 🚀 Workflow at a Glance

The AI will guide you through the following phases. For detailed instructions on steps 0-4, please refer to the [`/dev-workflow/README.md`](dev-workflow/README.md).

---

### 0️⃣ **`0-bootstrap-your-project.md`**
-   **Phase:** 0 (One-Time Setup)
-   **Role:** AI Codebase Analyst & Context Architect
-   **Why:** To build a shared knowledge base that turns a generic AI into a project-specific expert.
-   **Goal:** To analyze a codebase and create a foundational "Context Kit" of `READMEs` and project-specific rules.

---

### 1️⃣ **`1-create-prd.md`**
-   **Phase:** 1 (Feature Definition)
-   **Role:** AI Product Manager
-   **Why:** To clarify the "what" and "why," ensuring the feature fits the existing architecture before any code is written.
-   **Goal:** To transform a user request into a detailed Product Requirements Document (PRD).

---

### 2️⃣ **`2-generate-tasks.md`**
-   **Phase:** 2 (Technical Planning)
-   **Role:** AI Tech Lead
-   **Why:** To decompose complexity into small, manageable tasks, dramatically improving AI accuracy and predictability.
-   **Goal:** To convert the PRD into a step-by-step technical execution plan in a markdown checklist format.

---

### 3️⃣ **`3-process-tasks.md`**
-   **Phase:** 3 (Controlled Implementation)
-   **Role:** AI Meticulous Task Executor
-   **Why:** To ensure a high-quality, controlled implementation by executing tasks sequentially with human-in-the-loop validation.
-   **Goal:** To implement the feature by systematically completing each task from the plan, producing code that is validated at each step.

---

### 4️⃣ **`4-implementation-retrospective.md`**
-   **Phase:** 4 (Continuous Improvement)
-   **Role:** AI Code Auditor & Framework Refiner
-   **Why:** To create a continuous improvement loop where each new feature makes the AI smarter and refines the framework for the future.
-   **Goal:** To audit the implemented code against existing rules, and then to identify and propose concrete improvements to the framework's protocols and rules.


## ❤️ Support This Project

This framework is offered freely to the community. If you find it valuable and it has helped you improve your AI-assisted development workflow, please consider showing your support. It is greatly appreciated!

-   **[Sponsor on GitHub](https://github.com/sponsors/Fr-e-d)**

## 🤝 Attribution & License

This framework is an enhanced and structured adaptation inspired by the foundational work on AI-driven development by [snarktank/ai-dev-tasks](https://github.com/snarktank/ai-dev-tasks).

It is shared under the **Apache 2.0 License**. See the `LICENSE` file for more details. For contribution guidelines, please see `CONTRIBUTING.md`. 