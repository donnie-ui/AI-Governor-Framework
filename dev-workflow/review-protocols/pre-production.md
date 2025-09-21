# PROTOCOL: Generic Deep Security Audit

**IMPORTANT**: This protocol is a specialized pointer to the comprehensive quality audit.

**Primary Protocol**: `dev-workflow/4-quality-audit.md`

**Execution Mode**: `deep-security`
- **Layers**: LAYER 2 (Security), LAYER 1 (Architectural Design), and LAYER 7 (Testing)
- **Usage**: For a deep security analysis, compliance audit, or comprehensive security validation before production.

## 1. Deep Security Focus

When applying the comprehensive protocol in `deep-security` mode, focus on:
-   A complete multi-tenant security validation (if applicable).
-   A vulnerability assessment with confidence scoring.
-   An analysis of security testing coverage.
-   Verification of compliance status against relevant standards.

## 2. Mission

To conduct a comprehensive security evaluation for a modern, multi-service application, with a focus on authentication, data protection, and distributed systems security.

## 3. Security Framework

### 3.1. Module Security (Critical)
**[STRICT] Context Isolation:**
-   Each module or service must manage its own authentication.
-   Secrets must not be shared between contexts.
-   Secure communication protocols must be used for inter-service communication.
-   Input validation must be performed at the boundary of each context.

**[STRICT] Secure Error Handling:**
-   All authentication and authorization operations must be wrapped in `try/catch` blocks.
-   Logs must be scrubbed of sensitive data.
-   Authorization error handling should be consistent.
-   Error messages should not reveal sensitive information to external users.

### 3.2. Secure Service Communication (Critical)
**[STRICT] Secure Communication:**
-   API contracts must be used to avoid direct exposure of internal functions.
-   Parameters must be validated at every service boundary.
-   Service-to-service authentication must be implemented via secure interfaces.
-   Internal methods must not be exposed via public endpoints.

### 3.3. Secure Code Quality (Critical)
**[STRICT] Security Standards:**
-   Input validation with guard clauses is mandatory for all endpoints.
-   Use secure naming conventions (e.g., do not expose variables named `password` or `secret`).
-   Authentication functions should be kept short (<30 lines) for auditability (SRP).
-   Nesting depth should be limited (<3 levels) to avoid security bugs in complex logic.

### 3.4. Multi-Tenant Security (High Priority, if applicable)
**[STRICT] Data Isolation:**
-   Row-Level Security (RLS) is mandatory for all tenant-scoped tables.
-   A `tenant_id` must be validated with every database operation.
-   There must be no data leakage between tenants.
-   A complete audit trail for cross-tenant access is required.

**[STRICT] Security Architecture:**
-   Implement defense-in-depth at every layer (Client → Gateway → Service → DB).
-   Authentication should be handled at the gateway, with authorization handled by each service.
-   Secrets management must be isolated by business context.
-   Secure monitoring of inter-service communications should be in place.

## 4. Vulnerability Assessment Categories

### 4.1. Authentication & Session Management
-   Weak JWT validation.
-   Session fixation vulnerabilities.
-   Insecure password reset flows.
-   Missing multi-factor authentication.
-   Flaws in OAuth implementation.

### 4.2. Injection Attacks
-   SQL injection in database queries.
-   NoSQL injection patterns.
-   Command injection in services.
-   XSS in user-generated content.

### 4.3. Data Exposure
-   Sensitive data in logs.
-   Information disclosure in database error messages.
-   Data leaks in API responses.
-   Client-side credential exposure.
-   Insecure direct object references.

### 4.4. Security Misconfiguration
-   Weak CORS policies.
-   Missing security headers.
-   Exposed debug endpoints.
-   Default or weak configurations.
-   Over-privileged service accounts.

## 5. Report Format

```markdown
# Security Audit Report

## Executive Summary
- **Security Score**: 72/100 ⚠️
- **Critical Vulnerabilities**: 3
- **High-Risk Issues**: 7  
- **Compliance Status**: Partial

## 🚨 Critical Findings (Immediate Action Required)

### CVE-2024-XXXXX: SQL Injection in User Query
- **File**: `services/core/src/api/users.ts:45`
- **Severity**: HIGH (9.2/10)
- **Confidence**: 0.95
- **Vector**: Unsanitized user input in a dynamic query.
- **Exploit**: `'; DROP TABLE users; --`
- **Impact**: Complete database compromise.
- **Fix**: Use parameterized queries with an ORM client.
```sql
-- Vulnerable
const { data } = await db.raw('SELECT * FROM users WHERE name = ' + userInput); // UNSAFE

-- Fixed  
const { data } = await db.from('users').select('*').where('name', userInput); // SAFE
```

### Missing Row-Level Security: Cross-Tenant Data Access
- **Table**: `billing_invoices`
- **Severity**: HIGH (9.0/10)
- **Confidence**: 1.0
- **Impact**: Users can access other tenants' billing data.
- **Exploit**: A direct API call with a modified `tenant_id`.
- **Fix**: Implement a row-level security policy immediately.
```sql
ALTER TABLE billing_invoices ENABLE ROW LEVEL SECURITY;

CREATE POLICY "Users can only see their own tenant's invoices" 
ON billing_invoices
FOR ALL USING (tenant_id = current_setting('app.current_tenant_id'));
```

## ⚠️ High-Risk Issues

### Hardcoded API Keys in Configuration
- **Files**: `apps/gateway/.env.example`, `services/auth/config.ts`
- **Severity**: MEDIUM (7.5/10)
- **Impact**: Service compromise if the keys are real.
- **Fix**: Move the keys to a secure environment variable management system.

## 🔍 Security Recommendations

### Immediate (This Sprint)
1.  Fix SQL injection vulnerabilities.
2.  Implement missing row-level security policies.
3.  Remove hardcoded credentials.
4.  Enable MFA for admin accounts.

### Short-term (Next Sprint)
1.  Implement comprehensive audit logging.
2.  Add rate limiting to all public endpoints.
3.  Complete the security header configuration.
4.  Set up dependency vulnerability monitoring.