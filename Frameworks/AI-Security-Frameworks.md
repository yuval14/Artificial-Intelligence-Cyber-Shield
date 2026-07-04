# AI Security Frameworks

This page lists major AI security frameworks, taxonomies, standards, and control catalogs that help organizations protect AI systems, models, agents, data pipelines, AI-enabled services, connected products, and AI-enabled cyber defense capabilities.

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
| 16 | ETSI | ETSI ISG SAI standards and reports | Standardization work for securing AI and using AI for security | 2019 onwards | Yes | AI cybersecurity standardization |
| 17 | ETSI | ETSI GR SAI 004, Problem Statement | Defines the AI cybersecurity problem space and standardization needs | 2020 | Yes | Threat framing and gap analysis |
| 18 | ETSI | ETSI GR SAI 005, Mitigation Strategy Report | Describes mitigation strategies for threats against AI systems | 2021 | Yes | AI security control planning |
| 19 | ETSI | ETSI GR SAI 006, Role of Hardware in Security of AI | Explains hardware roots of trust, trusted execution, and platform security for AI | 2021 | Yes | AI platform and hardware security |
| 20 | ETSI | ETSI GR SAI 007, Explicability and Transparency of AI Processing | Addresses explainability, transparency, and traceability of AI processing | 2022 | Yes | Assurance, explainability, and accountability |
| 21 | ETSI | ETSI GR SAI 008, Privacy Aspects of AI / ML Systems | Addresses privacy risks and privacy protection for AI and ML systems | 2022 | Yes | Privacy-preserving AI security |
| 22 | ETSI | ETSI GR SAI 009, AI Computing Platform Security Framework | Provides a security framework for AI computing platforms | 2023 | Yes | AI platform and infrastructure security |
| 23 | ETSI | ETSI GR SAI 010, AI-Based Security and Security of AI Ecosystem | Addresses AI used for cybersecurity and security of AI ecosystems | 2023 | Yes | AI ecosystem security architecture |
| 24 | ETSI | ETSI GR SAI 011, Multi-Party Coordinated Vulnerability Disclosure for AI | Applies coordinated vulnerability disclosure practices to AI systems | 2024 | Yes | AI vulnerability disclosure and PSIRT workflow |
| 25 | ETSI | ETSI TS 103 732, Security Baseline for AI Models and Systems | Establishes baseline security requirements for AI models and systems | 2024 | Yes | Technical AI security baseline |
| 26 | ETSI | ETSI EN 303 645 | Baseline cybersecurity provisions for consumer IoT devices, relevant to edge AI and AI-enabled connected products | 2020, updated later | Yes | Consumer IoT and edge-AI security |
| 27 | ETSI | ETSI TS 103 701 | Conformity assessment specification for ETSI EN 303 645 | 2021 | Yes | IoT and edge-AI security testing |
| 28 | ETSI | ETSI TR 103 621 | Implementation guidance for consumer IoT cybersecurity | 2019 | Yes | Secure implementation guidance |
| 29 | ETSI | ETSI 304 223 | AI cybersecurity, safety, and responsibility related guidance | Verification pending | Yes / public if published | Responsible, safe, and secure AI alignment |
| 30 | AIDEFEND Framework Initiative | AIDEFEND, AI Security Defense Framework | Structured AI security defense knowledge base of countermeasures for AI and ML systems, mapped to major AI security frameworks | 2026 | Yes, CC BY 4.0 | AI defense architecture, control mapping, detection, containment, incident response, and recovery |
| 31 | IBM | Adversarial Robustness Toolbox | Open source library for adversarial ML attacks, defenses, robustness testing, certification, and runtime detection | 2018 | Yes, MIT License | AI security testing, adversarial robustness, red teaming, and model hardening |
| 32 | IBM | AI Fairness 360 | Open source toolkit for detecting, explaining, and mitigating unwanted algorithmic bias in datasets and ML models | 2018 | Yes, Apache 2.0 | Fairness testing, bias mitigation, and responsible AI assurance |
| 33 | IBM | AI Explainability 360 | Open source toolkit and taxonomy for explaining AI model decisions using multiple explanation methods | 2019 | Yes, Apache 2.0 | Explainability, transparency, auditability, and model assurance |
| 34 | IBM | AI FactSheets 360 | Research framework and toolkit for documenting AI services through supplier-style declarations of conformity | 2018 | Yes | AI transparency, provenance, accountability, and governance evidence |
| 35 | IBM | Uncertainty Quantification 360 | Open source toolkit for quantifying, evaluating, improving, and communicating AI uncertainty | 2021 | Yes, Apache 2.0 | Reliability assessment, uncertainty communication, and trustworthy AI engineering |
| 36 | IBM | AI Risk Atlas and Risk Atlas Nexus | Taxonomy and tooling for navigating AI risks, resources, benchmarks, datasets, mitigations, and governance mappings | 2025 | Yes | AI risk taxonomy, governance mapping, compliance workflows, and mitigation planning |
| 37 | IBM | watsonx.governance | Enterprise AI governance platform for lifecycle governance, risk management, compliance, monitoring, and model oversight | 2023 | Public / commercial platform | Operational AI governance, regulatory compliance, model monitoring, and audit evidence |

