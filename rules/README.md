# AI Assistant Rule Governance

This document explains how to organize and govern AI assistant rules. It provides a structured way to codify your project's expert knowledge, ensuring the AI has the *right context* at the *right time*.

This framework is designed to be flexible, supporting both single-project repositories and complex monorepos, and is compatible with any modern AI development assistant.

The main guide, `0-how-to-create-effective-rules.md`, located at the root of this directory, explains the practical steps for creating your own high-quality rules.

## 🎯 The Purpose: Rules as Codified Context

The core philosophy of this framework is **Context Engineering**. While AI can do incredible things, its effectiveness is limited by the quality of the context it receives. Simply dumping all your codebase files into a prompt is inefficient and expensive.

**Rules are the solution.** They are a formal way to distill and codify critical information that is often unstated:
-   **Architectural Decisions:** *Why* your app is built a certain way.
-   **Best Practices:** The coding patterns that lead to quality and maintainability.
-   **Project Constraints:** The non-negotiable requirements of your tech stack or platform.

By creating a knowledge base of rules, you provide the AI with on-demand, precise context.

### Trust and AI Autonomy

Once this expert context is codified, we must trust the AI to use it intelligently. The system is designed to grant the AI **full autonomy** to work optimally. It can:

-   **Scan Dynamically:** Automatically discover all available rules.
-   **Evaluate Freely:** Independently decide which rules are relevant to the current task.
-   **Load Selectively:** Activate only the most useful rules to perform its work.

💡 **Core Principle:** First, we codify our expertise into rules. Then, we trust the AI to apply that expertise.

## 📁 Understanding the Rule Structure

The framework organizes rules into three distinct categories based on their scope. This separation is key to maintaining a clear and scalable governance system.

### Strict Placement Rules

Each rule type has a unique, non-negotiable location. The examples below use the recommended `.ai/rules/` path, but **Cursor users MUST replace this with `.cursor/rules/` for the rules to be effective.**

#### ✅ Master Rules (`.ai/rules/master-rules/`)
-   **LOCATION:** Repository root ONLY.
-   **PURPOSE:** To govern the rule system itself and collaboration protocols.
-   **EXAMPLES:** How to create rules, naming conventions, conflict resolution, code development directives.

#### ✅ Common Rules (`.ai/rules/common-rules/`)
-   **LOCATION:** Repository root ONLY.
-   **PURPOSE:** To define technical protocols shared across multiple codebases.
-   **EXAMPLES:** Document versioning on cloud storage, shared authentication standards.

#### ✅ Project Rules (`{project-folder}/.ai/rules/project-rules/`)
-   **LOCATION:** Inside each specific project/codebase folder.
-   **PURPOSE:** To contain protocols specific to that project's tech stack.
-   **EXAMPLES:** Rules for Cloudflare Workers, React components, or REST API endpoints.

## 📚 References

Consult the documentation for your specific AI assistant to understand how it discovers and applies context rules. Below are some examples for popular tools.

-   **Cursor:**
    -   [Official Documentation on Rules](https://docs.cursor.com/context/rules)
    
-   **Other Tools:**
    -   Refer to the documentation for tools like Claude Code, Windsurf, cline, etc., for instructions on providing context.