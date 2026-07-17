# AI Governance and Assurance Frameworks

This page maps AI governance, assurance, safety, cybersecurity, responsibility, and quantitative risk frameworks that can help organizations design, deploy, evaluate, monitor, and audit AI systems.

## Framework comparison

| # | Organization | Framework / standard / resource | Goal / function | Release date | Open source / public | Primary use |
| --- | --- | --- | --- | --- | --- | --- |
| 1 | NIST | AI Risk Management Framework 1.0 | Voluntary framework to manage AI risks to individuals, organizations, and society | 2023 | Yes | Enterprise AI risk management |
| 2 | NIST | AI RMF Generative AI Profile, NIST AI 600-1 | Profile for identifying and managing unique risks from generative AI | 2024 | Yes | GenAI governance and assurance |
| 3 | NIST | AI RMF Critical Infrastructure Profile concept | Forthcoming profile for trustworthy AI in critical infrastructure | 2026 concept note | Yes | Critical infrastructure AI governance |
| 4 | ISO / IEC | ISO/IEC 42001 | AI management system standard | 2023 | Public standard, paid text | AI governance management system |
| 5 | ISO / IEC | ISO/IEC 23894 | Guidance on AI risk management | 2023 | Public standard, paid text | AI risk lifecycle management |
| 6 | ISO / IEC | ISO/IEC 23053 | Framework for AI systems using machine learning | 2022 | Public standard, paid text | AI system lifecycle and architecture |
| 7 | OECD | OECD AI Principles | Human-centered values, transparency, robustness, accountability, and inclusive growth | 2019, updated | Yes | Policy and responsible AI alignment |
| 8 | European Union | EU AI Act | Risk-based legal framework for AI systems and GPAI models | 2024 | Yes | Legal compliance and market access |
| 9 | European Commission | General-Purpose AI Code of Practice | Voluntary compliance tool for GPAI transparency, copyright, safety, and security obligations | 2025 | Yes | GPAI provider assurance |
| 10 | ENISA | AI cybersecurity guidance | Cybersecurity threats, controls, and lifecycle considerations for AI | 2020 onwards | Yes | EU AI cybersecurity governance |
| 11 | ETSI | Securing Artificial Intelligence standards family | AI cybersecurity, privacy, transparency, platform security, vulnerability disclosure, and baseline security | 2019 onwards | Yes | AI security assurance and standardization |
| 12 | Cloud Security Alliance | AI Controls Matrix | Control mapping for AI risks and governance evidence | 2024 | Yes | Control assurance and audit mapping |
| 13 | Google | Secure AI Framework | Practitioner guide for secure AI design, deployment, operations, and agents | 2023 onwards | Yes | Security engineering governance |
| 14 | Microsoft | Responsible AI Standard and AI security guidance | Internal governance model and operational guidance for responsible AI and security | 2022 onwards | Public guidance | Enterprise responsible AI implementation |
| 15 | CISA, NSA, FBI, UK NCSC, and partners | Guidelines for Secure AI System Development | Secure AI design, development, deployment, and operation | 2023 | Yes | Secure lifecycle governance |
| 16 | OpenAI | Preparedness Framework | Frontier model risk tracking and safeguards for cyber, CBRN, persuasion, and autonomy risks | 2023, updated | Public document | Frontier AI safety governance |
| 17 | Anthropic | Responsible Scaling Policy | Capability-linked safety and security requirements for advanced AI systems | 2023, updated | Public document | Frontier AI risk governance |
| 18 | Google DeepMind | Frontier Safety Framework | Severe-risk identification and mitigation for frontier AI models | 2024, updated | Public document | Frontier safety assurance |
| 19 | UK AI Security Institute | AI safety evaluations | Independent evaluation of advanced AI systems | 2023 onwards | Public | Frontier model evaluation |
| 20 | MLCommons | AILuminate | AI safety benchmark and risk/reliability evaluation | 2024 onwards | Yes | Model behavior assurance |
| 21 | FAIR Institute | [FAIR-AIR Approach](FAIR-AIR-Approach.md) | Five-stage FAIR-based approach for contextualizing, scoping, quantifying, prioritizing, treating, and communicating GenAI cyber risk in financial terms | February 2024 | Yes | Quantitative AI cyber risk analysis and investment prioritization |

