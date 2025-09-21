# PROTOCOL: Generic UI/UX & Accessibility Review

**IMPORTANT**: This protocol is a specialized pointer to the comprehensive quality audit.

**Primary Protocol**: `dev-workflow/4-quality-audit.md`

**Execution Mode**: `ui`
- **Layers**: LAYER 6 (UI/UX & Accessibility)
- **Usage**: For UI/UX and accessibility validation.

## 1. UI/UX Focus

When applying the comprehensive protocol in `ui` mode, focus on:
-   WCAG AA+ accessibility compliance.
-   Responsive design validation.
-   Verification of user experience patterns.
-   Consistency of interaction flows.

## 2. Review Framework

### 2.1. Accessibility Compliance (Critical)
**[STRICT] WCAG AA+ Validation:**
-   Color contrast must be at least 4.5:1 for normal text and 3:1 for large text.
-   All interactive elements must be fully navigable with a keyboard.
-   Appropriate ARIA attributes must be used for screen readers.
-   The HTML must have a correct semantic structure (headings, landmarks).
-   All inputs and controls must have explicit labels.

### 2.2. Responsive Design (Critical)
**[STRICT] Breakpoint Validation:**
-   The application must be fully functional on mobile, tablet, and desktop.
-   There should be no unintentional horizontal scrolling.
-   Touch targets must be at least 44x44px on mobile devices.
-   Navigation must be adapted for each viewport.
-   Performance must be maintained across all devices.

### 2.3. User Experience Patterns (High Priority)
**[STRICT] Interaction Consistency:**
-   Interaction patterns must be consistent throughout the application.
-   Visual feedback must be provided for all user actions.
-   Loading, error, and success states must be clearly indicated.
-   Navigation should be intuitive and predictable.

**[STRICT] Cognitive Load Management:**
-   Information should be presented in appropriate chunks.
-   Use progressive disclosure for complex workflows.
-   Labels and instructions must be clear.
-   Provide clear confirmation for destructive actions.

### 2.4. Performance UX (High Priority)
**[STRICT] Loading Experience (Core Web Vitals):**
-   Largest Contentful Paint (LCP) < 2.5s.
-   First Input Delay (FID) < 100ms.
-   Cumulative Layout Shift (CLS) < 0.1.
-   Use progressive loading with skeletons or placeholders.
-   Optimize images and other assets.

## 3. Review Process

### 3.1. Accessibility Audit
-   Scan the HTML markup for semantic compliance.
-   Test for complete keyboard navigation.
-   Automatically check color contrasts.
-   Validate ARIA attributes and labels.
-   Simulate screen readers and other assistive technologies.

### 3.2. Responsive Testing
-   Test on standard breakpoints (e.g., 320px, 768px, 1024px, 1200px+).
-   Validate touch interactions on mobile.
-   Check both portrait and landscape orientations.
-   Control for performance on low-end devices.

### 3.3. UX Flow Validation
-   Trace critical user journeys.
-   Identify friction points and areas of confusion.
-   Validate user feedback at each step.
-   Check error states and recovery paths.
-   Test for edge cases and error scenarios.

## 4. Report Format

```markdown
# UI/UX & Accessibility Review

## Executive Summary
- **Accessibility Score**: X/10 (WCAG AA compliance)
- **Responsive Design**: ✅/⚠️/🚨
- **UX Patterns**: ✅/⚠️/🚨
- **Performance UX**: ✅/⚠️/🚨

## Critical Violations

### 🚨 [File:Line] Title of Violation
- **Standard Violated**: A reference to the specific WCAG guideline or UX best practice.
- **Issue**: A precise description of the accessibility or UX violation.
- **Impact**: The users affected and the consequences.
- **Fix**: A specific code or design example with ✅ CORRECT and ❌ INCORRECT states.

## Accessibility Metrics
- **WCAG AA Compliance**: XX% (target: 100%)
- **Keyboard Navigation**: ✅/⚠️/🚨
- **Screen Reader Support**: ✅/⚠️/🚨
- **Color Contrast Ratio**: X.X:1 (minimum: 4.5:1)

## Performance UX Metrics
- **Largest Contentful Paint**: X.Xs (target: <2.5s)
- **First Input Delay**: XXms (target: <100ms)
- **Cumulative Layout Shift**: X.XX (target: <0.1)

## Priority Recommendations
1.  **[CRITICAL]** Immediate actions to ensure WCAG AA compliance.
2.  **[HIGH]** Optimizations for responsive design.
3.  **[MEDIUM]** Improvements to UX patterns.
4.  **[LOW]** Performance and micro-interaction suggestions.
```