# PROTOCOL: Generic Design System Review

**IMPORTANT**: This protocol is a specialized pointer to the comprehensive quality audit.

**Primary Protocol**: `dev-workflow/4-quality-audit.md`

**Execution Mode**: `design`
- **Layers**: LAYER 5 (Design System)
- **Usage**: For design system compliance validation.

## 1. Design Focus

When applying the comprehensive protocol in `design` mode, focus on:
-   Visual consistency validation.
-   Compliance with the design system.
-   Verification of component usage patterns.
-   Adherence to brand guidelines.

## 2. Review Framework

### 2.1. Design System Compliance (Critical)
**[STRICT] Component Usage:**
-   Use components from the design system exclusively.
-   Respect the defined variants and states of each component.
-   Comply with the established guidelines for spacing and typography.
-   Validate that colors are used according to the defined palette.

**[STRICT] Visual Consistency:**
-   Ensure visual coherence between different modules and services.
-   Respect the established visual hierarchy.
-   Align with existing UI patterns.
-   Validate responsive breakpoints.

### 2.2. Brand Guidelines (High Priority)
**[STRICT] Brand Compliance:**
-   Respect the visual identity (logos, colors, typography).
-   Apply brand guidelines correctly.
-   Ensure a consistent tone of voice in the UI.
-   Comply with all established visual standards.

### 2.3. Component Architecture (Critical)
**[STRICT] Component Boundaries:**
-   Reusable components should be located in a shared library (e.g., `/libs/ui`).
-   Avoid duplicating UI components between services.
-   Respect the abstractions provided by the design system.
-   Maintain a clear separation between presentation and business logic.

### 2.4. Design Token Usage (High Priority)
**[STRICT] Token Compliance:**
-   Use design tokens for colors, spacing, and typography.
-   Avoid hard-coded values in the CSS.
-   Respect the established naming convention for tokens.
-   Ensure consistent use of tokens across all components.

## 3. Review Process

### 3.1. Design System Audit
-   Identify all components used and compare them against the design system.
-   Analyze the compliance of the component variants used.
-   Verify the application of design tokens.
-   Check for overall visual consistency.

### 3.2. Brand Compliance Check
-   Scan the usage of colors and typography.
-   Verify the application of visual guidelines.
-   Check for alignment with the brand identity.
-   Validate the consistency of the visual language.

### 3.3. Component Architecture Review
-   Verify the reusability of components.
-   Check the separation of concerns between UI and business logic.
-   Analyze the organization of the component library.
-   Validate the architecture of the design system itself.

## 4. Communication Style

**[STRICT] Classification:**
-   🚨 **[CRITICAL/BLOCKER]**:
    -   Violation of the design system (e.g., using a custom component instead of a system one).
    -   Non-compliance with brand guidelines.
    -   Duplication of UI components between services.
    -   Ignoring design tokens in favor of hard-coded values.
-   ⚠️ **[IMPROVEMENT]**:
    -   Minor visual inconsistencies.
    -   Possible UX optimizations.
    -   Sub-optimal but functional component usage.
    -   Missing design documentation.
-   💡 **[SUGGESTION]**:
    -   Aesthetic improvements.
    -   Micro-interaction optimizations.
    -   Suggestions for evolving the design system.

## 5. Report Format

```markdown
# Design System Review Report

## Executive Summary
- **Design System Score**: X/10
- **Brand Compliance**: ✅/⚠️/🚨
- **Component Usage**: ✅/⚠️/🚨
- **Visual Consistency**: ✅/⚠️/🚨

## Critical Violations

### 🚨 [File:Line] Title of Violation
- **Rule Violated**: A reference to the specific design system or brand guideline.
- **Issue**: A precise description of the design or brand violation.
- **Impact**: The consequences for consistency and user experience.
- **Fix**: A specific code or design example with ✅ CORRECT and ❌ INCORRECT states.

## Design System Compliance
- **Component Usage**: ✅/⚠️/🚨
- **Design Token Usage**: ✅/⚠️/🚨
- **Brand Guidelines**: ✅/⚠️/🚨
- **Visual Consistency**: ✅/⚠️/🚨

## Priority Recommendations
1.  **[CRITICAL]** Immediate actions to ensure design system compliance.
2.  **[HIGH]** Improvements to align with brand guidelines.
3.  **[MEDIUM]** Optimizations for UI components.
4.  **[LOW]** Aesthetic and UX suggestions.
```