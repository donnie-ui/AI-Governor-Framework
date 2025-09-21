# 🎯 Centralized Review Router

This protocol defines the fallback logic for the review system, ensuring that a generic protocol is used if a custom, stack-specific one is not available.

## Router Logic

The system first checks for a custom protocol within the `custom/` directory. If a matching custom protocol is found, it is used. If not, the system gracefully falls back to the corresponding generic protocol.

### Example Flow: Code Review

1.  **Check for Custom Protocol**: The router looks for `custom/code-review.md`.
2.  **Decision**:
    -   If `custom/code-review.md` exists, it is selected for the review.
    -   If it does not exist, the router selects the generic `code-review.md`.

This ensures that reviews can be tailored to a specific technology stack while maintaining a universal baseline for all projects.

## Protocol-Specific Selection

The same fallback logic applies to all review types:

| Mode            | Custom Protocol (`custom/`) | Generic Fallback         |
| --------------- | --------------------------- | ------------------------ |
| `quick`         | `code-review.md`            | `code-review.md`         |
| `security`      | `security-check.md`         | `security-check.md`      |
| `architecture`  | `architecture-review.md`    | `architecture-review.md` |
| `design`        | `design-system.md`          | `design-system.md`       |
| `ui`            | `ui-accessibility.md`       | `ui-accessibility.md`    |
| `deep-security` | `pre-production.md`         | `pre-production.md`      |

## Implementation Benefits

-   **Centralized Logic**: A single source of truth for the selection algorithm.
-   **Seamless Fallback**: Graceful degradation when custom protocols are unavailable.
-   **Open-Source Ready**: Generic protocols work standalone, while custom protocols provide enhancement.
-   **Maintenance Optimized**: One place to modify the selection logic.