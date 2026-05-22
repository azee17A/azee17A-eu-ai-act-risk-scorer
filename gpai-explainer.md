# General Purpose AI (GPAI) Models — EU AI Act Explainer

**Source**: Regulation (EU) 2024/1689, Articles 51–55 and Recitals 97–110

---

## What is a GPAI Model?

A General Purpose AI Model is an AI model trained on large amounts of data that can perform a wide range of tasks — not designed for one specific use case.

Examples include:
- Large language models (GPT-4, Claude, Gemini, Llama)
- Multimodal models (text + image + audio)
- Foundation models used as a base for other products

> **Why it matters**: Most of the AI being built today is either a GPAI model or built *on top of* one. This section of the EU AI Act affects almost every major AI company operating in or selling to the EU.

---

## Why GPAI Has Its Own Rules

The standard risk tier framework (Unacceptable / High / Limited / Minimal) was designed for AI systems with a specific intended purpose — a hiring tool, a credit scorer, a chatbot.

GPAI models are different. They have **no single intended purpose**. The same model can be used to:
- Write a children's story (minimal risk)
- Screen job candidates (high risk)
- Predict court outcomes (high risk)
- Generate deepfakes (limited risk, or prohibited if used for manipulation)

The EU AI Act responds to this by creating **two separate compliance tracks** that run in parallel:

| Track | Who | What |
|-------|-----|------|
| GPAI model obligations | The company that built the model | Technical docs, training data transparency, copyright policy |
| Deployment obligations | The company/person using the model | Standard risk tier rules apply based on how they use it |

---

## GPAI Obligations — All Providers (Articles 53–54)

Regardless of model size or risk level, all GPAI model providers must:

**1. Technical Documentation**
- Maintain documentation covering: model architecture, training methodology, training data sources, compute used, evaluation results, and known limitations
- Must be provided to the EU AI Office on request

**2. Training Data Transparency**
- Publish a sufficiently detailed summary of the content used for training
- This summary must be publicly available (not just on request)
- Purpose: enable copyright holders to assess whether their work was used without authorisation

**3. Copyright Compliance Policy**
- Implement a policy to comply with EU copyright law
- Specifically: respect opt-outs under the Text and Data Mining exception (Article 4, EU Copyright Directive)
- In practice: honour robots.txt and similar signals from rights holders

**4. Cooperation with EU AI Office**
- Provide information and access as requested by the EU AI Office
- Participate in codes of practice if invited

---

## Systemic Risk GPAI — Additional Obligations (Article 55)

The EU AI Act creates a higher tier for GPAI models that could pose **systemic risk** — meaning their failure or misuse could affect large parts of society or critical systems.

### What triggers systemic risk classification?

**Automatic trigger**: Training compute exceeding **10²⁵ FLOPs** (floating point operations)
- This is a proxy for model capability and scale
- As of 2024, only the largest frontier models (GPT-4 class and above) exceed this threshold

**Discretionary trigger**: The EU AI Office can designate a model as systemic risk based on other factors, including:
- Number of users in the EU
- Multimodal capabilities
- Potential for widespread harm

### Additional obligations for systemic risk GPAI:

**Model Evaluation & Red-Teaming**
- Conduct standardised model evaluations before deployment
- Perform adversarial testing ("red-teaming") to identify misuse potential
- Results must be reported to the EU AI Office

**Incident Reporting**
- Report serious incidents and near-misses to the EU AI Office
- Timeframe: as soon as the provider becomes aware
- Examples: outputs causing serious harm, large-scale misuse, unexpected dangerous capabilities

**Cybersecurity**
- Implement measures to protect model weights and infrastructure
- Proportionate to the risk level of the model

**Energy Transparency**
- Report energy consumption of training and inference
- Publication required (publicly available)

---

## The Responsibility Split — Who Owns What?

This is the most important practical question for product teams building on GPAI models.

### Scenario: A law firm builds a case outcome predictor on top of a GPAI API

| Obligation | GPAI Provider (e.g. API company) | Deployer (e.g. law firm) |
|-----------|----------------------------------|--------------------------|
| Technical documentation | ✅ Must maintain | Can rely on provider's docs |
| Training data summary | ✅ Must publish | No obligation |
| Copyright policy | ✅ Must implement | No obligation |
| High Risk conformity assessment | ❌ Not responsible for deployment use | ✅ Must complete before deployment |
| Human oversight design | ❌ Cannot control how deployer uses model | ✅ Must implement |
| Incident reporting (deployment) | ❌ May not know about specific use | ✅ Must report to national authority |

### The critical interface: API Terms of Service

The legal boundary between GPAI provider and deployer is largely defined by the **API terms of service and usage policy**. A PM at a GPAI company must ensure:

- Prohibited uses are clearly defined and enforceable
- High Risk use cases are identified and deployers are informed of their obligations
- The system card / model card provides enough information for deployers to conduct their own conformity assessment
- Monitoring and enforcement mechanisms exist for policy violations

This is not just a legal document — it is a **product specification** with compliance implications.

---

## GPAI vs Standard Risk Tiers — How They Interact

```
GPAI Model (provider obligations apply)
        ↓
Used to build a specific AI system
        ↓
That system assessed against standard risk tiers
        ↓
If High Risk → deployer takes on full High Risk obligations
If Limited Risk → deployer ensures transparency
If Minimal Risk → no additional obligations
```

A GPAI model provider does **not** automatically take on High Risk obligations just because someone uses their model for a High Risk purpose — unless the provider itself deploys the model for that purpose.

---

## Key Dates for GPAI Compliance

| Milestone | Date |
|-----------|------|
| EU AI Act enters into force | 1 August 2024 |
| GPAI obligations apply | 2 August 2025 |
| Full Act applies (most provisions) | 2 August 2026 |
| EU AI Office publishes codes of practice | Ongoing from 2025 |

---

## PM Takeaways

- **If you work at a foundation model company**: Your compliance obligations exist at the model level, independent of how customers use your API. Training data transparency and copyright policy are product features, not just legal footnotes.

- **If you work at a company building on a GPAI API**: You are the deployer. If your product is High Risk, you own the conformity assessment — you cannot delegate this to your API provider.

- **If you work at a company doing both**: You have obligations on both tracks simultaneously. This is the most complex compliance situation and requires a dedicated AI governance function.

---

*Source: EUR-Lex — Regulation (EU) 2024/1689, Articles 51–55*
*https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:32024R1689*