## ETSI AI cybersecurity standards family

ETSI material should be treated as a standards family rather than a single checklist. It is useful for linking AI cybersecurity with hardware trust, platform security, privacy, transparency, vulnerability disclosure, IoT, and assurance.

| ETSI item | Suggested mapping in this repository |
| --- | --- |
| ETSI GR SAI 004 | AI cybersecurity problem definition, threat framing, and gap analysis |
| ETSI GR SAI 005 | Mitigation planning for attacks against AI systems |
| ETSI GR SAI 006 | Hardware roots of trust, secure execution, and AI platform protection |
| ETSI GR SAI 007 | Explainability, traceability, transparency, and accountability evidence |
| ETSI GR SAI 008 | Privacy risks, privacy controls, and privacy-preserving AI techniques |
| ETSI GR SAI 009 | AI computing platform security and secure infrastructure architecture |
| ETSI GR SAI 010 | Security architecture for AI-enabled security and AI ecosystem protection |
| ETSI GR SAI 011 | AI vulnerability disclosure, multi-party coordination, and PSIRT integration |
| ETSI TS 103 732 | Baseline security requirements for AI models and AI systems |
| ETSI EN 303 645 | Security baseline for consumer IoT and edge-AI devices |
| ETSI TS 103 701 | Conformity assessment for consumer IoT cybersecurity controls |
| ETSI TR 103 621 | Implementation guidance for consumer IoT cybersecurity controls |
| ETSI 304 223 | Candidate mapping for AI cybersecurity, safety, and responsibility; confirm exact ETSI designation before formal citation |

## AIDEFEND AI defense mapping

AIDEFEND is useful as a defensive complement to threat-oriented AI security resources. It organizes countermeasures across the AI security lifecycle, including threat modeling, preventive hardening, runtime detection, containment, incident response, and recovery. Its stated mappings include MITRE ATLAS, MITRE D3FEND, MITRE ATT&CK, MAESTRO, OWASP LLM Top 10, OWASP ML Security Top 10, OWASP Agentic AI Top 10, NIST Adversarial Machine Learning, Cisco Integrated AI Security and Safety Framework, Google Secure AI Framework, and Databricks AI Security Framework.

| AIDEFEND use case | Suggested mapping in this repository |
| --- | --- |
| Defensive technique catalog | Translate AI threats into practical safeguards and controls |
| Threat-to-defense mapping | Link MITRE ATLAS and OWASP risks to mitigation, detection, and recovery actions |
| AI security architecture | Support layered controls for AI applications, ML systems, and AI agents |
| Detection and containment | Identify runtime controls and response actions for AI-specific abuse |
| Assurance and gap assessment | Compare existing controls against multiple AI security frameworks |

## IBM AI security, governance, and trustworthy AI resources

IBM's AI security and trustworthy AI resources are useful because they cover both technical AI security testing and governance evidence. ART supports adversarial robustness testing and defenses. AIF360, AIX360, AI FactSheets 360, and UQ360 support fairness, explainability, transparency, provenance, and uncertainty management. AI Risk Atlas and watsonx.governance support enterprise risk taxonomy, governance workflows, compliance monitoring, and operational oversight.

| IBM resource | Suggested mapping in this repository |
| --- | --- |
| Adversarial Robustness Toolbox | Map to AI red teaming, adversarial ML testing, model hardening, runtime detection, and robustness assurance |
| AI Fairness 360 | Map to fairness testing, bias detection, bias mitigation, responsible AI evidence, and model validation |
| AI Explainability 360 | Map to explainability controls, model transparency, decision auditability, and stakeholder assurance |
| AI FactSheets 360 | Map to AI documentation, supplier declarations, provenance, audit trails, accountability, and governance evidence |
| Uncertainty Quantification 360 | Map to model reliability, confidence communication, uncertainty-aware decisions, and safety cases |
| AI Risk Atlas and Risk Atlas Nexus | Map to AI risk taxonomy, governance mappings, compliance workflows, risk resources, and mitigation planning |
| watsonx.governance | Map to operational AI lifecycle governance, regulatory compliance, model monitoring, and enterprise audit evidence |

