---
description: "TAGS: [global,workflow,context,rules,discovery] | TRIGGERS: rule,context,understand,project,setup | SCOPE: global | DESCRIPTION: Defines the systematic process an AI assistant must follow to discover and select relevant rules and context before starting any task."
alwaysApply: true
---
# Master Rule: Context Discovery Protocol

## 1. Systematic Rule Discovery Process

Before executing any code or command, the Agent **MUST** imperatively follow these steps to build its operational context.

### Step 1: Full Inventory
**Action:** The AI must have a way to list all available rule files (e.g., `.md` or `.mdc` files in a `.cursor/rules` directory). This can be done via `find` or by reading from a cached list.

**Goal:** To create an exhaustive list of all rule files present in the entire repository, regardless of their location (`master-rules`, `common-rules`, `project-rules`).

### Step 2: Intelligent Contextual Analysis
FOR EACH RULE FOUND:

1.  **Attempt to Parse Metadata:** Read the YAML frontmatter block (the part between `---`).
2.  **If Metadata Exists and is Well-Formed:**
    *   Use the `description` string to extract `TAGS`, `TRIGGERS`, and `SCOPE`.
    *   Proceed to Step 3 to evaluate relevance based on this rich, structured data.
3.  **If Metadata is Missing or Malformed (Fallback Protocol):**
    *   To control costs and latency, you **MUST NOT** read the entire file.
    *   You **MUST** read only the first ~15 lines of the file (enough to get the title and the first paragraph).
    *   You **MUST** infer the rule's purpose from its title (`# Rule Name`) and its first few sentences.
    *   Proceed to Step 3 to evaluate relevance based on this limited, inferred context.

### Step 3: Weighted Relevance Evaluation Algorithm
The AI Agent **MUST** use the following weighted algorithm to assess the relevance of each rule:

1.  **Level 1: Absolute Directives (`alwaysApply`)**
    *   Any rule with `alwaysApply: true` is automatically selected. This is the highest level of priority.

2.  **Level 2: Scope Matching (`SCOPE`)**
    *   If the rule's `SCOPE` (e.g., `My-UI-App`) directly matches the current working directory or the user's explicit request, its relevance score is significantly boosted.

3.  **Level 3: Keyword Matching (`TRIGGERS`)**
    *   If the user's prompt contains keywords from the rule's `TRIGGERS` list (e.g., "test," "component," "api"), its relevance score is increased.

4.  **Level 4: Concept Matching (`TAGS`)**
    *   If the rule's `TAGS` (e.g., `[quality]`, `[security]`) align with the general intent of the task, its relevance score gets a minor boost. This is the most "fuzzy" level of matching.

### Step 4: Report and Application
**Action:** Based on the relevance scores calculated above, select the top 2-5 most relevant rules. Announce them to the user clearly and concisely.
> *"I have loaded the `{rule-name-1}` and `{rule-name-2}` rules, which cover {relevant_domain} for your request. I am ready to begin."*

---

## 🏷️ Standardized Tagging System (For Metadata)

This system is key to discoverability.

### Mandatory Format for ALL Rules
```yaml
---
description: "TAGS: [tag1,tag2] | TRIGGERS: keyword1,keyword2 | SCOPE: scope | DESCRIPTION: use when..."
alwaysApply: false
---
```

### Standard Tags by Domain (Examples)

#### **🌍 GLOBAL TAGS** (Master Rules)
- `global`: Rule applies everywhere
- `collaboration`: AI-user interaction protocols
- `quality`: Code quality standards
- `documentation`: Docs/markdown management
- `workflow`: Work processes

#### **🔧 BACKEND TAGS** 
- `backend`: General backend
- `api`: APIs (REST, GraphQL)
- `database`: Databases and migrations
- `auth`: Authentication and security
- `deployment`: Deployment and CI/CD
- `testing`: Backend testing

#### **🌐 FRONTEND TAGS**
- `frontend`: User interface
- `component`: UI Components
- `form`: Forms and validation
- `styling`: CSS, theming, responsive design
- `api-calls`: API calls from the frontend

#### **🗄️ INFRASTRUCTURE TAGS**
- `storage`: Object storage (S3, R2, etc.)
- `cache`: Caching strategies
- `cdn`: CDN and performance
- `monitoring`: Monitoring and logging

---

## 🧠 Contextual Intelligence

### Detecting the Working Context
The AI Agent **MUST** analyze:

1.  The **current working directory** (`pwd`) to identify the project.
2.  **Keywords** from the user's request to match triggers.
3.  The **type of operation** (creation, modification, debug, deployment).
4.  The **files concerned** to understand the technology.

### Monorepo Dependency Mapping (Example)
Understand the relationships to load related rules.
> *Example: "If the task is on the UI, also load relevant rules for the microservices it calls."*

---

## 🧠 Communication & Flexibility

### Natural Communication
-   **DO:** Announce the loaded rules in a simple and useful way.
    > *"I've loaded the `quality-standards` and `api-rest-conventions` rules to help with your request. I'm ready to start!"*
-   **DON'T:** Do not list technical scores, the full scanning process, or complex file names. The focus should be on the value added, not the mechanism.

### Flexibility & Continuous Adaptation
-   **If you are unsure** about a rule's relevance, it's better to load it than to miss an important context.
-   **If the user mentions a new technology** or context during the task, dynamically search for rules related to it.
-   **Learn from feedback** to improve future selections. 