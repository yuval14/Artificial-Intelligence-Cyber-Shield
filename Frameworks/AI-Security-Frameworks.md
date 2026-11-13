# AI Security Frameworks

This page lists major AI security frameworks, taxonomies, standards, and control catalogs that help organizations protect AI systems, models, agents, data pipelines, AI-enabled services, connected products, and AI-enabled cyber defense capabilities.

## Framework comparison

| # | Vendor / organization | Framework / resource | Goal / function | Release date | Open source / public | Primary use |
| --- | --- | --- | --- | --- | --- | --- |
| 1 | NIST | AI Risk Management Framework 1.0 | Manage AI risks through Govern, Map, Measure, and Manage functions | 2023 | Yes | Enterprise AI risk management and governance |
| 2 | NIST | AI RMF Generative AI Profile | Apply the AI RMF to generative AI risks and controls | 2024 | Yes | GenAI risk management |
| 3 | MITRE | ATLAS | Knowledge base of adversary tactics and techniques against AI-enabled systems | 2020 | Yes | AI threat modeling, detection, red teaming, and CTI |
| 4 | OWASP | [Top 10 for LLM Applications](https://genai.owasp.org/resource/owasp-genai-llm-top-10-2026/) | Identify leading security risks in LLM applications | 2026 | Yes | Secure LLM application design and assessment |
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
| 25 | ETSI | [ETSI TS 104 223 V1.1.1](https://www.etsi.org/deliver/etsi_TS/104200_104299/104223/01.01.01_60/ts_104223v010101p.pdf) | Establishes baseline security requirements for AI models and systems and formed the basis for EN 304 223 | 2025-04 | Yes | Technical AI security baseline |
| 26 | ETSI | ETSI EN 303 645 | Baseline cybersecurity provisions for consumer IoT devices, relevant to edge AI and AI-enabled connected products | 2020, updated later | Yes | Consumer IoT and edge-AI security |
| 27 | ETSI | ETSI TS 103 701 | Conformity assessment specification for ETSI EN 303 645 | 2021 | Yes | IoT and edge-AI security testing |
| 28 | ETSI | ETSI TR 103 621 | Implementation guidance for consumer IoT cybersecurity | 2019 | Yes | Secure implementation guidance |
| 29 | ETSI | [ETSI EN 304 223 V2.1.1](https://www.etsi.org/deliver/etsi_en/304200_304299/304223/02.01.01_60/en_304223v020101p.pdf) | Defines lifecycle cybersecurity requirements for AI models and systems | 2025-12 | Yes | Technical security requirements for design, development, deployment, maintenance, and end of life |
| 30 | AIDEFEND Framework Initiative | AIDEFEND, AI Security Defense Framework | Structured AI security defense knowledge base of countermeasures for AI and ML systems, mapped to major AI security frameworks | 2026 | Yes, CC BY 4.0 | AI defense architecture, control mapping, detection, containment, incident response, and recovery |
| 31 | Pillar Security | SAIL, Secure AI Lifecycle Framework V2 | Practical lifecycle-oriented strategy for managing AI-specific and agentic AI risks across policy, discovery, posture, red teaming, runtime controls, sandboxing, and governance | 2026, updated 08 July 2026 | Yes / public | AI security roadmap, agentic risk assessment, lifecycle control mapping, RFP support, and compliance checklisting |
| 32 | IBM | Adversarial Robustness Toolbox | Open source library for adversarial ML attacks, defenses, robustness testing, certification, and runtime detection | 2018 | Yes, MIT License | AI security testing, adversarial robustness, red teaming, and model hardening |
| 33 | IBM | AI Fairness 360 | Open source toolkit for detecting, explaining, and mitigating unwanted algorithmic bias in datasets and ML models | 2018 | Yes, Apache 2.0 | Fairness testing, bias mitigation, and responsible AI assurance |
| 34 | IBM | AI Explainability 360 | Open source toolkit and taxonomy for explaining AI model decisions using multiple explanation methods | 2019 | Yes, Apache 2.0 | Explainability, transparency, auditability, and model assurance |
| 35 | IBM | AI FactSheets 360 | Research framework and toolkit for documenting AI services through supplier-style declarations of conformity | 2018 | Yes | AI transparency, provenance, accountability, and governance evidence |
| 36 | IBM | Uncertainty Quantification 360 | Open source toolkit for quantifying, evaluating, improving, and communicating AI uncertainty | 2021 | Yes, Apache 2.0 | Reliability assessment, uncertainty communication, and trustworthy AI engineering |
| 37 | IBM | AI Risk Atlas and Risk Atlas Nexus | Taxonomy and tooling for navigating AI risks, resources, benchmarks, datasets, mitigations, and governance mappings | 2025 | Yes | AI risk taxonomy, governance mapping, compliance workflows, and mitigation planning |
| 38 | IBM | watsonx.governance | Enterprise AI governance platform for lifecycle governance, risk management, compliance, monitoring, and model oversight | 2023 | Public / commercial platform | Operational AI governance, regulatory compliance, model monitoring, and audit evidence |

## OWASP and CSA guidance

Use the [OWASP LLM Top 10 (2026)](https://genai.owasp.org/resource/owasp-genai-llm-top-10-2026/) for LLM application risks and the [OWASP Top 10 for Agentic Applications](https://genai.owasp.org/initiatives/agentic-security-initiative/) for agent-specific risks. Include the edition alongside risk identifiers in assessments because identifiers and rankings can change.

For implementation, see [agent runtime enforcement](AI-Agent-Security.md#agent-runtime-enforcement). For control ownership and audit evidence, see [CSA STAR for AI](../Organizational-Certifications/AI-Organizational-Certifications.md#cloud-security-alliance-star-for-ai).

### OWASP data and infrastructure security

| Resource | Scope | Practical use |
| --- | --- | --- |
| [GenAI Data Security Best Practices v2 - Part 1](https://genai.owasp.org/resource/genai-data-security-best-practices-v2-part1/) (November 3, 2026) | First installment of the implementation playbook, including AI data security posture management (AI-DSPM) | Define an operating model, stage the rollout, select operational metrics, and integrate findings with security operations. |
| [OWASP Top 10 Neocloud & AI Data Center Security Risks](https://owasp.org/projects/top-10-neocloud-and-ai-data-center-security-risks) (2026) | OWASP incubator project covering shared AI compute infrastructure, including accelerators, network fabrics, firmware, storage, and management planes | Assess provider isolation and management-plane controls during procurement and architecture reviews. |

## NIST AI security updates (September-November 2026)

| Published | Resource |
| --- | --- |
| 2026-11-09 | [NIST SP 2400-102 E2026](https://csrc.nist.gov/pubs/sp/2400-102/e2026/ipd) - initial public draft on adversarial machine learning, with an attack taxonomy and mitigations for agentic superintelligence systems. Public comments due December 18, 2026. |
| 2026-11-02 | [IR 8621](https://doi.org/10.6028/NIST.IR.8621) - final workshop report |
| 2026-10-27 | [Agent identity design tenets](https://www.nist.gov/blogs/cybersecurity-insights/design-tenets-agent-identity-management-systems) - proposed design guidance |
| 2026-10-16 | [Incident readiness and response](https://www.nist.gov/document/keypracticesforincidentreadinessandresponseinsuperintelligence-trainingandevaluation) - joint voluntary guidance |
| 2026-09-29 | [Agent identity concept paper feedback](https://www.nist.gov/news-events/news/2026/09/comments-software-and-agentic-ai-identity-concept-paper) - NCCoE public-comment summary |
| 2026-09-17 | [GLM-5.3 cyber assessment](https://www.nist.gov/news-events/news/2026/09/caisis-assessment-zais-glm-53-cyber-capabilities) - model capability evaluation |

See [AI Agent Security](AI-Agent-Security.md) for identity controls and [AI Incident Response](../AI-Incident-Response/AI-Incident-Response-Standards-and-Frameworks.md) for response guidance. The GLM-5.3 assessment describes performance on selected cyber tasks under its evaluation setup. Use it as threat context and record the benchmark, harness, and budget when comparing results.

### NIST Cyber AI Profile and control overlays

| Resource | Status | Practical use |
| --- | --- | --- |
| [NIST IR 8596 - Cyber AI Profile](https://csrc.nist.gov/pubs/ir/8596/iprd) | Initial preliminary draft, December 2025 | Apply the NIST Cybersecurity Framework to securing AI systems, using AI for cyber defense, and countering AI-enabled attacks. |
| [NIST IR 8607 - Cyber AI Profile Workshop #2](https://csrc.nist.gov/pubs/ir/8607/final) | Final workshop report, August 2026 | Review stakeholder feedback on the draft profile and its implementation. |
| [NIST SP 800-53 Control Overlays for Super Intelligence Systems (COSIS)](https://csrc.nist.gov/Projects/cosis) | Project in development, formerly COSAiS. A concept paper and discussion outline are available. | Track how SP 800-53 controls are tailored to AI use cases and assets such as training data, model weights, and configuration. |

## CERT-In AI security auditing guidelines

CERT-In's [AI Security Auditing Guidelines](https://www.cert-in.org.in/PDF/AI_Security_Auditing_Guidelines.pdf) (CISG-2026-04, November 4, 2026) define a risk-based approach to auditing AI systems across their lifecycle.

| Audit step | What to assess |
| --- | --- |
| Scope and risk tier | Inventory AI systems and classify each by risk. |
| Controls and evidence | Check governance, security controls, data and model provenance, and audit records. |
| Follow-up | Use the assigned tier to determine audit depth, evidence requirements, and frequency. |

Use the applicability matrix to determine which requirements apply in the Indian context.

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
| [ETSI EN 304 223 V2.1.1](https://www.etsi.org/deliver/etsi_en/304200_304299/304223/02.01.01_60/en_304223v020101p.pdf) | Published lifecycle baseline for AI models and systems, based on ETSI TS 104 223 V1.1.1 |
| [ETSI TS 104 033 V1.1.1](https://www.etsi.org/deliver/etsi_ts/104000_104099/104033/01.01.01_60/ts_104033v010101p.pdf) | Published May 2026. Assess AI computing platform security and use Annex F to map platform controls to EN 304 223. |
| ETSI EN 303 645 | Security baseline for consumer IoT and edge-AI devices |
| ETSI TS 103 701 | Conformity assessment for consumer IoT cybersecurity controls |
| ETSI TR 103 621 | Implementation guidance for consumer IoT cybersecurity controls |

### ETSI work items in development

| Work item | Scope | Status |
| --- | --- | --- |
| [ETSI TS 104 328](https://portal.etsi.org/webapp/WorkProgram/Report_WorkItem.asp?WKI_ID=79428) | Additional baseline cybersecurity requirements for agentic AI systems, building on EN 304 223 | Work item adopted October 2026 |
| [ETSI TS 104 330](https://portal.etsi.org/webapp/WorkProgram/Report_WorkItem.asp?WKI_ID=79399) | Application of EN 304 223 to secure code generation with generative AI and prevention of misuse | Work item adopted October 2026 |

## ISO/IEC AI cybersecurity, robustness, and privacy

| Resource | Status | Practical use |
| --- | --- | --- |
| [ISO/IEC 27090:2026](https://www.iso.org/standard/27090) | Published October 2026. Public preview, paid full text. | Identify, detect, and mitigate AI-specific threats across the lifecycle, including data poisoning and model theft. |
| [ISO/IEC 24029-2:2023](https://www.iso.org/standard/79804.html) | Published August 2023. Public preview, paid full text. | Select and apply formal methods to assess specified robustness properties of neural networks. |
| [ISO/IEC FDIS 27091](https://www.iso.org/standard/56582.html) | Final Draft International Standard | Track guidance for addressing privacy risks in AI systems and machine learning models. |

## AIDEFEND AI defense mapping

AIDEFEND is useful as a defensive complement to threat-oriented AI security resources. It organizes countermeasures across the AI security lifecycle, including threat modeling, preventive hardening, runtime detection, containment, incident response, and recovery. Its stated mappings include MITRE ATLAS, MITRE D3FEND, MITRE ATT&CK, MAESTRO, OWASP LLM Top 10, OWASP ML Security Top 10, OWASP Agentic AI Top 10, NIST Adversarial Machine Learning, Cisco Integrated AI Security and Safety Framework, Google Secure AI Framework, and Databricks AI Security Framework.

| AIDEFEND use case | Suggested mapping in this repository |
| --- | --- |
| Defensive technique catalog | Translate AI threats into practical safeguards and controls |
| Threat-to-defense mapping | Link MITRE ATLAS and OWASP risks to mitigation, detection, and recovery actions |
| AI security architecture | Support layered controls for AI applications, ML systems, and AI agents |
| Detection and containment | Identify runtime controls and response actions for AI-specific abuse |
| Assurance and gap assessment | Compare existing controls against multiple AI security frameworks |

## Pillar Security SAIL lifecycle mapping

SAIL, the Secure AI Lifecycle Framework V2, is useful as a lifecycle-oriented framework for operationalizing AI and agentic AI security. It covers the full AI journey from policy and discovery through posture assessment, agentic red teaming, runtime controls, sandboxing, and governance. The framework is especially relevant for organizations that need a common language between development, MLOps, security, and governance teams.

| SAIL phase | Suggested mapping in this repository |
| --- | --- |
| AI Policy | AI governance, risk tolerance, autonomy classification, action authorization, agentic identity policy, and secure experimentation |
| AI Discovery | AI asset inventory, third-party AI and agentic integrations, data flow mapping, MCP server discovery, and shadow agent visibility |
| Agentic Posture | Agent configuration review, tool and connector scope analysis, memory and RAG dependency mapping, identity reachability, and posture drift analysis |
| Agentic Red Teaming | Goal hijacking, prompt injection across tool chains, privilege escalation, reasoning manipulation, memory poisoning, and multi-agent workflow testing |
| Runtime Controls | Action-level authorization, least-privilege tool invocation, output validation, behavioral baselining, abuse detection, and emergency stop controls |
| Sandbox | Isolation of agent execution, network and filesystem boundaries, API/tool restrictions, rollback paths, and blast-radius reduction |
| Govern | Continuous monitoring, agent telemetry, anomaly detection, AI-specific incident response, decommissioning, credential rotation, and end-of-life audit evidence |

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
2. Use OWASP, MITRE ATLAS, ETSI SAI, Google SAIF, SAIL, AIDEFEND, and IBM ART for technical security engineering.
3. Use CSA AI Controls Matrix, ETSI EN 304 223, SAIL, AIDEFEND, IBM AI FactSheets 360, IBM watsonx.governance, and ISO/IEC 42001 for control evidence and assurance.
4. Use SAIL, OWASP Agentic AI guidance, MITRE ATLAS, and AIDEFEND for agentic AI lifecycle security, red teaming, runtime controls, sandboxing, and governance.
5. Use IBM AIF360, IBM AIX360, ETSI GR SAI 007, the EU AI Act, and OECD AI Principles for transparency, fairness, responsibility, and public-interest alignment.
6. Use CISA, NCSC, ETSI secure lifecycle guidance, and IBM governance tooling for secure implementation and ongoing oversight.

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

Indian Computer Emergency Response Team. (2026, November 4). *Artificial intelligence (AI) security auditing guidelines* (CISG-2026-04). https://www.cert-in.org.in/PDF/AI_Security_Auditing_Guidelines.pdf

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

European Telecommunications Standards Institute. (2025, April). *Securing artificial intelligence (SAI): Baseline cyber security requirements for AI models and systems* (ETSI TS 104 223 V1.1.1). https://www.etsi.org/deliver/etsi_TS/104200_104299/104223/01.01.01_60/ts_104223v010101p.pdf

European Telecommunications Standards Institute. (2025, December). *Securing artificial intelligence (SAI): Baseline cyber security requirements for AI models and systems* (ETSI EN 304 223 V2.1.1). https://www.etsi.org/deliver/etsi_en/304200_304299/304223/02.01.01_60/en_304223v020101p.pdf

European Telecommunications Standards Institute. (2026, May). *Securing artificial intelligence (SAI): Security requirements for an artificial intelligence computing platform* (ETSI TS 104 033 V1.1.1). https://www.etsi.org/deliver/etsi_ts/104000_104099/104033/01.01.01_60/ts_104033v010101p.pdf

European Union. (2024). *Artificial Intelligence Act*. https://artificialintelligenceact.eu/

Ghosh, S., Liao, Q. V., Ramamurthy, K. N., Navratil, J., Sattigeri, P., Varshney, K. R., & Zhang, Y. (2021). *Uncertainty Quantification 360: A holistic toolkit for quantifying and communicating the uncertainty of AI*. arXiv. https://arxiv.org/abs/2106.01410

Google. (2023). *Secure AI framework*. https://saif.google/

IBM. (2023). *watsonx.governance*. https://www.ibm.com/products/watsonx-governance

International Organization for Standardization. (2023). *ISO/IEC 23894:2023 Artificial intelligence: Guidance on risk management*. https://www.iso.org/

International Organization for Standardization. (2023). *Artificial intelligence (AI): Assessment of the robustness of neural networks. Part 2: Methodology for the use of formal methods* (ISO/IEC 24029-2:2023). https://www.iso.org/standard/79804.html

International Organization for Standardization. (2023). *ISO/IEC 42001:2023 Artificial intelligence: Management system*. https://www.iso.org/

International Organization for Standardization. (2026). *Cybersecurity: Artificial intelligence (AI): Addressing security threats and compromises to AI systems* (ISO/IEC 27090:2026). https://www.iso.org/standard/27090

Megas, K., Cuthill, B., Dotter, M., Garris, M., Khemani, I., Patrick, B., Schiro, N., Snyder, J. N., & Zarei, M. (2025). *Cybersecurity Framework Profile for Artificial Intelligence (Cyber AI Profile): NIST Community Profile* (NIST IR 8596, initial preliminary draft). National Institute of Standards and Technology. https://csrc.nist.gov/pubs/ir/8596/iprd

Megas, K., Cuthill, B., Sames, C., & Snyder, J. (2026). *Workshop summary report for "Cyber AI Profile" hybrid workshop #2* (NIST IR 8607). National Institute of Standards and Technology. https://csrc.nist.gov/pubs/ir/8607/final

MITRE. (2020). *MITRE ATLAS: Adversarial threat landscape for artificial-intelligence systems*. https://atlas.mitre.org/

National Institute of Standards and Technology. (2023). *Artificial intelligence risk management framework (AI RMF 1.0)*. https://www.nist.gov/itl/ai-risk-management-framework

National Institute of Standards and Technology. (2024). *Artificial intelligence risk management framework: Generative artificial intelligence profile*. https://www.nist.gov/itl/ai-risk-management-framework

Nicolae, M.-I., Sinn, M., Tran, M. N., Buesser, B., Rawat, A., Wistuba, M., Zantedeschi, V., Baracaldo, N., Chen, B., Ludwig, H., Molloy, I. M., & Edwards, B. (2018). *Adversarial Robustness Toolbox v1.0.0*. arXiv. https://arxiv.org/abs/1807.01069

Organisation for Economic Co-operation and Development. (2019). *OECD principles on artificial intelligence*. https://oecd.ai/

OWASP Foundation. (2025). *OWASP top 10 for large language model applications*. https://owasp.org/www-project-top-10-for-large-language-model-applications/

OWASP Foundation. (2023). *Machine learning security top 10*. https://owasp.org/

OWASP Foundation. (2026). *OWASP Top 10 neocloud & AI data center security risks*. https://owasp.org/projects/top-10-neocloud-and-ai-data-center-security-risks

OWASP GenAI Security Project. (2026, November 3). *GenAI data security best practices v2 - Part 1*. https://genai.owasp.org/resource/genai-data-security-best-practices-v2-part1/

Pillar Security. (2026). *SAIL: Secure AI lifecycle framework V2*. https://www.pillar.security/sail

Richards, J., Piorkowski, D., Hind, M., Houde, S., Mojsilovic, A., & Varshney, K. R. (2020). *AI FactSheets 360*. IBM Research. https://aifs360.res.ibm.com/

Vassilev, A., Oprea, A., Fordyce, A., Davies, X., & Hamin, M. (2026). *Adversarial machine learning: A taxonomy and terminology of attacks and mitigations* (NIST SP 2400-102 E2026, initial public draft). National Institute of Standards and Technology. https://csrc.nist.gov/pubs/sp/2400-102/e2026/ipd

Vijay Arya, R., Bellamy, K. E., Chen, P.-Y., Dhurandhar, A., Hind, M., Hoffman, S. C., Houde, S., Liao, Q. V., Luss, R., Mojsilovic, A., Mourad, S., Pedemonte, P., Raghavendra, R., Richards, J., Sattigeri, P., Shanmugam, K., Singh, M., Varshney, K. R., Wei, D., & Zhang, Y. (2019). *One explanation does not fit all: A toolkit and taxonomy of AI explainability techniques*. arXiv. https://arxiv.org/abs/1909.03012
