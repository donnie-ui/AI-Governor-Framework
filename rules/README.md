# AI Assistant Rules

This directory contains a set of foundational rules that govern the AI's behavior, thinking process, and operational protocols.

The main guide, `0-how-to-create-effective-rules.md`, located at the root of this directory, explains the philosophy and structure for creating your own high-quality rules.

## Structure

The rules are organized into sub-directories based on their scope and purpose, demonstrating the best practice outlined in the main guide.

-   **/master-rules/**: Contains foundational, global rules that define the core behavior and safety protocols of the AI assistant.
-   **/common-rules/**: Intended for rules that might be shared across several projects but are not universal enough to be master rules.
-   **/project-rules/**: **This is the most important category.** These rules are specific to a single codebase (e.g., a UI app, a microservice) and live inside that project's `.cursor/rules/` directory. They define the unique architectural and coding conventions of your project.

## How to Use in Your Project

To activate these rules in your project using an assistant like [Cursor](https://cursor.sh/):

1.  **Create the Core Directory:** At the root of your project, create a hidden directory named `.cursor/rules/`.

2.  **Copy the Starter Kit:** Copy the `master-rules` and `common-rules` sub-directories from this framework into your new `.cursor/rules/` folder.

3.  **Create Your Project Rules:** This is where you'll get the most value. Inside your specific codebase (e.g., `my-app/`), create your own rules directory: `my-app/.cursor/rules/project-rules/`. Start adding rules that define your project's standards.

4.  **Activate the Rules:** Cursor only recognizes rules with a `.mdc` extension. You **must** rename all the `.md` files you copied or created to `.mdc`.

5.  **Learn More:** For more details on how Cursor uses rules, refer to the [official documentation](https://docs.cursor.com/context/rules).