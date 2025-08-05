# AI Assistant Rule Governance

This document explains how to organize and govern AI assistant rules. It provides a structured way to codify your project's expert knowledge, ensuring the AI has the *right context* at the *right time*.

The main guide, `0-how-to-create-effective-rules.md`, located in the `master-rules` directory, explains the practical steps for creating your own high-quality rules.

## 🎯 The Purpose: Rules as Codified Context

The core philosophy of this framework is **Context Engineering**. While AI can do incredible things, its effectiveness is limited by the quality of the context it receives. Simply dumping all your codebase files into a prompt is inefficient and expensive.

**Rules are the solution.** They are a formal way to distill and codify critical information that is often unstated:
-   **Architectural Decisions:** *Why* your app is built a certain way.
-   **Best Practices:** The coding patterns that lead to quality and maintainability.
-   **Project Constraints:** The non-negotiable requirements of your tech stack or platform.

By creating a knowledge base of rules, you provide the AI with on-demand, precise context.

### Trust and AI Autonomy

Once this expert context is codified, we must trust the AI to use it intelligently. The system is designed to grant the AI **full autonomy** based on a stable foundation.

-   **Deterministic Boot Sequence:** The AI first loads a minimal, non-negotiable "kernel" (`context-discovery` and `collaboration` rules). This boot process is predictable and safe.
-   **Dynamic Task Context:** From this stable kernel, the AI then:
    -   **Scans Dynamically:** Automatically discovers all available task-specific rules.
    -   **Evaluates Freely:** Independently decides which rules are relevant to the current task.
    -   **Loads Selectively:** Activates only the most useful rules to perform its work.

💡 **Core Principle:** First, we codify our expertise into rules. Then, we trust the AI to apply that expertise, starting from a predictable and secure foundation.

## 📁 Understanding the Rule Structure

The framework organizes rules into three distinct categories based on their scope. This separation is key to maintaining a clear and scalable governance system.

### Strict Placement Rules

Each rule type has a unique, non-negotiable location. The examples below use the recommended `.ai/rules/` path, but **Cursor users MUST replace this with `.cursor/rules/` for the rules to be effective.**

#### ✅ Master Rules (`.ai/rules/master-rules/`)
-   **LOCATION:** Repository root ONLY.
-   **PURPOSE:** To govern the rule system itself and collaboration protocols. These form the AI's "operating system".
-   **EXAMPLES:** `1-master-rule-context-discovery.mdc`, `2-master-rule-ai-collaboration-guidelines.mdc`.

#### ✅ Common Rules (`.ai/rules/common-rules/`)
-   **LOCATION:** Repository root ONLY.
-   **PURPOSE:** To define technical protocols shared across multiple codebases.
-   **EXAMPLES:** Document versioning on cloud storage, shared authentication standards.

#### ✅ Project Rules (`{project-folder}/.ai/rules/project-rules/`)
-   **LOCATION:** Inside each specific project/codebase folder.
-   **PURPOSE:** To contain protocols specific to that project's tech stack.
-   **EXAMPLES:** Rules for Cloudflare Workers, React components, or REST API endpoints.

## 📚 References

Consult the documentation for your specific AI assistant to understand how it discovers and applies context rules.

-   **Cursor:**
    -   [Official Documentation on Rules](https://docs.cursor.com/context/rules)