## Practical use

Use these frameworks together rather than as substitutes:

1. Use NIST AI RMF, IBM AI Risk Atlas, and ISO/IEC 23894 for risk governance.
2. Use OWASP, MITRE ATLAS, ETSI SAI, Google SAIF, AIDEFEND, and IBM ART for technical security engineering.
3. Use CSA AI Controls Matrix, ETSI TS 103 732, AIDEFEND, IBM AI FactSheets 360, IBM watsonx.governance, and ISO/IEC 42001 for control evidence and assurance.
4. Use IBM AIF360, IBM AIX360, ETSI GR SAI 007, the EU AI Act, and OECD AI Principles for transparency, fairness, responsibility, and public-interest alignment.
5. Use CISA, NCSC, ETSI secure lifecycle guidance, and IBM governance tooling for secure implementation and ongoing oversight.

## Suggested control domains

| Domain | Example controls |
| --- | --- |
| AI asset inventory | Model registry, dataset inventory, API inventory, agent tool registry |
| Data security | Data provenance, access control, poisoning detection, sensitive-data filtering |
| Model security | Model artifact protection, model integrity checks, evaluation gates, rollback plans |
| Prompt and context security | Prompt injection defenses, retrieval filtering, instruction hierarchy, output validation |
| Agent security | Tool permissions, identity boundaries, memory control, sandboxing, human approval gates |
| Platform and hardware security | Trusted execution, secure boot, attestation, model artifact integrity, hardware root of trust |
| Privacy | Data minimization, privacy-preserving ML, sensitive data controls, privacy risk assessment |
| Transparency | Explainability evidence, traceability, model cards, decision logs, audit trails |
| Monitoring | Abuse detection, drift monitoring, jailbreak telemetry, model behavior logging |
| Incident response | AI incident taxonomy, playbooks, evidence capture, escalation paths |
| Vulnerability disclosure | AI vulnerability intake, coordinated disclosure, supplier coordination, PSIRT workflow |
| Assurance | Red teaming, independent evaluation, safety cases, audit evidence, continuous review |

## APA 7 references

AIDEFEND Framework Initiative. (2026). *AIDEFEND: AI security defense framework*. https://aidefend.net/

Bagehorn, F., Brimijoin, K., Daly, E. M., He, J., Hind, M., Garces-Erice, L., Giblin, C., Giurgiu, I., Martino, J., Nair, R., Piorkowski, D., Rawat, A., Richards, J., Rooney, S., Salwala, D., Tirupathi, S., Urbanetz, P., Varshney, K. R., Vejsbjerg, I., & Wolf-Bauwens, M. L. (2025). *AI Risk Atlas: Taxonomy and tooling for navigating AI risks and resources*. arXiv. https://arxiv.org/abs/2503.05780

Bellamy, R. K. E., Dey, K., Hind, M., Hoffman, S. C., Houde, S., Kannan, K., Lohia, P., Martino, J., Mehta, S., Mojsilovic, A., Nagar, S., Ramamurthy, K. N., Richards, J., Saha, D., Sattigeri, P., Singh, M., Varshney, K. R., & Zhang, Y. (2018). *AI Fairness 360: An extensible toolkit for detecting, understanding, and mitigating unwanted algorithmic bias*. arXiv. https://arxiv.org/abs/1810.01943

Cloud Security Alliance. (2024). *AI controls matrix*. https://cloudsecurityalliance.org/

Cybersecurity and Infrastructure Security Agency, National Security Agency, Federal Bureau of Investigation, National Cyber Security Centre, and international partners. (2023). *Guidelines for secure AI system development*. https://www.cisa.gov/

European Telecommunications Standards Institute. (2019). *ETSI TR 103 621: Cyber security for consumer Internet of Things: Guide to implementing ETSI EN 303 645*. https://www.etsi.org/

European Telecommunications Standards Institute. (2020). *ETSI EN 303 645: Cyber security for consumer Internet of Things: Baseline requirements*. https://www.etsi.org/

