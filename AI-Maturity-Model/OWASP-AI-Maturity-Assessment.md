# OWASP AI Maturity Assessment (AIMA)

## Overview

The **OWASP AI Maturity Assessment (AIMA)** is a community-driven maturity model that helps organizations evaluate and improve how they adopt, design, implement, operate, and govern artificial intelligence systems.

The model is useful for security leaders, AI governance teams, architects, developers, risk managers, auditors, and executives who need a structured path from experimental AI adoption to controlled, measurable, and continuously improved AI operations.

OWASP AIMA organizes organizational maturity into five core domains:

1. Strategy.
2. Design.
3. Implementation.
4. Operations.
5. Governance.

This page provides an implementation-oriented interpretation for AI security, safety, governance, and assurance programs. It does not replace the official OWASP documentation or toolkit.

## Why use an AI maturity model?

Organizations often deploy AI faster than they establish ownership, risk controls, security testing, monitoring, incident response, and evidence-based assurance. A maturity model helps establish a defensible baseline, identify gaps, prioritize investment, and define a realistic improvement roadmap.

A maturity assessment should answer four questions:

1. What AI capabilities and dependencies does the organization currently operate?
2. Which controls are consistently implemented and supported by evidence?
3. Which risks exceed the organization's risk appetite?
4. What improvements are required to reach the target maturity level?

## Five maturity levels

| Level | Name | Organizational characteristics |
| --- | --- | --- |
| 1 | Initial | AI use is experimental or fragmented. Ownership, inventories, controls, and evidence are limited or inconsistent. |
| 2 | Managed | Basic policies, named owners, inventories, risk reviews, and minimum security controls exist for selected systems. |
| 3 | Defined | Standardized lifecycle processes, control baselines, testing requirements, documentation, and approval gates are applied across the organization. |
| 4 | Measured | Control effectiveness, model behavior, incidents, drift, resilience, and business outcomes are measured using defined metrics and evidence. |
| 5 | Optimizing | The organization continuously improves AI governance, security, safety, assurance, automation, and resilience using lessons learned and threat intelligence. |

Maturity should be scored per domain rather than assigning a single unsupported organization-wide score. A weak domain can create systemic exposure even when other domains are advanced.

## Domain assessment matrix

| Domain | Level 1: Initial | Level 2: Managed | Level 3: Defined | Level 4: Measured | Level 5: Optimizing |
| --- | --- | --- | --- | --- | --- |
| Strategy | Isolated pilots and unclear business objectives | Approved use cases and named sponsors | Enterprise AI strategy aligned with risk appetite | Value, risk, and control performance are measured | Portfolio decisions adapt continuously to evidence and emerging risk |
| Design | Security and safety considered late | Basic threat and privacy reviews | Secure-by-design architecture, trust boundaries, misuse cases, and human oversight | Design controls are validated through testing and assurance evidence | Reference architectures and design patterns improve continuously |
| Implementation | Ad hoc development and weak provenance | Minimum coding, data, access, and dependency controls | Secure AI lifecycle, CI/CD gates, model and data provenance, SBOM/AIBOM, and repeatable testing | Automated verification, red teaming, coverage metrics, and release evidence | Adaptive testing, continuous validation, and threat-informed engineering |
| Operations | Limited monitoring and informal support | Logging, access control, backup, and basic incident procedures | Defined AI operations, model monitoring, drift management, response playbooks, and change control | Operational risk, model behavior, incidents, recovery, and control effectiveness are measured | Predictive monitoring, automated containment, safe remediation, and continuous resilience exercises |
| Governance | Unclear accountability and undocumented AI use | AI inventory, basic policy, risk ownership, and approval requirements | Formal governance structure, lifecycle accountability, documentation, compliance mapping, and auditability | Governance metrics, independent assurance, exceptions, and residual risk are tracked | Governance evolves through incidents, regulation, assurance results, and strategic review |

## Recommended control areas

Each assessment should examine evidence across the following control areas:

1. AI system and use-case inventory.
2. Accountability, ownership, and segregation of duties.
3. Risk classification and acceptable-use decisions.
4. Data governance, provenance, quality, privacy, and poisoning resistance.
5. Model provenance, integrity, evaluation, and change control.
6. Threat modeling for models, agents, RAG, tools, APIs, and infrastructure.
7. Identity, least privilege, secret management, and tool authorization.
8. Secure development, dependency management, and supply-chain assurance.
9. Prompt injection, jailbreak, misuse, abuse, and adversarial testing.
10. Output validation, guardrails, deterministic controls, and human approval.
11. Logging, observability, drift detection, and continuous monitoring.
12. AI incident response, recovery, disclosure, and lessons learned.
13. Third-party AI, cloud, model, plugin, and agent-service risk.
14. Legal, regulatory, ethical, and contractual compliance.
15. Independent assurance, audit evidence, and executive reporting.

## Scoring method

Score each practice from 0 to 5:

| Score | Meaning |
| --- | --- |
| 0 | Not applicable or not assessed; justification is required |
| 1 | Informal, reactive, or undocumented |
| 2 | Partially implemented for selected systems |
| 3 | Defined and consistently implemented |
| 4 | Measured and supported by effectiveness evidence |
| 5 | Continuously improved and integrated into enterprise decision-making |

