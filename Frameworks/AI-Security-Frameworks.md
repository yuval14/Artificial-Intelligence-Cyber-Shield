# AI Security Frameworks

This page lists major AI security frameworks, taxonomies, standards, and control catalogs that help organizations protect AI systems, models, agents, data pipelines, and AI-enabled cyber defense capabilities.

## Framework comparison

| # | Vendor / organization | Framework / resource | Goal / function | Release date | Open source / public | Primary use |
| --- | --- | --- | --- | --- | --- | --- |
| 1 | NIST | AI Risk Management Framework 1.0 | Manage AI risks through Govern, Map, Measure, and Manage functions | 2023 | Yes | Enterprise AI risk management and governance |
| 2 | NIST | AI RMF Generative AI Profile | Apply the AI RMF to generative AI risks and controls | 2024 | Yes | GenAI risk management |
| 3 | MITRE | ATLAS | Knowledge base of adversary tactics and techniques against AI-enabled systems | 2020 | Yes | AI threat modeling, detection, red teaming, and CTI |
| 4 | OWASP | Top 10 for LLM Applications | Identify leading security risks in LLM applications | 2023, updated 2025 | Yes | Secure LLM application design and assessment |
| 5 | OWASP | Machine Learning Security Top 10 | Identify security risks in machine learning systems | 2023 | Yes | ML system security assessment |
| 6 | Cloud Security Alliance | AI Controls Matrix | Map AI risks to security and governance controls | 2024 | Yes | Control mapping and assurance |
| 7 | Cloud Security Alliance | AI Security Initiative guidance | Practical security guidance for AI adoption and AI-enabled systems | 2023 onwards | Yes | Cloud and enterprise AI security |
| 8 | Google | Secure AI Framework | Security framework for building and deploying AI systems securely | 2023 | Yes | Secure AI engineering and architecture |
| 9 | Microsoft | AI security guidance and AI red team practices | Secure development, testing, monitoring, and threat mitigation for AI systems | 2023 onwards | Yes | Enterprise AI security operations |
| 10 | ENISA | Cybersecurity of AI and AI cybersecurity guidance | Explain AI cybersecurity threats, controls, and assurance needs | 2020 onwards | Yes | EU cybersecurity policy and AI assurance |
| 11 | ISO / IEC | ISO/IEC 42001 | AI management system standard for responsible AI governance | 2023 | Public standard, paid text | AI management system implementation |
| 12 | ISO / IEC | ISO/IEC 23894 | AI risk management guidance | 2023 | Public standard, paid text | AI risk lifecycle management |
| 13 | CISA, NSA, FBI, UK NCSC, and partners | Guidelines for Secure AI System Development | Secure design, development, deployment, and operation of AI systems | 2023 | Yes | Secure AI lifecycle guidance |
| 14 | OECD | AI Principles and OECD AI Policy Observatory | Human-centered, trustworthy AI policy principles and implementation resources | 2019 onwards | Yes | Policy and governance alignment |
| 15 | European Union | EU AI Act | Risk-based legal framework for AI systems in the EU | 2024 | Yes | Legal and regulatory compliance |

## Practical use

Use these frameworks together rather than as substitutes:

1. Use NIST AI RMF and ISO/IEC 23894 for risk governance.
2. Use OWASP, MITRE ATLAS, and Google SAIF for technical security engineering.
3. Use CSA AI Controls Matrix and ISO/IEC 42001 for control evidence and assurance.
4. Use the EU AI Act and OECD AI Principles for legal, policy, and public-interest alignment.
5. Use CISA and NCSC secure AI guidance for secure lifecycle implementation.

## Suggested control domains

| Domain | Example controls |
| --- | --- |
| AI asset inventory | Model registry, dataset inventory, API inventory, agent tool registry |
| Data security | Data provenance, access control, poisoning detection, sensitive-data filtering |
| Model security | Model artifact protection, model integrity checks, evaluation gates, rollback plans |
| Prompt and context security | Prompt injection defenses, retrieval filtering, instruction hierarchy, output validation |
| Agent security | Tool permissions, identity boundaries, memory control, sandboxing, human approval gates |
| Monitoring | Abuse detection, drift monitoring, jailbreak telemetry, model behavior logging |
| Incident response | AI incident taxonomy, playbooks, evidence capture, escalation paths |
| Assurance | Red teaming, independent evaluation, safety cases, audit evidence, continuous review |

## APA 7 references

Cloud Security Alliance. (2024). *AI controls matrix*. https://cloudsecurityalliance.org/

Cybersecurity and Infrastructure Security Agency, National Security Agency, Federal Bureau of Investigation, National Cyber Security Centre, and international partners. (2023). *Guidelines for secure AI system development*. https://www.cisa.gov/

European Union. (2024). *Artificial Intelligence Act*. https://artificialintelligenceact.eu/

Google. (2023). *Secure AI framework*. https://saif.google/

International Organization for Standardization. (2023). *ISO/IEC 23894:2023 Artificial intelligence: Guidance on risk management*. https://www.iso.org/

International Organization for Standardization. (2023). *ISO/IEC 42001:2023 Artificial intelligence: Management system*. https://www.iso.org/

MITRE. (2020). *MITRE ATLAS: Adversarial threat landscape for artificial-intelligence systems*. https://atlas.mitre.org/

National Institute of Standards and Technology. (2023). *Artificial intelligence risk management framework (AI RMF 1.0)*. https://www.nist.gov/itl/ai-risk-management-framework

National Institute of Standards and Technology. (2024). *Artificial intelligence risk management framework: Generative artificial intelligence profile*. https://www.nist.gov/itl/ai-risk-management-framework

Organisation for Economic Co-operation and Development. (2019). *OECD principles on artificial intelligence*. https://oecd.ai/

OWASP Foundation. (2025). *OWASP top 10 for large language model applications*. https://owasp.org/www-project-top-10-for-large-language-model-applications/

OWASP Foundation. (2023). *Machine learning security top 10*. https://owasp.org/