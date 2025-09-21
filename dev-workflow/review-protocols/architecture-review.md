# PROTOCOL: Generic Architecture-Focused Validation

**IMPORTANT**: This protocol is a specialized pointer to the comprehensive quality audit.

**Primary Protocol**: `dev-workflow/4-quality-audit.md`

**Execution Mode**: `architecture`
- **Layers**: LAYER 1 (Architectural Design) + LAYER 4 (Architecture & Performance)
- **Usage**: For major architectural changes or a deep architecture review.

## 1. Architecture Focus

When applying the comprehensive protocol in `architecture` mode, focus on the following areas:
-   Validation of modular design and separation of concerns.
-   Analysis of inter-service communication patterns.
-   Assessment of performance, scalability, and resilience.
-   Verification of architectural pattern consistency.

## 2. Mission

To validate the architectural integrity, modularity, and established patterns in a modern, multi-service application.

## 3. Core Architectural Principles

### 3.1. Modular Design (Critical)
**[STRICT] Validation:**
-   Each module or service should correspond to a unique business domain.
-   The physical separation of code (in different directories) must respect the logical design.
-   A consistent and ubiquitous language for domain concepts should be used throughout the code.
-   Data and the behaviors that operate on that data should be kept together.

**[STRICT] Physical Separation:**
-   Services should be located in a dedicated `services/` (or equivalent) directory.
-   Public-facing entrypoints (like UIs or gateways) should be in an `apps/` directory.
-   Shared, reusable code should be in a `libs/` directory.
-   Direct imports between services are an anti-pattern and should be flagged.

### 3.2. Inter-Module Communication (Critical)
**[STRICT] API Contracts:**
-   Synchronous communication must occur exclusively through well-defined, stable interfaces (APIs).
-   Direct calls to internal functions of another module are an anti-pattern.
-   Each service must have a clearly defined public interface or contract.

**[STRICT] Asynchronous Communication:**
-   Use message queues or an event bus for decoupled, event-based communication.
-   Event producers and consumers should be explicitly configured.
-   Use fire-and-forget patterns for non-critical, asynchronous operations.

### 3.3. Performance and Resilience
**[STRICT] Performance Optimization:**
-   Minimize service startup time by managing dependencies carefully.
-   Implement strategic caching where appropriate.
-   Optimize the bundle or binary size for each service.
-   Use resilience patterns like circuit breakers for calls to external or volatile services.

### 3.4. Clean Architecture (Optional but Recommended)
**[GUIDELINE] Ports & Adapters Pattern:**
-   Isolate business logic from infrastructure concerns (e.g., databases, frameworks).
-   Use interfaces (ports) to define the boundary of the business logic.
-   Implement technology-specific details in adapters.
-   This keeps the core business logic pure and highly testable.

## 4. Validation Framework

### 4.1. Architectural Analysis
The audit should produce a report covering:
-   **Module Identification**: A list of the identified modules and their responsibilities.
-   **Language Compliance**: Any violations of the ubiquitous language.
-   **Domain Model Quality**: An assessment of how well data and behavior are co-located.
-   **Boundary Integrity**: Whether module boundaries are respected.
-   **Communication Compliance**: Whether inter-service communication follows the defined patterns.

### 4.2. Architectural Anti-Patterns to Detect
-   **Anemic Domain Model**: Classes that contain only data, with business logic handled elsewhere in services.
-   **Monolithic Module**: A single, massive module that is not properly decomposed.
-   **Chaotic Communication**: Direct calls between internal components of different modules, bypassing public APIs.
-   **Leaky Abstractions**: Implementation details of one module being exposed to another.

## 5. Report Format

```markdown
# Architecture Audit Report

## Executive Summary
- **Architectural Score**: 85/100
- **Modules**: 4 identified, 3 compliant
- **Service Communication**: ⚠️ 2 direct call violations detected
- **Code Quality**: ✅ Compliant with standards

## Critical Architectural Violations

### 🚨 Module Boundary Violation
**File**: `services/billing/src/user-service.ts:15`
**Issue**: Direct import from the `auth` service.
**Impact**: Creates tight coupling and violates module isolation.
**Fix**: Use shared types from a `libs/shared-types` directory.
```typescript
// ❌ INCORRECT
import { User } from '../../../auth/src/models/user';

// ✅ CORRECT
import { User } from '@shared/types/user';
```

### 🚨 Improper Service Communication  
**File**: `apps/gateway/src/api/users.ts:42`
**Issue**: Direct call to an internal service function instead of using the public API contract.
**Impact**: Degrades performance and creates tight coupling.
**Fix**: Use the defined service interface.
```typescript
// ❌ INCORRECT - Direct call
const response = await userService.getUserDirectly(userId);

// ✅ CORRECT - Interface contract
const user = await this.userServiceContract.getUser(userId);
```

## Architectural Health
### ✅ Strengths Identified
-   Modules are well-separated physically.
-   The ubiquitous language is respected in the `auth` and `billing` services.
-   The overall modular structure is well-defined.

### ⚠️ Areas for Improvement
-   Address the two direct-call violations.
-   Add documentation for the identified modules.
-   Improve integration testing between modules.

### 📊 Architectural Metrics
| Metric | Score | Target |
|----------|-------|-----------|
| Module Isolation | 85% | >90% |
| API Contract Usage | 70% | 100% |
| Ubiquitous Language | 92% | >90% |

## Priority Recommendations
1. **[CRITICAL]** Eliminate direct calls between services.
2. **[CRITICAL]** Refactor direct imports between services.
3. **[HIGH]** Add missing `try/catch` blocks around I/O operations.
4. **[MEDIUM]** Complete the documentation for all modules.