European Telecommunications Standards Institute. (2020). *ETSI GR SAI 004: Securing artificial intelligence: Problem statement*. https://www.etsi.org/

European Telecommunications Standards Institute. (2021). *ETSI GR SAI 005: Securing artificial intelligence: Mitigation strategy report*. https://www.etsi.org/

European Telecommunications Standards Institute. (2021). *ETSI GR SAI 006: Securing artificial intelligence: The role of hardware in security of AI*. https://www.etsi.org/

European Telecommunications Standards Institute. (2021). *ETSI TS 103 701: Cyber security assessment for consumer Internet of Things*. https://www.etsi.org/

European Telecommunications Standards Institute. (2022). *ETSI GR SAI 007: Securing artificial intelligence: Explicability and transparency of AI processing*. https://www.etsi.org/

European Telecommunications Standards Institute. (2022). *ETSI GR SAI 008: Securing artificial intelligence: Privacy aspects of AI / ML systems*. https://www.etsi.org/

European Telecommunications Standards Institute. (2023). *ETSI GR SAI 009: Securing artificial intelligence: AI computing platform security framework*. https://www.etsi.org/

European Telecommunications Standards Institute. (2023). *ETSI GR SAI 010: Securing artificial intelligence: AI-based security and security of AI ecosystem*. https://www.etsi.org/

European Telecommunications Standards Institute. (2024). *ETSI GR SAI 011: Securing artificial intelligence: Multi-party coordinated vulnerability disclosure for AI*. https://www.etsi.org/

European Telecommunications Standards Institute. (2024). *ETSI TS 103 732: Securing artificial intelligence: Security baseline for AI models and systems*. https://www.etsi.org/

European Union. (2024). *Artificial Intelligence Act*. https://artificialintelligenceact.eu/

Ghosh, S., Liao, Q. V., Ramamurthy, K. N., Navratil, J., Sattigeri, P., Varshney, K. R., & Zhang, Y. (2021). *Uncertainty Quantification 360: A holistic toolkit for quantifying and communicating the uncertainty of AI*. arXiv. https://arxiv.org/abs/2106.01410

Google. (2023). *Secure AI framework*. https://saif.google/

IBM. (2023). *watsonx.governance*. https://www.ibm.com/products/watsonx-governance

International Organization for Standardization. (2023). *ISO/IEC 23894:2023 Artificial intelligence: Guidance on risk management*. https://www.iso.org/

International Organization for Standardization. (2023). *ISO/IEC 42001:2023 Artificial intelligence: Management system*. https://www.iso.org/

MITRE. (2020). *MITRE ATLAS: Adversarial threat landscape for artificial-intelligence systems*. https://atlas.mitre.org/

National Institute of Standards and Technology. (2023). *Artificial intelligence risk management framework (AI RMF 1.0)*. https://www.nist.gov/itl/ai-risk-management-framework

National Institute of Standards and Technology. (2024). *Artificial intelligence risk management framework: Generative artificial intelligence profile*. https://www.nist.gov/itl/ai-risk-management-framework

Nicolae, M.-I., Sinn, M., Tran, M. N., Buesser, B., Rawat, A., Wistuba, M., Zantedeschi, V., Baracaldo, N., Chen, B., Ludwig, H., Molloy, I. M., & Edwards, B. (2018). *Adversarial Robustness Toolbox v1.0.0*. arXiv. https://arxiv.org/abs/1807.01069

Organisation for Economic Co-operation and Development. (2019). *OECD principles on artificial intelligence*. https://oecd.ai/

OWASP Foundation. (2025). *OWASP top 10 for large language model applications*. https://owasp.org/www-project-top-10-for-large-language-model-applications/

OWASP Foundation. (2023). *Machine learning security top 10*. https://owasp.org/

Richards, J., Piorkowski, D., Hind, M., Houde, S., Mojsilovic, A., & Varshney, K. R. (2020). *AI FactSheets 360*. IBM Research. https://aifs360.res.ibm.com/

Vijay Arya, R., Bellamy, K. E., Chen, P.-Y., Dhurandhar, A., Hind, M., Hoffman, S. C., Houde, S., Liao, Q. V., Luss, R., Mojsilovic, A., Mourad, S., Pedemonte, P., Raghavendra, R., Richards, J., Sattigeri, P., Shanmugam, K., Singh, M., Varshney, K. R., Wei, D., & Zhang, Y. (2019). *One explanation does not fit all: A toolkit and taxonomy of AI explainability techniques*. arXiv. https://arxiv.org/abs/1909.03012