# Sample Scenarios — Extended Set

Three additional AI systems scored through the EU AI Act decision tree.

---

## Scenario 5 — "MedAssist" (Clinical Decision Support Tool)

**Product description**: An AI tool used by hospital clinicians in Germany to analyse patient medical records, lab results, and imaging data, then recommend treatment pathways. The final decision always rests with the doctor.

**Operator**: A private hospital group operating across Germany and the Netherlands.

### Classification Walkthrough

| Question | Answer | Reasoning |
|----------|--------|-----------|
| Q1: AI system? | ✅ Yes | Uses ML to analyse data and generate treatment recommendations |
| Q2: EU scope? | ✅ Yes | Deployed in EU member states |
| Q3: Prohibited practice? | ❌ No | No manipulation, no biometric ID, no social scoring |
| Q4: Annex III? | ✅ Yes | Medical devices with safety components — critical infrastructure adjacent; also covered under EU Medical Device Regulation (MDR) |
| Q5: Significant risk? | ✅ Yes | Directly influences clinical decisions affecting patient health and safety |

### Result: 🟠 HIGH RISK

### Key Obligations
- Risk management system must cover clinical failure modes (misdiagnosis, missed conditions)
- Training data must be assessed for demographic bias — models trained on non-representative patient populations can perform worse for certain ethnicities or age groups
- Clinician must retain full override capability — system output is a recommendation, not a decision
- Technical documentation must include accuracy benchmarks per patient subgroup
- Post-market monitoring must track real-world clinical outcomes, not just model accuracy
- **Dual compliance**: EU AI Act AND EU Medical Device Regulation (MDR) — whichever is stricter applies

### PM Insight
> This is the most complex compliance scenario in practice. A PM on a healthcare AI product is navigating two regulatory regimes simultaneously. The key product decision is how to present AI recommendations to clinicians without creating automation bias — where doctors defer to the AI even when their clinical judgment says otherwise. This is a UX and ethics problem, not just a compliance checkbox.

---

## Scenario 6 — "FraudGuard" (Real-Time Payment Fraud Detection)

**Product description**: An AI system used by a pan-European bank to monitor transactions in real time and automatically block payments it classifies as likely fraudulent. Blocked transactions are held for human review within 24 hours.

**Operator**: A retail bank licensed in Ireland, serving customers across 12 EU member states.

### Classification Walkthrough

| Question | Answer | Reasoning |
|----------|--------|-----------|
| Q1: AI system? | ✅ Yes | ML classification model with autonomous blocking action |
| Q2: EU scope? | ✅ Yes | EU-licensed bank, EU customers |
| Q3: Prohibited practice? | ❌ No | Fraud detection ≠ social scoring (different purpose and legal basis) |
| Q4: Annex III? | ✅ Yes | Essential services — creditworthiness and financial services category |
| Q5: Significant risk? | ✅ Yes | Autonomous blocking directly restricts access to customer funds |

### Result: 🟠 HIGH RISK

### Key Obligations
- System must be accurate enough to avoid disproportionate false positives (legitimate transactions blocked)
- False positive rate must be documented and monitored as a key performance indicator
- Customers must be informed when a transaction is blocked by an automated system
- Human review process (the 24-hour hold) must be genuinely effective — not rubber-stamping
- GDPR Article 22 applies: customers have the right to request human review of automated decisions affecting them
- Cybersecurity resilience is critical — adversarial attacks (fraudsters probing the model) must be anticipated

### PM Insight
> Fraud detection is where compliance and business metrics collide hardest. A PM on this product is balancing false positive rate (customer experience, churn risk) against false negative rate (fraud losses). The EU AI Act adds a third dimension: the legal obligation to document and justify the threshold you set. Setting the sensitivity too high to catch more fraud creates a compliance problem; setting it too low creates a financial one. This tradeoff must be owned explicitly on the product roadmap.

---

## Scenario 7 — "LexAI" (General Purpose AI — Legal Research Assistant)

**Product description**: A large language model (similar to ChatGPT or Claude) developed by a US company and made available via API to law firms, businesses, and individuals across the EU. It can answer legal questions, summarise case law, and draft contract clauses. It has no specific deployment context — customers use it however they choose.

**Operator**: US-based AI company; deployers are EU law firms and businesses.

### Classification Walkthrough

| Question | Answer | Reasoning |
|----------|--------|-----------|
| Q1: AI system? | ✅ Yes | Large language model with broad capabilities |
| Q2: EU scope? | ✅ Yes | Accessible and marketed to EU users |
| Q3: Prohibited practice? | ❌ No | General assistant — no prohibited use built in |
| Q4: Annex III? | ⚠️ Depends on use | The model itself may not be High Risk, but specific deployments (e.g. EU law firm using it for case outcome prediction) could be |

### Special Classification: General Purpose AI (GPAI) Model

LexAI is a **General Purpose AI Model** under Articles 51–55 of the EU AI Act. GPAI models have their own rules, separate from the standard risk tiers.

### GPAI Obligations (Articles 51–55)

**All GPAI providers must:**
- Prepare and maintain technical documentation about the model
- Publish a summary of training data (content used for training)
- Have a policy for complying with EU copyright law (including respecting opt-outs from web scraping)
- Cooperate with the EU AI Office on request

**If the model has "systemic risk" (>10^25 FLOPs training compute or designated by EU AI Office):**
- Conduct model evaluations and adversarial testing
- Report serious incidents to the EU AI Office within defined timeframes
- Implement cybersecurity measures proportionate to the risk

**Who is responsible when GPAI is used for a High Risk purpose?**
- If a deployer uses LexAI for a High Risk application (e.g. predicting court outcomes to advise on litigation), **the deployer** takes on High Risk obligations
- The GPAI provider's obligations remain at the model level, not the deployment level

### PM Insight
> GPAI is the most commercially significant category in the EU AI Act and the least well understood. A PM at a foundation model company needs to manage two separate compliance tracks: model-level obligations (training data, technical docs, copyright policy) and deployment-level obligations (communicating to deployers what their responsibilities are when they build High Risk applications on top of the model). The interface between these two — the API terms of service, the usage policy, the system card — is fundamentally a product problem, not just a legal one.

---

## Extended Summary — All Scenarios

| System | Tier | Key PM Challenge |
|--------|------|-----------------|
| HireBot (CV Screening) | 🟠 High Risk | Bias in training data, human override workflow |
| BorderCheck (Document Verification) | 🟠 High Risk | Human oversight handoff design |
| SupportBot (Customer Chatbot) | 🟡 Limited Risk | Disclosure UX without killing conversion |
| CreditScore AI (Credit Assessment) | 🟠 High Risk | Explainability as a first-class product feature |
| MedAssist (Clinical Decision Support) | 🟠 High Risk | Dual regulatory compliance (AI Act + MDR) |
| FraudGuard (Payment Fraud Detection) | 🟠 High Risk | False positive rate as a compliance AND business metric |
| LexAI (General Purpose AI) | 🔵 GPAI | Two-tier compliance: model obligations + deployer obligations |

---

*All scenarios are fictional and created for educational and portfolio purposes.*
*Source law: Regulation (EU) 2024/1689 — https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:32024R1689*
