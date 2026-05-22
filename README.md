# 🇪🇺 EU AI Act Compliance Risk Scorer

A structured, logic-based framework for classifying AI systems under the **EU Artificial Intelligence Act (Regulation (EU) 2024/1689)** — fully in force as of August 2024.

> Built by a PM with a background in identity verification, AI governance, and regulatory compliance.

---

## What This Is

This repository is a **product thinking exercise** — not legal advice. It translates the EU AI Act's classification logic into a structured, reusable framework that any product or engineering team can use to:

- Understand where their AI system sits on the risk spectrum
- Identify compliance obligations early (before engineering begins)
- Run internal pre-assessments before formal conformity assessment

---

## Why It Matters

Every company building or deploying AI in the EU must comply with the EU AI Act. Non-compliance carries fines of up to **€35 million or 7% of global annual turnover** (whichever is higher) for the most serious violations.

Most teams don't know where to start. This framework gives them a starting point.

---

## Repository Structure

```
eu-ai-act-risk-scorer/
│
├── README.md                        ← You are here
├── risk-classification-logic.md     ← How risk tiers work + classification rules
├── compliance-checklist.md          ← Obligations per risk tier
├── decision-tree.md                 ← Step-by-step classification flowchart
├── sample-scenarios.md              ← 4 fictional AI systems scored (hiring, border, chatbot, credit)
├── sample-scenarios-extended.md     ← 3 more scenarios (healthcare, fraud detection, GPAI)
├── gpai-explainer.md                ← General Purpose AI models — dedicated rules explained
├── enforcement-tracker.md           ← National authority status + fine structure by country
└── glossary.md                      ← Key terms from the Act
```

---

## The Four Risk Tiers (Summary)

| Tier | Description | Examples |
|------|-------------|---------|
| 🔴 Unacceptable | Banned outright | Social scoring, subliminal manipulation |
| 🟠 High Risk | Permitted with strict obligations | Biometric ID, hiring tools, credit scoring |
| 🟡 Limited Risk | Transparency obligations only | Chatbots, deepfakes |
| 🟢 Minimal Risk | No specific obligations | Spam filters, AI in video games |

---

## How to Use This Framework

1. Start with [`decision-tree.md`](./decision-tree.md) — answer 6 questions to get a risk tier
2. Read [`risk-classification-logic.md`](./risk-classification-logic.md) for the full reasoning
3. Apply [`compliance-checklist.md`](./compliance-checklist.md) for your tier's obligations
4. Review [`sample-scenarios.md`](./sample-scenarios.md) to see how real-world cases are scored

---

## Legal Basis

All logic in this framework is derived from publicly available EU legislation:

- **Regulation (EU) 2024/1689** — The EU AI Act (full text)
- **Annex I** — AI system definition
- **Annex III** — High-risk AI system categories
- **Recitals 1–180** — Legislative intent and interpretation guidance

Source: [EUR-Lex — EU AI Act](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:32024R1689)

---

## Author

**Aizaz Ahmad** — Product & Operations | AI Governance | Identity Infrastructure  
[LinkedIn](https://linkedin.com/in/aizaz-a-b53224240)

---

> ⚠️ **Disclaimer**: This is a personal portfolio project for educational and PM demonstration purposes. It is not legal advice. Always consult qualified legal counsel for actual compliance decisions.