For each score, record:

1. Current maturity.
2. Target maturity.
3. Evidence.
4. Identified gap.
5. Risk created by the gap.
6. Remediation action.
7. Accountable owner.
8. Target date.
9. Dependency or required investment.
10. Residual risk and approval status.

## Assessment principles

### Evidence over declarations

A policy alone does not demonstrate maturity. Evidence may include inventories, architecture reviews, threat models, test reports, logs, incident exercises, model cards, data documentation, approvals, exception records, metrics, and independent assurance reports.

### Risk-based targets

Not every system requires Level 5 maturity. Target maturity should reflect impact, autonomy, data sensitivity, external exposure, model capability, regulatory obligations, and the potential for physical, financial, societal, or national-security harm.

### No averaging away critical weaknesses

A high average score should not conceal severe gaps. Critical domains such as identity, data protection, human oversight, incident response, and agent tool authorization should have minimum required thresholds.

### Lifecycle coverage

The assessment should cover planning, acquisition, design, development, testing, deployment, operation, change, incident response, and retirement.

### Continuous reassessment

Reassess after major model changes, new data sources, new tools or plugins, autonomy increases, material incidents, regulatory changes, mergers, and significant threat-landscape changes.

## Suggested assessment workflow

1. Define the assessment scope and business context.
2. Inventory AI systems, models, agents, datasets, tools, vendors, and owners.
3. Classify systems by impact, autonomy, exposure, and data sensitivity.
4. Interview governance, security, engineering, legal, privacy, operations, and business stakeholders.
5. Collect evidence and score each domain practice.
6. Validate findings through technical testing and sample-based verification.
7. Identify minimum-threshold failures and systemic risks.
8. Define target maturity by system class and domain.
9. Create a prioritized remediation roadmap.
10. Obtain accountable executive approval for residual risk.
11. Track improvements using measurable indicators.
12. Repeat the assessment at least annually and after material change.

## Example metrics

| Area | Example indicator |
| --- | --- |
| Inventory | Percentage of AI systems with an identified owner and risk classification |
| Design | Percentage of high-impact systems with an approved threat model |
| Testing | Percentage of releases passing required security, safety, and adversarial evaluations |
| Data | Percentage of datasets with documented provenance and integrity controls |
| Agents | Percentage of agent tools protected by scoped authorization and approval gates |
| Monitoring | Mean time to detect model, data, prompt, or agent anomalies |
| Incidents | Mean time to contain and recover from AI-related incidents |
| Assurance | Percentage of high-risk systems with independent validation |
| Exceptions | Number and age of unresolved AI control exceptions |
| Improvement | Percentage of maturity-roadmap actions completed on schedule |

## Mapping to complementary frameworks

| Framework or standard | How it complements maturity assessment |
| --- | --- |
| OWASP AI Maturity Assessment | Primary organizational AI maturity structure |
| OWASP SAMM | Software assurance maturity and secure development improvement |
| OWASP AISVS | Testable security requirements for AI-enabled systems |
| OWASP Top 10 for LLM Applications | Common LLM application risk categories |
| OWASP Agentic AI guidance | Threats and mitigations for autonomous and tool-using AI systems |
| NIST AI RMF | GOVERN, MAP, MEASURE, and MANAGE risk-management functions |
| NIST AI 600-1 | Generative AI risk profile and recommended actions |
| ISO/IEC 42001 | Artificial intelligence management system requirements |
| ISO/IEC 23894 | AI risk-management guidance |
| MITRE ATLAS | Adversarial tactics and techniques targeting AI systems |
| CSA AI Controls Matrix | Cloud and enterprise AI control mapping |
| Google SAIF | Secure AI development and deployment principles |

## Executive interpretation

The maturity score is not the final objective. The objective is to establish an AI capability that delivers value while remaining governable, secure, safe, resilient, auditable, and aligned with organizational risk appetite.

Executives should focus on:

1. Critical gaps below mandatory thresholds.
2. High-impact systems operating without sufficient evidence.
3. Excessive autonomy or privilege without compensating controls.
4. Unmanaged third-party and supply-chain dependencies.
5. Weak detection, response, recovery, and accountability.
6. Whether investment improves measurable risk and business outcomes.

## References

National Institute of Standards and Technology. (2023). *Artificial intelligence risk management framework (AI RMF 1.0)*. U.S. Department of Commerce. https://doi.org/10.6028/NIST.AI.100-1

National Institute of Standards and Technology. (2024). *Artificial intelligence risk management framework: Generative artificial intelligence profile (NIST AI 600-1)*. U.S. Department of Commerce. https://doi.org/10.6028/NIST.AI.600-1

OWASP Foundation. (2026). *OWASP AI maturity assessment*. https://owasp.org/www-project-ai-maturity-assessment/

OWASP Foundation. (n.d.). *OWASP software assurance maturity model*. https://owaspsamm.org/

## Author

Yuval Sinay, 2026.

## License and use

Original repository content is licensed under CC BY 4.0 unless otherwise stated. Use this material for lawful, ethical, defensive, governance, assurance, and educational purposes. The official OWASP project materials remain subject to their respective licenses and project terms.