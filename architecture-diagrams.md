# Enterprise AI Architecture Diagrams

This document contains high-level Mermaid diagrams for enterprise AI, RAG, agentic AI, and human-in-the-loop workflows.

These diagrams are simplified for public learning and architecture explanation.

---

## 1. Enterprise GenAI Reference Architecture

```mermaid
flowchart TD
    A[User / Business Team] --> B[AI Application Layer]
    B --> C[Orchestration Layer]
    C --> D[Model Access Layer]
    C --> E[Enterprise Knowledge Layer]
    C --> F[Tools and APIs]

    D --> G[LLM / AI Model]
    E --> H[Documents / Databases / Knowledge Bases]
    F --> I[Enterprise Systems]

    C --> J[Governance and Risk Layer]
    J --> K[Logging / Monitoring / Audit]
    J --> L[Human Review]

    G --> M[AI Response]
    H --> M
    M --> L
    L --> N[Final User Output]
```

---

## 2. RAG Architecture Pattern

```mermaid
flowchart TD
    A[User Query] --> B[Query Processing]
    B --> C[Retriever]
    C --> D[Vector Database / Search Index]
    D --> E[Relevant Context]
    E --> F[LLM]
    F --> G[Grounded Answer]
    G --> H[Source References]
    G --> I[User Response]
    G --> J[Monitoring and Feedback]
```

---

## 3. Agentic AI Architecture Pattern

```mermaid
flowchart TD
    A[User Goal] --> B[Agent Planner]
    B --> C[Task Breakdown]
    C --> D[Tool Selection]
    D --> E[Knowledge Retrieval / API / System Action]
    E --> F[Draft Output]
    F --> G[Validation Layer]
    G --> H{Human Approval Needed?}

    H -->|Yes| I[Human Review]
    H -->|No| J[Final Output]

    I --> K{Approved?}
    K -->|Yes| J
    K -->|Edit Needed| F
    K -->|Rejected| L[Stop / Escalate]

    J --> M[Logging and Monitoring]
```

---

## 4. Human-in-the-Loop AI Pattern

```mermaid
flowchart TD
    A[User Request] --> B[AI Analysis]
    B --> C[Draft Output]
    C --> D{Risk Level}

    D -->|Low Risk| E[User Review]
    D -->|Medium Risk| F[Business Review]
    D -->|High Risk| G[Expert Review]

    E --> H[Final Output]
    F --> H
    G --> H

    H --> I[Audit Log / Feedback]
```

---

## Design Principles

Enterprise AI systems should be designed with:

- Clear business value
- Secure data access
- Source-grounded responses
- Human review for high-risk tasks
- Monitoring and auditability
- Governance from the beginning
- Reusable architecture patterns
