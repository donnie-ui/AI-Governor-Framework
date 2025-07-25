# AI Assistant Rules

This directory contains a set of foundational rules that govern the AI's behavior, thinking process, and operational protocols. They are the constitution of the AI assistant.

The main guide, `0-how-to-create-effective-rules.md`, located at the root of this directory, explains how to create your own well-structured rules.

## Philosophy

These rules are designed to be:
-   **High-Level:** They focus on "how to think" rather than specific implementation details.
-   **Universal:** They are generic and can be applied to almost any software development project.
-   **Actionable:** They provide clear, non-ambiguous instructions.

## Structure

The rules are organized into sub-directories based on their scope and purpose, demonstrating the best practice outlined in `0-how-to-create-effective-rules.md`.

-   **/master-rules/**: Contains foundational, global rules that define the core behavior and safety protocols of the AI assistant. These are designed to be stable and universally applicable.
-   **/common-rules/**: This directory is currently empty. It is intended to hold rules that might be shared across several projects in a monorepo but are not universal enough to be master rules.

## How to Use in Your Project

These rules serve as a "starter kit" to provide a solid foundation for quality, safety, and efficient collaboration. To activate them in your own project using [Cursor](https://cursor.sh/):

1.  **Create the Directory:** At the root of your project, create a hidden directory named `.cursor/rules/`.

2.  **Copy the Rules:** Copy the `master-rules` and `common-rules` sub-directories from this framework into your new `.cursor/rules/` folder.

3.  **Activate the Rules:** This is the most important step. Cursor only recognizes rules with a `.mdc` extension. You **must** rename all the `.md` files you copied to `.mdc`.
    -   *Example: `0-master-rule-create-effective-rules.md` → `0-master-rule-create-effective-rules.mdc`*

4.  **Learn More:** For more details on how Cursor uses rules, refer to the [official documentation](https://docs.cursor.com/context/rules).

You are encouraged to build upon this foundation by creating your own project-specific rules.