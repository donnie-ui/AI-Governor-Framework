# PROTOCOL: Generic Security-Focused Audit

**IMPORTANT**: This protocol is a specialized pointer to the comprehensive quality audit.

**Primary Protocol**: `dev-workflow/4-quality-audit.md`

**Execution Mode**: `security`
- **Layers**: LAYER 2 (Security) + LAYER 1 (Architectural Design)
- **Usage**: For authentication/data changes, compliance checks, and security validation.

## 1. Security Focus

When applying the comprehensive protocol in `security` mode, focus on:
-   Multi-tenant data protection validation (if applicable).
-   Security isolation of modules.
-   Secure configuration of inter-service communication.
-   Input validation and authentication patterns.

## 2. Security Audit Framework

### 2.1. Module Security (Critical)
**[STRICT] Secure Isolation:**
-   Each module or service must manage its own authentication.
-   Secrets must not be shared between contexts.
-   Input validation must be performed at every context boundary.
-   Error handling must be secure and comply with established standards.

**[STRICT] Secure Inter-Module Communication:**
-   API contracts must be used for all communication; no direct internal calls.
-   Service-to-service authentication must be implemented via secure interfaces.
-   Parameters must be validated at every boundary.
-   Internal methods must not be exposed via public endpoints.

### 2.2. Secure Code Quality (Critical)
**[STRICT] Security Standards:**
-   Input validation with guard clauses is MANDATORY.
-   All authentication operations must have `try/catch` error handling.
-   Use secure naming conventions (do not expose variables like `password` or `secret`).
-   Authentication functions should be short (<30 lines) for auditability (SRP).
-   Nesting depth should be limited (<3 levels) to avoid complex security bugs.

### 2.3. Multi-Tenant Security (Critical, if applicable)
**[STRICT] Data Isolation:**
-   Row-Level Security (RLS) policies are MANDATORY for all tenant-scoped tables.
-   A `tenant_id` must be validated with every database operation.
-   A complete audit trail for cross-tenant access is required.
-   There must be no data leakage between tenants.

**[STRICT] Security Architecture:**
-   Implement defense-in-depth (Client → Gateway → Service → DB).
-   Centralize authentication, but distribute authorization to each context.
-   Isolate secrets management by business context.
-   Securely monitor inter-service communications.

## 3. Vulnerability Categories

### 3.1. Module Security Violations
-   Direct import of secrets between services.
-   Shared authentication logic between contexts.
-   Logs containing sensitive cross-context data.
-   Insecure communication between modules.

### 3.2. Service Communication Security Issues
-   Direct calls between internal components of different modules.
-   Interfaces without access validation.
-   Configuration with exposed secrets.
-   Methods without input validation.

### 3.3. Input Validation & Injection
-   SQL injection in database queries.
-   XSS in user-generated content.
-   Command injection in services.
-   NoSQL injection patterns.

### 3.4. Configuration Security
-   Overly permissive CORS policies.
-   Weak or missing security headers.
-   Exposed debug endpoints in production.
-   Hard-coded secrets in the codebase.

## 4. Report Format

```markdown
# Security Audit Report

## Executive Summary
- **Security Score**: X/10
- **Module Security**: ✅/⚠️/🚨
- **Service Communication Security**: ✅/⚠️/🚨
- **Code Quality Security**: ✅/⚠️/🚨

## Critical Vulnerabilities (High Confidence >0.8)

### 🚨 CRITICAL [File:Line] Title of Vulnerability
- **Category**: Module Security Violation
- **Rule Violated**: A reference to a specific rule or standard.
- **Vulnerability**: A precise description with context.
- **Exploit Scenario**: How an attacker could exploit the vulnerability.
- **Business Impact**: The impact on tenants, data, or the system.
- **Fix**: Specific code examples.
```typescript
// ❌ INCORRECT - Standard Violation
const user = await database.users.find(userId); // Without try/catch

// ✅ CORRECT - Standard Compliant
try {
  const user = await database.users.find(userId);
  if (!user) {
    console.error(`User lookup failed: ${userId}`);
    return null;
  }
  return user;
} catch (error) {
  console.error('Database error:', error.message);
  throw new AuthenticationError('User validation failed');
}
```
- **Confidence**: 0.95

## Security Compliance
- **Module Isolation**: ✅/⚠️/🚨
- **Secure Service Communication**: ✅/⚠️/🚨
- **Multi-Tenant Data Protection**: ✅/⚠️/🚨
- **Secure Code Quality**: ✅/⚠️/🚨

## Priority Recommendations
1.  **[CRITICAL]** Fix critical security vulnerabilities immediately.
2.  **[HIGH]** Implement missing secure communication patterns.
3.  **[MEDIUM]** Complete multi-tenant security policies.
4.  **[LOW]** Optimize defense-in-depth patterns.