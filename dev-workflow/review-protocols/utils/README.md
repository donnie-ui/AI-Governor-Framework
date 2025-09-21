# 🔧 Review Protocol Utilities

## 🎯 Purpose

This `utils/` folder contains utility components that support the review protocols, enabling dynamic analysis and context-aware rule application.

## 📁 Components

- **`context-analyzer.md`**: Provides git change analysis to inform protocol selection.
- **`rule-injection-system.md`**: Filters and applies relevant rules based on the analysis context.
- **`_review-router.md`**: Contains centralized fallback logic for protocol selection.
- **`enhanced-static-validation.md`**: A framework for testing and validating the review utilities.

## 🚀 Integration

These utilities are primarily used by the main orchestrator protocols:
- `../review.md`
- `../4-quality-audit.md`