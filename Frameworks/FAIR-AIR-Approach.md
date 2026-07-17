# FAIR-AIR Approach for Quantitative AI Cyber Risk

FAIR-AIR™ is a FAIR-inspired approach developed by the FAIR Institute to help organizations identify, quantify, prioritize, and treat cyber risks associated with generative artificial intelligence and large language models. It applies the business-oriented language of cyber risk quantification to AI adoption decisions by expressing probable loss exposure in financial terms.

> **Type:** Practical AI cyber risk analysis playbook  
> **Organization:** FAIR Institute  
> **Public release:** February 2024  
> **Primary focus:** Quantitative GenAI and LLM cyber risk analysis  
> **Official resource:** [FAIR-AIR Approach Playbook](https://www.fairinstitute.org/hubfs/FAIR-AIR%20Approach%20Playbook.pdf)

## Purpose

The approach is designed to help security, privacy, technology, and business leaders collaborate on secure AI adoption without reducing the discussion to qualitative labels such as low, medium, or high. FAIR-AIR supports decisions concerning:

1. The probable financial exposure associated with an AI risk scenario.
2. The scenarios that should receive priority.
3. The risk drivers that most strongly influence exposure.
4. The controls or treatment options likely to produce the greatest reduction in risk.
5. The allocation of security investment across competing AI initiatives.

FAIR-AIR is an analytical and decision-support approach. It is not a standalone security-control catalogue, compliance standard, or substitute for technical threat modeling and assurance testing.

## Five-stage approach

| Stage | Objective | Key activities | Primary output |
| --- | --- | --- | --- |
| **1. Contextualize** | Understand the business decision and the relevant AI risk vector | Identify stakeholders, decision questions, business objectives, and the AI operating model | Decision context and selected risk vector |
| **2. Scope** | Define the specific loss event scenario to analyze | Identify assets, threat actors, attack methods, effects, and organizational impacts; formulate a clear risk statement | Scoped and defensible risk scenario |
| **3. Quantify** | Estimate probable loss exposure using FAIR | Collect internal and external data; estimate loss event frequency and loss magnitude; use ranges and distributions where appropriate | Quantified risk exposure expressed in financial terms |
| **4. Prioritize and Treat** | Identify the most material scenarios and effective mitigation options | Compare scenarios by probability and probable loss; identify key risk drivers; assess treatment options | Prioritized risk register and treatment alternatives |
| **5. Decision Making** | Support investment and deployment decisions | Compare the expected effect of controls, residual exposure, cost, feasibility, and business value | Risk-informed decision and execution plan |

## Five GenAI risk vectors

| Risk vector | Description | Example analysis questions |
| --- | --- | --- |
| **Shadow GenAI** | Employees or business units use GenAI services without full organizational awareness or authorization | What sensitive information may be disclosed? How frequently could unauthorized use create a loss event? |
| **Foundational LLM** | The organization builds or trains its own foundation model | Could inadequate safety controls, unauthorized training data, bias, poisoning, or integrity failures create material loss? |
| **Hosting on LLMs** | The organization hosts an LLM and develops applications or use cases on top of it | Are success criteria, model tuning, access controls, monitoring, resilience, and output-integrity controls adequate? |
| **Managed LLMs** | The organization uses a third-party LLM provider for business use cases | Could supplier control failures, prompt injection, data leakage, outages, or contractual gaps create material exposure? |
| **Active Cyber Attack** | Adversaries use LLMs to improve attacks against the organization | How could AI increase phishing effectiveness, vulnerability discovery, malware development, fraud, or attack scale? |

## Quantitative risk structure

A FAIR-AIR analysis should define a precise loss event rather than quantify “AI risk” as a broad category. A useful scenario statement normally identifies:

- The asset or business process at risk.
- The threat actor or causal agent.
- The action or attack method.
- The adverse event or control failure.
- The resulting operational, financial, legal, privacy, safety, or reputational effects.
- The time horizon for the estimate.

The analysis then estimates two core dimensions:

| FAIR dimension | AI risk interpretation |
| --- | --- |
| **Loss Event Frequency** | How often the defined AI-related loss event is expected to occur during the selected time horizon |
| **Loss Magnitude** | The probable financial impact if the event occurs, including primary and secondary loss effects |

The FAIR-AIR playbook also recommends identifying the key risk drivers behind the quantified result. Examples include the number of users with access to sensitive data, phishing click rates, the quantity of data exposed to a third-party LLM, missing safety controls, and poorly defined success criteria.

## Integration with the AI Cyber Shield

FAIR-AIR complements, rather than replaces, governance, security, and assurance frameworks.

| AI Cyber Shield activity | FAIR-AIR contribution | Complementary resources |
| --- | --- | --- |
| AI governance | Converts governance concerns into decision-oriented financial exposure | NIST AI RMF, ISO/IEC 42001, ISO/IEC 23894, EU AI Act |
| AI threat modeling | Converts selected threats and abuse cases into clearly scoped loss scenarios | MITRE ATLAS, OWASP Top 10 for LLM Applications, AI STRIDE, attack trees |
| Control selection | Identifies the risk drivers that controls should reduce | FAIR-CAM, CSA AI Controls Matrix, Google SAIF, secure AI lifecycle guidance |
| Materiality analysis | Estimates probable financial consequences of AI-related events | FAIR-MAM, enterprise materiality criteria, incident impact models |
| Assurance | Provides quantified decision evidence and residual-risk estimates | Evaluation reports, red-team findings, control testing, model and system cards |
| Executive communication | Expresses AI cyber risk in probability and financial-loss terms | Board risk appetite, investment analysis, risk registers, treatment plans |

## Suggested implementation workflow

1. Select an actual AI deployment, planned use case, agent, model, or third-party service.
2. Identify the business decision that the analysis must support.
3. Choose the most relevant FAIR-AIR risk vector.
4. Develop a small set of well-formed loss event scenarios.
5. Validate each scenario with business, privacy, legal, technology, and security stakeholders.
6. Collect internal data first, then supplement gaps with defensible external data and calibrated estimates.
7. Quantify loss event frequency and loss magnitude using ranges rather than false precision.
8. Document assumptions, confidence, uncertainty, and data limitations.
9. Identify the dominant risk drivers and model proposed controls against them.
10. Compare treatment cost, expected risk reduction, residual exposure, operational feasibility, and business value.
11. Record the decision, accountable owner, implementation plan, and reassessment trigger.
12. Reassess when the model, data, tools, autonomy, supplier, user population, threat landscape, or business process materially changes.

## Practical limitations

- The playbook focuses primarily on GenAI and LLM-related cyber risk and should be extended carefully for other AI technologies.
- Quantification quality depends on scenario quality, data quality, calibration, and transparent assumptions.
- Financial estimates should not obscure non-financial harms, legal duties, human-rights impacts, safety consequences, or national-security considerations.
- The example probabilities and loss values in the playbook are illustrative and should not be reused as organizational estimates.
- FAIR-AIR should be combined with technical testing, architectural review, security controls, privacy assessment, safety evaluation, and continuous monitoring.

## APA 7 references

FAIR Institute. (2024). *FAIR-AIR approach playbook: Using a FAIR-based risk approach to expedite AI adoption at your organization*. https://www.fairinstitute.org/hubfs/FAIR-AIR%20Approach%20Playbook.pdf

FAIR Institute. (2024, February 28). *A FAIR artificial intelligence (AI) cyber risk playbook*. https://www.fairinstitute.org/blog/fair-artificial-intelligence-ai-cyber-risk-playbook
