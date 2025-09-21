# TEMPLATE: Custom Review Protocol

## 🎯 Template Structure

Use this template to create custom, stack-specific review protocols (`custom_*.md`).

### **Header Template**
```markdown
# PROTOCOL: Custom [PROTOCOL_NAME] for [TECHNOLOGY_STACK]

## Context-Aware Review

**Approach**: This protocol combines a reliable static review foundation with intelligent, stack-specific targeting for [TECHNOLOGY_STACK].

**Execution Mode**: `[MODE]`
- **Layers**: [SPECIFIC_LAYERS]
- **Usage**: [SPECIFIC_USAGE] with context-aware analysis.

## 🧠 Context Analysis

**Intelligence**: This protocol can be enhanced by analyzing git changes for stack-specific patterns:

```typescript
interface CustomContext {
  customServices: boolean;     // e.g., changes in a specific service directory
  frameworkIntegration: boolean; // e.g., changes related to a specific framework
  customConfig: boolean;       // e.g., changes to stack-specific configuration
  [SPECIFIC_CONTEXT]: boolean; // protocol-specific context
}
```

**Smart Recommendations**: 
- **[CONTEXT_1]** → [RECOMMENDATION_1]
- **[CONTEXT_2]** → [RECOMMENDATION_2]

## 🎯 Stack-Specific Validation

### **Rule Injection**

Based on the detected context, prioritize relevant validation rules:

**Critical Rules (Always Apply)**:
- **Master Rule: Error Handling**
- **Master Rule: Code Quality** 
- **Project Rule: [Your Critical Project Rule]**

**Context-Triggered Rules**:
- **[PROTOCOL_CONTEXT]** → [SPECIFIC_RULES]
- **[TECHNOLOGY_STACK] Context** → [Stack-specific performance or security rules]

**Execution Instructions**:
1.  **Execute Critical Rules First**
2.  **Apply Context-Triggered Rules**
3.  **Skip Irrelevant Checks**
4.  **Focus on**: [FOCUS_AREAS]

## 📋 Static Protocol Framework

### **Layer X: [PROTOCOL_LAYER]**

[EXISTING_GENERIC_PROTOCOL_CONTENT_ENHANCED_WITH_STACK_SPECIFICS]
```

### **Footer Template**
```markdown
---

## 🚀 Benefits of Custom Protocols

**🎯 Context-Aware Intelligence:**
- **More efficient** reviews through stack-specific rule filtering.
- **Smart recommendations** based on your project's patterns.
- **Targeted validation** focusing on [PROTOCOL_FOCUS].

**🛡️ Proven Reliability + Custom Intelligence:**
- A **static protocol foundation** ensures comprehensive validation coverage.
- **Enhanced with context analysis** for intelligent targeting of custom patterns.
- **Graceful degradation** to static validation when context analysis fails.
```

## 📋 Protocol-Specific Mappings (Examples)

### **custom_security-check.md**
-   PROTOCOL_NAME: "Security Check"
-   MODE: "security"
-   SPECIFIC_LAYERS: "LAYER 2 (Security) + LAYER 1 (Architectural Design)"
-   PROTOCOL_CONTEXT: "Security Context"
-   SPECIFIC_RULES: "Authentication, authorization, secrets management"
-   FOCUS_AREAS: "API security, data validation, access control"

### **custom_architecture-review.md**
-   PROTOCOL_NAME: "Architecture Review"
-   MODE: "architecture"
-   SPECIFIC_LAYERS: "LAYER 1 (Architectural Design) + LAYER 4 (Architecture & Performance)"
-   PROTOCOL_CONTEXT: "Architecture Context"
-   SPECIFIC_RULES: "Modular design, inter-service communication, scalability"
-   FOCUS_AREAS: "Module boundaries, API contracts, performance patterns"