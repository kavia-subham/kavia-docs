# Overview

## What is Kavia AI

Kavia AI is an enterprise-first, cross-functional workflow platform that spans the full software development lifecycle — from requirements gathering and design through code generation, testing, scanning, and triage.

Unlike IDE-bound coding assistants that focus narrowly on developer productivity, Kavia AI unifies the entire SDLC into an intelligent, agentic workflow. It serves cross-functional teams — product managers, developers, QA engineers, operations, and managers — within a single platform.

```mermaid
graph LR
    A["Requirements"] --> B["Design"]
    B --> C["Code Generation"]
    C --> D["Testing"]
    D --> E["Scanning"]
    E --> F["Triage"]
    F --> G["CI/CD"]

    style A fill:#ffffff,stroke:#000000,color:#000000
    style B fill:#ffffff,stroke:#000000,color:#000000
    style C fill:#ffffff,stroke:#000000,color:#000000
    style D fill:#ffffff,stroke:#000000,color:#000000
    style E fill:#ffffff,stroke:#000000,color:#000000
    style F fill:#ffffff,stroke:#000000,color:#000000
    style G fill:#ffffff,stroke:#000000,color:#000000
```

## Core Architecture

Kavia AI is powered by two foundational components: the **Enterprise Knowledge Graph** and a **Multi-Agent Orchestrator**.

The Enterprise Knowledge Graph maps relationships between code, documentation, workflows, and business logic. This allows Kavia's multi-agent system to reason across the entire software stack rather than operating on isolated files or snippets.

```mermaid
graph TD
    EKG["Enterprise Knowledge Graph"]
    EKG --- CODE["Source Code"]
    EKG --- DOCS["Documentation"]
    EKG --- WORK["Workflows"]
    EKG --- BIZ["Business Logic"]

    ORCH["Multi-Agent Orchestrator"] --- EKG
    ORCH --- PLAN["Planner Agent"]
    ORCH --- GEN["Code Generator Agent"]
    ORCH --- TEST["Test Agent"]
    ORCH --- SCAN["Scanner Agent"]

    style EKG fill:#ffffff,stroke:#000000,color:#000000
    style CODE fill:#ffffff,stroke:#000000,color:#000000
    style DOCS fill:#ffffff,stroke:#000000,color:#000000
    style WORK fill:#ffffff,stroke:#000000,color:#000000
    style BIZ fill:#ffffff,stroke:#000000,color:#000000
    style ORCH fill:#ffffff,stroke:#000000,color:#000000
    style PLAN fill:#ffffff,stroke:#000000,color:#000000
    style GEN fill:#ffffff,stroke:#000000,color:#000000
    style TEST fill:#ffffff,stroke:#000000,color:#000000
    style SCAN fill:#ffffff,stroke:#000000,color:#000000
```

Source code knowledge graphs are stored inside the repository itself, so each branch carries a version that is accurate with the changes corresponding to that branch. Document knowledge graphs rely on a specialized implementation of agentic retrieval that navigates to the core of a topic efficiently without consuming excessive LLM context.

## Getting Started

Kavia AI is accessible as a web application. To begin:

1. Sign up at the Kavia AI platform.
2. Create or import a project.
3. Connect your repositories, documentation sources, and external tools (GitHub, Jira, Confluence, Bitbucket, CI/CD pipelines).
4. Start working — use Unified Chat, plan generation, or code generation features.

For detailed installation and first-run steps, see the [Quickstart](quickstart.md) guide.

## What You Can Do with Kavia

### Full Project Creation from Prompts or Documents

Kavia can generate a complete project plan — spanning multiple containers and components — from simple prompts or from extensive input documents such as PRDs, BRDs, Figma assets, screenshots, architecture documents, API documents, or meeting notes. Every step in the plan can be auto-generated or interactively refined based on user feedback. Plans can be reviewed and approved by multiple approvers before being handed to Kavia's code generators.

```mermaid
graph LR
    INPUT["Input Documents"] --> PLAN["Project Plan"]
    PLAN --> REVIEW["Review & Approval"]
    REVIEW --> CODEGEN["Code Generation"]

    INPUT --- PRD["PRDs"]
    INPUT --- BRD["BRDs"]
    INPUT --- FIG["Figma Assets"]
    INPUT --- ARCH["Architecture Docs"]
    INPUT --- MEET["Meeting Notes"]

    style INPUT fill:#ffffff,stroke:#000000,color:#000000
    style PLAN fill:#ffffff,stroke:#000000,color:#000000
    style REVIEW fill:#ffffff,stroke:#000000,color:#000000
    style CODEGEN fill:#ffffff,stroke:#000000,color:#000000
    style PRD fill:#ffffff,stroke:#000000,color:#000000
    style BRD fill:#ffffff,stroke:#000000,color:#000000
    style FIG fill:#ffffff,stroke:#000000,color:#000000
    style ARCH fill:#ffffff,stroke:#000000,color:#000000
    style MEET fill:#ffffff,stroke:#000000,color:#000000
```

### Unified Chat

Kavia Unified Chat lets you connect all project-related and external assets through a familiar chat interface. You can:

- Ask Kavia to assess complexity for a new user story.
- Analyze a bug in Jira and surface potential root causes.
- Analyze logs from Datadog sessions.
- Extract screens from a Figma file and implement them.
- Generate documents, perform deep analysis, or trigger code generation — all from the same chat.

### Code Generation

Kavia generates production-ready code that adheres to enterprise standards and best practices, even with basic prompting. The platform automatically incorporates proper error handling, security considerations, documentation, testing frameworks, and architectural patterns. It supports scaffolding for 30+ frameworks, and the DevOps agent can scaffold additional frameworks automatically.

### Testing and QA

Kavia's testing agents handle test-case generation, regression automation, and bug triage. These agents work in context with the knowledge graph, understanding not just the code under test but its relationships to requirements, design decisions, and deployment targets.

### Manager Dashboard

Kavia provides usage dashboards that give managers visibility into team activity — which members have adopted Kavia effectively, which features are heavily used or underutilized, and the results being generated from Kavia sessions. This is critical for enterprise AI rollouts where training and adoption directly impact ROI.

### Enterprise Integrations

Kavia integrates with existing enterprise ecosystems including GitHub, Jira, Confluence, Bitbucket, and CI/CD pipelines, fitting into established workflows without requiring teams to change how they work.