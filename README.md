# AI Dev Assistant Framework

A pragmatic, plug-and-play governance framework for AI-assisted software development. It is designed to work with any modern AI coding assistant, from IDE-integrated tools like [Cursor](https://cursor.sh/) and GitHub Copilot to conversational agents like Claude. This framework transforms AI collaborators from simple code generators into structured, context-aware engineering partners.

It provides a set of structured Markdown files—protocols and rules—that guide an AI through the entire development lifecycle, from initial codebase analysis to continuous improvement.

---

## 🌟 The Philosophy: From Prompting to Governing

Standard AI prompting is chaotic. It lacks structure, context, and a feedback loop, often leading to inconsistent results and time-consuming rework.

This framework shifts the paradigm from **prompting** to **governing**. Instead of asking an AI to "build a feature," you instruct it to follow a battle-tested **workflow**. The AI's role evolves:

-   From a simple coder to an **Architect** who analyzes your codebase.
-   From a task executer to a **Tech Lead** who creates a detailed technical plan.
-   From an uncontrolled generator to a **Paired Developer** who awaits your approval at every key step.
-   From a one-shot tool to a **QA Lead** who helps you improve the process itself.

By providing the AI with a clear "operating system," you ensure the code it produces is not only functional but also architecturally sound, consistent with your project's standards, and highly maintainable.

## 🚀 The "Companion Expert" Workflow

This framework is designed to turn your AI assistant into a **companion expert** that learns and grows with your project. The workflow is simple:

1.  **Bootstrap Your Project (One-Time Setup):** Run the `0-bootstrap-your-project.md` protocol. The AI will analyze your codebase and work with you to create a foundational "Context Kit" of `READMEs` and project-specific rules.
2.  **Develop Features:** Use the main 4-step development workflow (starting with `1-create-prd.md`) to create or modify features. The AI will now be significantly more accurate because it uses the context you built together.
3.  **Evolve the Context:** With each feature you build, the AI will get smarter. Use the `4-implementation-retrospective.md` protocol to identify gaps and continuously enrich your project's rules and documentation.

### A Note on the First Run: The Learning Curve

Your first few interactions with the AI using this framework might require more corrections and clarifications. **This is normal and by design.** You are actively *teaching* the assistant the specific nuances of your codebase.

Think of it as onboarding a new junior developer. The initial investment in teaching pays off exponentially. With each iteration, the AI's context gets richer, its proposals become more accurate, and it evolves from a generic tool into a true expert companion for your project.

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