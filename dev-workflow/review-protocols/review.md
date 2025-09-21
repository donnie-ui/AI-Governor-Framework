# PROTOCOL: Review Orchestrator

## 1. Mission

This protocol serves as the unified entry point for all quality reviews. It provides an interactive interface for selecting one or more review protocols to execute. It can be enhanced with context-aware recommendations based on an analysis of the changes.

## 2. Smart Context Analysis (Optional)

Before presenting the selection, you can optionally analyze the recent changes to provide intelligent recommendations.

```bash
# Analyze git changes for context...
DETECTED_CONTEXT=$(analyze-git-changes)
RECOMMENDATIONS=$(generate-smart-suggestions $DETECTED_CONTEXT)
```

## 3. Protocol Selection

Based on the analysis, you can present smart recommendations to the user before showing the full list of protocols.

### Smart Recommendations (Context-Driven Example)
-   🎯 **HIGH CONFIDENCE**: Based on changes to authentication and security files, a **Security Check** and **Pre-Production Security** review are recommended.
-   💡 **SUGGESTED**: You may also want to run a **Code Review** to check for general quality standards.

---

### ☐ **Code Review** - Mode: `quick`
**Usage**: For quick feedback during the development iteration cycle.
**Focus**: Code quality and standards compliance.

### ☐ **Comprehensive Review** - Mode: `comprehensive`
**Usage**: For a complete quality validation before a merge or release.
**Focus**: All quality layers, with intelligent prioritization.

### ☐ **Security Check** - Mode: `security`
**Usage**: For security compliance validation.
**Focus**: Security best practices and module boundaries.
**When to use**: After changes to authentication, authorization, or data handling.

---

### ☐ **Architecture Review** - Mode: `architecture`
**Usage**: For validating architectural changes or refactoring.
**Focus**: Architectural integrity, performance, and scalability.
**When to use**: After major architectural changes.

---

### ☐ **Design System Compliance** - Mode: `design`
**Usage**: For ensuring visual consistency and adherence to brand guidelines.
**Focus**: Design token usage and component library standards.
**When to use**: After changes to UI components or the design system.

---

### ☐ **UI/UX & Accessibility** - Mode: `ui`
**Usage**: For validating the user experience and accessibility.
**Focus**: Accessibility standards (WCAG), cross-device usability, and UX patterns.
**When to use**: After changes to the user experience or accessibility-related features.

---

### ☐ **Pre-Production Security** - Mode: `deep-security`
**Usage**: For a comprehensive security validation before a production deployment.
**Focus**: A complete security validation, including testing.
**When to use**: Before deploying to production or for a focused security analysis.

---

## 4. AI Execution Instructions

Based on the user's selection, execute the `4-quality-audit.md` protocol with the corresponding mode.

### Single Protocol Selection
```bash
# Example if the user selects "Security Check":
Apply instructions from dev-workflow/4-quality-audit.md --mode security
```

### Multiple Protocol Selection  
```bash
# Execute the selected protocols in an optimal order. For example:
# 1. Code Review (for quick feedback)
# 2. Security Check
# 3. Architecture Review 
# 4. Design System Compliance
# 5. UI/UX & Accessibility
# 6. Pre-Production Security (usually last)

# Example if the user selects "Code Review" and "Security Check":
Apply instructions from dev-workflow/4-quality-audit.md --mode quick
Apply instructions from dev-workflow/4-quality-audit.md --mode security
```

### Comprehensive Selection
```bash
# If "Comprehensive Review" is selected:
Apply instructions from dev-workflow/4-quality-audit.md --mode comprehensive
```

## 5. Protocol Selection Logic

The orchestrator uses the centralized router (`dev-workflow/review-protocols/utils/_review-router.md`) which automatically:

1.  **Detects** if a `custom/` directory exists.
2.  **Selects** the appropriate protocol (custom → generic fallback).
3.  **Executes** the review via the `4-quality-audit.md` orchestrator.
4.  **Reports** the results in a unified format.

## 6. Report Format

```markdown
# Quality Review Results

## Selected Protocols
- ✅ Code Review - Score: 8.5/10
- ✅ Security Check - Score: 9.2/10  
- ⏭️ Architecture Review (skipped)
- ⏭️ Design System Compliance (skipped)
- ⏭️ UI/UX & Accessibility (skipped)
- ⏭️ Pre-Production Security (skipped)

## Executive Summary
- **Overall Quality Score**: 8.9/10
- **Critical Issues**: 0 🟢
- **High Priority Issues**: 2 🟡
- **Recommendations**: 5 💡

## Next Steps
1.  Address the high-priority issues.
2.  Consider running an Architecture Review due to recent service changes.
3.  Schedule a Design System Compliance check if UI components were modified.
```