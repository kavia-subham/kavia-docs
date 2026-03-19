# Model Configuration

Kavia AI provides flexibility in how LLMs are used across the platform. Organizations can use Kavia's default models, bring their own, or run models in customer-hosted environments.

## Default Models Provided by Kavia

Kavia ships with a curated set of default LLMs optimized for different stages of the SDLC. These models are pre-configured and require no setup — they work out of the box for all Kavia features including code generation, test generation, planning, and analysis.

```mermaid
graph TD
    KAVIA["Kavia Platform"] --> DEFAULT["Default Models"]
    KAVIA --> BYOM["Bring Your Own Models"]
    KAVIA --> HOSTED["Customer-Hosted Models"]

    DEFAULT --> TASK["Task-Optimized Routing"]
    BYOM --> TASK
    HOSTED --> TASK

    TASK --> PLAN["Planning"]
    TASK --> CODE["Code Generation"]
    TASK --> TEST["Testing"]
    TASK --> ANALYSIS["Analysis"]

    style KAVIA fill:#ffffff,stroke:#000000,color:#000000
    style DEFAULT fill:#ffffff,stroke:#000000,color:#000000
    style BYOM fill:#ffffff,stroke:#000000,color:#000000
    style HOSTED fill:#ffffff,stroke:#000000,color:#000000
    style TASK fill:#ffffff,stroke:#000000,color:#000000
    style PLAN fill:#ffffff,stroke:#000000,color:#000000
    style CODE fill:#ffffff,stroke:#000000,color:#000000
    style TEST fill:#ffffff,stroke:#000000,color:#000000
    style ANALYSIS fill:#ffffff,stroke:#000000,color:#000000
```

Kavia's multi-agent orchestrator selects the appropriate model for each task based on complexity, latency requirements, and the nature of the operation.

## Bring Your Own Models (BYOM)

Kavia allows developers and organizations to select LLMs from several providers, including open-source models or custom models set up by the customer. Supported options include:

- **Commercial LLM providers** — Connect models from providers such as OpenAI, Anthropic, Google, and others.
- **Open-source LLMs** — Use self-hosted open-source models (e.g., Llama, Mistral, Code Llama).
- **Custom fine-tuned models** — Bring models that have been fine-tuned on your organization's data or domain.

These models can optionally run in the customer's own hosted environment, ensuring that no data leaves the organization's infrastructure.

```mermaid
graph LR
    ORG["Your Organization"] --> HOSTED_ENV["Customer-Hosted Environment"]
    HOSTED_ENV --> MODEL["Your LLM"]
    MODEL --> KAVIA["Kavia Platform"]
    KAVIA --> OUTPUT["Results"]

    style ORG fill:#ffffff,stroke:#000000,color:#000000
    style HOSTED_ENV fill:#ffffff,stroke:#000000,color:#000000
    style MODEL fill:#ffffff,stroke:#000000,color:#000000
    style KAVIA fill:#ffffff,stroke:#000000,color:#000000
    style OUTPUT fill:#ffffff,stroke:#000000,color:#000000
```

## Recommendations from Kavia

When selecting models, Kavia recommends:

- **For high-complexity tasks** (architecture generation, multi-file refactoring, deep analysis) — use larger, more capable models that can handle extended context and multi-step reasoning.
- **For routine tasks** (formatting, simple test generation, boilerplate scaffolding) — use smaller, faster models to optimize for speed and cost.
- **For compliance-sensitive environments** — use customer-hosted models to ensure all data processing stays within your organization's boundaries.

Kavia's orchestrator can automatically route tasks to the most appropriate model when multiple models are configured, balancing capability, latency, and cost.