## Governance domains

| Domain | Description | Example evidence |
| --- | --- | --- |
| Accountability | Clear ownership for AI system risk, approval, deployment, monitoring, and retirement | RACI, named risk owner, executive approval record |
| Risk classification | Classification of system purpose, impact, autonomy, data sensitivity, and legal category | AI system risk register, EU AI Act classification, impact assessment |
| Quantitative risk analysis | Scenario-based estimation of probable AI loss event frequency, magnitude, key risk drivers, and residual exposure | FAIR-AIR analysis, loss exposure distribution, assumptions register, treatment comparison |
| Secure AI lifecycle | Security gates across design, data, training, fine-tuning, deployment, inference, and retirement | SDLC policy, secure design review, release gates |
| Data governance | Provenance, consent, minimization, privacy, quality, and dataset integrity | Dataset cards, data lineage, DPIA, poisoning tests |
| Model governance | Model selection, evaluation, versioning, rollback, monitoring, and retirement | Model card, evaluation report, version registry, rollback plan |
| Agent governance | Tool permissions, autonomy levels, human approval, memory, identity, and action control | Tool registry, approval matrix, agent risk rating |
| Safety and misuse | Assessment of harmful capability, abuse cases, dual-use risks, and safeguards | Red team report, misuse case analysis, safety evaluation |
| Cybersecurity | Controls against prompt injection, model theft, data leakage, poisoning, supply-chain compromise, and tool misuse | Threat model, penetration test, AI red team evidence |
| Transparency | User disclosure, explainability, traceability, and documentation | Transparency notice, model card, system card, audit log |
| Incident response | Playbooks for AI incidents, vulnerability disclosure, rollback, evidence, and communication | AI incident playbook, PSIRT process, forensic package |
| Continuous assurance | Ongoing monitoring, drift detection, re-evaluation, and independent review | Monitoring dashboard, periodic review, audit report |

## Assurance evidence package

| Evidence artifact | Purpose |
| --- | --- |
| AI system card | Summarizes system purpose, users, data, models, tools, risks, limitations, and controls |
| AI risk register | Tracks risks, owners, severity, mitigations, residual risk, and review dates |
| Quantitative AI risk analysis | Documents the scoped loss event scenario, probability ranges, loss magnitude, key risk drivers, assumptions, uncertainty, and treatment economics |
| Threat model | Maps threats across identity, prompt, context, model, data, tools, agents, infrastructure, and supply chain |
| Evaluation report | Records safety, security, robustness, fairness, privacy, and performance test results |
| Red team report | Documents adversarial testing, exploit paths, severity, and remediation |
| Data provenance record | Shows origin, license, sensitivity, quality, and integrity of datasets and RAG sources |
| Model registry record | Tracks model version, hashes, lineage, evaluation, deployment state, and rollback options |
| Control mapping | Maps controls to NIST AI RMF, ISO/IEC 42001, CSA AI Controls Matrix, ETSI, OWASP, and EU AI Act obligations |
| Incident playbook | Defines escalation, containment, communication, legal review, and lessons learned |
| Human oversight matrix | Defines when human approval, human review, or human override is required |

## Suggested governance workflow

