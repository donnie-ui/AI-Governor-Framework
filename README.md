# AI-Powered Development Protocols Framework

A pragmatic, plug-and-play governance framework for AI-assisted software development. It is designed to work with any modern AI coding assistant, from IDE-integrated tools like [Cursor](https://cursor.sh/) and GitHub Copilot to conversational agents like Claude. This framework transforms AI collaborators from simple code generators into structured, context-aware engineering partners.

It provides a set of structured Markdown protocols that guide an AI through the entire development lifecycle: from robust requirement gathering and architectural planning to controlled execution and continuous improvement.

---

## 🌟 The Philosophy: From Prompting to Governing

Standard AI prompting is chaotic. It lacks structure, context, and a feedback loop, often leading to inconsistent results and time-consuming rework.

This framework shifts the paradigm from **prompting** to **governing**. Instead of asking an AI to "build a feature," you instruct it to follow a battle-tested **workflow**, where each step is a formal protocol. The AI's role evolves:

-   From a simple coder to a **Product Manager** who asks the right questions.
-   From a task executer to a **Tech Lead** who creates a detailed technical plan.
-   From an uncontrolled generator to a **Paired Developer** who awaits your approval at every key step.
-   From a one-shot tool to a **QA Lead** who helps you improve the process itself.

By providing the AI with a clear "operating system," you ensure the code it produces is not only functional but also architecturally sound, consistent with your project's standards, and highly maintainable.

## 🚀 Quick Start & Onboarding Guide (Plug & Play)

Integrating this framework into your project is designed to be simple.

### 1. **Copy the Framework**
   - Copy the `ai-protocol-framework` folder (or just its contents) into the root of your repository. You can rename the folder to whatever you like (e.g., `.ai-protocols`, `ai_governance`).

### 2. **Review and Adapt the Protocols**
   - The protocols inside `protocols/` are designed to be generic. Open each file and look for placeholders like `"[Your Frontend App]"` or `@[your-rule-name]`.
   - **Adapt the placeholders** to match your project's specific terminology, architecture, and file paths. This is the most crucial step to contextualize the AI.

### 3. **(Optional but Recommended) Create Your `@rules`**
   - This framework is most powerful when combined with a `.cursor/rules` directory containing specific rules for your codebase (e.g., coding style, API usage patterns).
   - The protocols will instruct the AI to consult these `@rules`, giving it deep, project-specific context.
   - To get you started, this repository includes an `ai-assistant-rules/` directory. It contains a collection of high-level, generic "master rules" that you can copy into your own `.cursor/rules/master-rules/` folder and adapt. It also includes a guide on how to write effective rules yourself.

### 4. **Start the Workflow**
   - You're ready to go! Start a new conversation with your AI assistant (e.g., Cursor) and kick off the workflow by referencing the first protocol.

   **Example First Prompt:**
   ```
   Please use the protocol defined in @ai-protocol-framework/protocols/1-create-prd.md.

   I want to build a new feature: [Describe your feature, its goal, and its target users].
   ```

   The AI will take over, following the protocol to guide you through the rest of the process.

## 🗺️ The 4-Step Development Workflow

This framework is built around a sequential, four-protocol workflow which is stored in the `dev-workflow/` directory. It is complemented by a set of foundational rules, located in the `rules/` directory, that govern the AI's behavior.

---

### 1️⃣ **Phase 1: Product Requirement Document (PRD) Creation**
   - **Protocol:** `1-create-prd.md`
   - **AI Role:** Product Manager
   - **Outcome:** A clear specification document (`.md`) that defines *what* to build and, crucially, *where* it fits within your existing architecture (e.g., Frontend, Backend Service, API Layer).

---

### 2️⃣ **Phase 2: Technical Task Generation**
   - **Protocol:** `2-generate-tasks.md`
   - **AI Role:** Tech Lead
   - **Outcome:** A detailed, step-by-step technical plan in a checklist format (`.md`) that breaks down the PRD into actionable tasks for development.

---

### 3️⃣ **Phase 3: Task Processing (`3-process-tasks.md`)**

-   **Protocol:** `3-process-tasks.md`
-   **AI Role:** Paired Developer
-   **Outcome:** The feature is implemented task by task, with the AI pausing for your explicit approval at each critical checkpoint, ensuring you remain in full control.

---

### 4️⃣ **Phase 4: Implementation Retrospective**

-   **Protocol:** `4-implementation-retrospective.md`
-   **AI Role:** QA & Process Improvement Lead
-   **Outcome:** A collaborative review of the development process to identify bottlenecks or ambiguities. This phase generates concrete suggestions for improving the protocols or your project's `@rules`, creating a powerful continuous improvement loop.

---

## ❤️ Support This Project

This framework is offered freely to the community. If you find it valuable and it has helped you improve your AI-assisted development workflow, please consider showing your support. It is greatly appreciated!

-   **[Sponsor on GitHub](https://github.com/sponsors/Fr-e-d)**

## 🤝 Attribution & License

This framework is an enhanced and structured adaptation inspired by the foundational work on AI-driven development by [snarktank/ai-dev-tasks](https://github.com/snarktank/ai-dev-tasks).

It is shared under the **Apache 2.0 License**. See the `LICENSE` file for more details. For contribution guidelines, please see `CONTRIBUTING.md`. 