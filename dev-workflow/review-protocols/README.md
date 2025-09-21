# 🔍 Review Protocols

## 1. Philosophy

This directory contains the core logic for AI-driven code reviews. The system is designed with a clear separation of responsibilities to be both flexible and robust.

-   **`review-protocols/`**: Contains the business logic for quality reviews, focusing on architecture, security, and code quality. It includes a set of generic, tool-agnostic protocols.
-   **`review-protocols/custom/`**: An optional directory for project-specific or stack-specific protocols that can override the generic ones.
-   **`dev-workflow/`**: Contains the strategic orchestrators that execute these protocols as part of the development lifecycle.

## 2. Protocol Architecture

### **Main Orchestrators**
-   **`review.md`**: The unified entry point for all reviews. It provides an interactive way to select the desired review protocol.
-   **`../4-quality-audit.md`**: The execution engine that performs the quality audit based on the selected mode.

### **Utilities**
-   **`utils/_review-router.md`**: Provides the logic for falling back from custom to generic protocols.
-   **`utils/context-analyzer.md`**: (Optional) Can be used to analyze file changes to recommend relevant review protocols.

### **Generic Protocols (Always Available)**
These protocols are designed to be universally applicable to any project, regardless of the technology stack.
-   **`code-review.md`**: For quick feedback on code quality and standards compliance.
-   **`security-check.md`**: Focuses on security best practices.
-   **`architecture-review.md`**: Validates architectural integrity and patterns.
-   **`design-system.md`**: Ensures compliance with the project's design system.
-   **`ui-accessibility.md`**: Checks for UI/UX and accessibility issues.
-   **`pre-production.md`**: A comprehensive security check before deployment.

### **Custom Protocols (Optional)**
You can add custom protocols in the `custom/` directory to tailor the review process to your specific stack (e.g., `custom/custom_code-review.md`). If a custom protocol is present, the router will use it instead of the generic equivalent.

## 3. Tool Integration

This review system is designed to be tool-agnostic. To trigger a review, apply the main review orchestrator.

**Generic Command:**
```
Apply instructions from dev-workflow/review-protocols/review.md
```
This will present an interactive selection of the available review protocols.

## 4. Workflow Integration

The review protocols are integrated into the main development workflow:
-   **Protocol 3 (Task Execution)**: After a task is completed, you will be prompted to run a quality review.
-   **Protocol 4 (Quality Audit)**: This protocol is the engine that executes the reviews defined here.

## 5. Adding or Modifying Protocols

### Adding a New Protocol
1.  **Create the Generic Version**: Add a new `[protocol-name].md` file in this directory with the core validation logic.
2.  **(Optional) Create a Custom Version**: If needed, add a `custom/custom_[protocol-name].md` file with stack-specific logic.
3.  **Update the Router**: Add the new protocol to `utils/_review-router.md`.
4.  **Update the Interface**: Add the new option to the `review.md` selection interface.

### Modifying Existing Protocols
-   Modify the generic protocols in this directory for universal changes.
-   Modify or create protocols in the `custom/` directory for project-specific adjustments.

The centralized router ensures that your changes will be automatically picked up by all tools.