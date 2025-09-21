# PROTOCOL: Generic Quick Code Review

**IMPORTANT**: This protocol is a specialized pointer to the comprehensive quality audit.

**Primary Protocol**: `dev-workflow/4-quality-audit.md`

**Execution Mode**: `quick`
- **Layers**: LAYER 1 (Architectural Design) + LAYER 3 (Code Quality)
- **Usage**: After each sub-task implementation for quick feedback.

## 1. Quick Review Focus

When applying the comprehensive protocol in `quick` mode, focus on:
-   Architectural compliance validation.
-   Code quality standards checks.
-   Verification of inter-service communication patterns.
-   Module and boundary integrity.

## 2. Review Framework

### 2.1. Architectural Principles (Critical)
**[STRICT] Modular Design:**
-   Verify that new code is placed in the correct module or service.
-   Ensure the physical separation of concerns (`services/`, `apps/`, `libs/`) is respected.
-   Check for a consistent naming convention (ubiquitous language).
-   Flag any direct imports between logically separate services.

### 2.2. Service Communication (Critical)
**[STRICT] Inter-Module Communication:**
-   API contracts MUST be used for synchronous communication.
-   Direct calls to internal functions of other modules are FORBIDDEN.
-   Verify that each service exposes a clear, well-defined interface.

### 2.3. Code Quality (Critical)
**[STRICT] Error Handling:**
-   All I/O operations MUST be wrapped in `try/catch` blocks or equivalent.
-   `catch` blocks must contain meaningful logging, not be empty.
-   Use guard clauses for input validation at the beginning of functions.

**[STRICT] Naming & Structure:**
-   Use explicit variable names (`userList` vs. `data`).
-   Use prefixes like `is`, `has`, `can` for boolean variables.
-   Functions should be short and follow the Single Responsibility Principle (SRP).
-   Nesting depth should be limited to a maximum of 3 levels.

### 2.4. Security (High Priority)
**[STRICT] Data Isolation:**
-   For multi-tenant applications, data access policies (like RLS) must be in place.
-   A `tenant_id` (or equivalent) must be validated with every database operation.
-   Secrets must be managed per-context and not shared.

### 2.5. Performance (High Priority)
**[STRICT] Platform-Specific Optimization:**
-   Be mindful of cold start times.
-   Optimize bundle or binary sizes.
-   Implement caching where appropriate.
-   Use resilience patterns like circuit breakers.

## 3. Review Process

### 3.1. Context Discovery
-   Identify the modules or services affected by the changes.
-   Analyze any changes to module boundaries.
-   Verify that the separation of concerns is maintained.

### 3.2. Service Communication Validation
-   Scan for direct calls between modules (anti-pattern).
-   Verify that API contracts are being used correctly.

### 3.3. Code Quality Review
-   Check for proper error handling.
-   Review naming, structure, and complexity (SRP, nesting).
-   Validate input handling and guard clauses.

## 4. Communication Style

**[STRICT] Classification:**
-   🚨 **[CRITICAL/BLOCKER]**:
    -   Violation of module boundaries (e.g., direct import between services).
    -   Direct calls between internal components of different modules.
    -   I/O operations without error handling.
-   ⚠️ **[IMPROVEMENT]**:
    -   Functions longer than 30 lines (SRP violation).
    -   Nesting depth greater than 3 levels.
    -   Missing documentation.
-   💡 **[SUGGESTION]**:
    -   Minor optimizations.
    -   Suggestions for improving clarity.
    -   Performance micro-optimizations.

## 5. Report Format

```markdown
# Code Review Report

## Executive Summary
- **Architectural Score**: X/10
- **Module Boundaries**: ✅/⚠️/🚨
- **Service Communication**: ✅/⚠️/🚨
- **Code Quality**: ✅/⚠️/🚨

## Critical Violations

### 🚨 [File:Line] Title of Violation
- **Rule Violated**: A reference to the specific rule or principle.
- **Issue**: A precise description of the violation.
- **Impact**: The consequences for the architecture, security, or performance.
- **Fix**: A code snippet with ✅ CORRECT and ❌ INCORRECT examples.

## Architectural Compliance
- **Module Integrity**: ✅/⚠️/🚨
- **Service Communication**: ✅/⚠️/🚨
- **Code Quality Standards**: ✅/⚠️/🚨

## Priority Recommendations
1.  **[CRITICAL]** Immediate actions to ensure compliance with standards.
2.  **[HIGH]** Architectural improvements.
3.  **[MEDIUM]** Optimizations for communication patterns.
4.  **[LOW]** Suggestions for performance or style.
```