1. Inventory AI systems, models, agents, datasets, tools, APIs, and third-party dependencies.
2. Classify each system by risk, autonomy, data sensitivity, sector, and legal/regulatory category.
3. Create a system-specific threat model using AI STRIDE, MITRE ATLAS, OWASP LLM Top 10, and agent-specific risks.
4. Translate material threats and control failures into precise loss event scenarios and use FAIR-AIR when financial quantification would improve the decision.
5. Map controls to NIST AI RMF, ISO/IEC 42001, CSA AI Controls Matrix, ETSI, EU AI Act, and secure AI lifecycle guidance.
6. Define assurance evidence before deployment, including evaluation, red teaming, model documentation, quantitative risk evidence, and incident response evidence.
7. Establish continuous monitoring for drift, abuse, prompt injection, unsafe tool use, data leakage, cost anomalies, and policy violations.
8. Reassess after model updates, new tools, new data sources, new jurisdictions, high-impact incidents, or material changes in autonomy.

## Relationship between governance and security

AI governance is not only policy. It must produce enforceable technical and operational controls. For high-impact AI systems, governance should connect directly to secure architecture, runtime policy enforcement, logging, incident response, red teaming, vulnerability disclosure, and quantified decision support.

| Governance requirement | Security implementation |
| --- | --- |
| Accountability | Named system owner, security owner, model owner, data owner, and tool owner |
| Risk-informed investment | FAIR-AIR scenario analysis, key risk drivers, control-effect estimates, treatment cost, and residual exposure |
| Human oversight | Approval gates, override mechanisms, escalation rules, evidence capture |
| Transparency | User notices, traceable outputs, model and system documentation |
| Robustness | Evaluation suites, adversarial testing, drift monitoring, rollback |
| Cybersecurity | Threat modeling, least privilege, sandboxing, secure SDLC, monitoring |
| Privacy | Data minimization, access control, privacy testing, retention limits |
| Incident handling | AI incident playbooks, coordinated vulnerability disclosure, post-incident review |

## APA 7 references

Anthropic. (2026). *Responsible scaling policy*. https://www.anthropic.com/responsible-scaling-policy

Cloud Security Alliance. (2024). *AI controls matrix*. https://cloudsecurityalliance.org/

Cybersecurity and Infrastructure Security Agency, National Security Agency, Federal Bureau of Investigation, National Cyber Security Centre, and international partners. (2023). *Guidelines for secure AI system development*. https://www.cisa.gov/

European Commission. (2025). *General-purpose AI code of practice*. https://digital-strategy.ec.europa.eu/

European Telecommunications Standards Institute. (n.d.). *Securing Artificial Intelligence*. https://www.etsi.org/technologies/securing-artificial-intelligence

European Union. (2024). *Artificial Intelligence Act*. https://artificialintelligenceact.eu/

FAIR Institute. (2024). *FAIR-AIR approach playbook: Using a FAIR-based risk approach to expedite AI adoption at your organization*. https://www.fairinstitute.org/hubfs/FAIR-AIR%20Approach%20Playbook.pdf

Google. (2023). *Secure AI framework*. https://saif.google/

Google DeepMind. (2024). *Frontier safety framework*. https://deepmind.google/

International Organization for Standardization. (2022). *ISO/IEC 23053:2022 Framework for artificial intelligence systems using machine learning*. https://www.iso.org/

International Organization for Standardization. (2023). *ISO/IEC 23894:2023 Artificial intelligence: Guidance on risk management*. https://www.iso.org/

International Organization for Standardization. (2023). *ISO/IEC 42001:2023 Artificial intelligence: Management system*. https://www.iso.org/

Microsoft. (2022). *Responsible AI standard*. https://www.microsoft.com/ai/responsible-ai

National Institute of Standards and Technology. (2023). *Artificial intelligence risk management framework (AI RMF 1.0)*. https://doi.org/10.6028/NIST.AI.100-1

National Institute of Standards and Technology. (2024). *Artificial intelligence risk management framework: Generative artificial intelligence profile*. https://doi.org/10.6028/NIST.AI.600-1

OpenAI. (2024). *Preparedness framework*. https://openai.com/safety/preparedness/

Organisation for Economic Co-operation and Development. (2019). *OECD principles on artificial intelligence*. https://oecd.ai/

UK AI Security Institute. (2024). *AI safety evaluations*. https://www.aisi.gov.uk/
