# AI Threat Modeling Frameworks

This page lists frameworks and methods for identifying, structuring, and prioritizing threats against AI systems, LLM applications, AI agents, model supply chains, data pipelines, and AI-enabled cyber operations.

## Framework comparison

| # | Vendor / organization | Framework / method | Goal / function | Release date | Open source / public | Primary use |
| --- | --- | --- | --- | --- | --- | --- |
| 1 | MITRE | ATLAS | Catalog adversarial tactics and techniques against AI systems | 2020 | Yes | Threat-informed AI security analysis |
| 2 | OWASP | Top 10 for LLM Applications | Identify and prioritize LLM application security risks | 2023, updated 2025 | Yes | LLM threat modeling checklist |
| 3 | OWASP | Machine Learning Security Top 10 | Identify major ML system security risks | 2023 | Yes | ML threat modeling |
| 4 | Microsoft | STRIDE for AI and AI threat modeling guidance | Apply spoofing, tampering, repudiation, information disclosure, denial of service, and elevation of privilege to AI systems | 2023 onwards | Yes | Architecture-level AI threat modeling |
| 5 | AI STRIDE | AI STRIDE Threat Model | Adapt STRIDE to AI systems, LLM applications, RAG pipelines, model supply chains, and AI agents | 2026 | Yes | Practical AI threat modeling checklist |
| 6 | Google | Secure AI Framework | Secure AI systems across infrastructure, supply chain, detection, and response | 2023 | Yes | Secure architecture review |
| 7 | NIST | AI RMF | Structure AI risks through Govern, Map, Measure, and Manage | 2023 | Yes | Risk-based threat analysis |
| 8 | NIST | Adversarial Machine Learning taxonomy and guidance | Classify attacks and mitigations for predictive and generative AI | 2024 | Yes | Adversarial ML risk analysis |
| 9 | Cloud Security Alliance | AI Controls Matrix | Map AI risks to controls and assurance evidence | 2024 | Yes | Control-driven threat modeling |
| 10 | ENISA | AI cybersecurity guidance | Identify cybersecurity threats and controls across the AI lifecycle | 2020 onwards | Yes | EU policy and operational security mapping |
| 11 | CISA, NSA, FBI, UK NCSC, and partners | Guidelines for Secure AI System Development | Identify secure AI design, development, deployment, and operation requirements | 2023 | Yes | Secure lifecycle threat modeling |
| 12 | MITRE | ATT&CK | Model conventional adversary behavior around AI infrastructure and enterprise environments | 2013 onwards | Yes | Enterprise attack path mapping |
| 13 | Lockheed Martin | Cyber Kill Chain | Structure attack lifecycle analysis | 2011 | Public | High-level attack sequence analysis |
| 14 | DREAD | Damage, reproducibility, exploitability, affected users, discoverability scoring | Older Microsoft-origin method | Public | Risk scoring support |
| 15 | PASTA | Process for Attack Simulation and Threat Analysis | Business-risk-driven threat modeling | 2012 | Public method | Risk-centric threat modeling |
| 16 | LINDDUN | Privacy threat modeling | Model privacy threats such as linkability, identifiability, and disclosure | 2010 onwards | Yes | AI privacy threat analysis |

## AI STRIDE Threat Model

AI STRIDE adapts the classic STRIDE model to AI systems. It is useful because many AI risks are not limited to the model itself. They emerge across prompts, context windows, retrieval pipelines, plugins, tools, model registries, datasets, agents, telemetry, and human approval workflows.

| STRIDE category | AI-specific threat examples | AI system layer | Example mitigations |
| --- | --- | --- | --- |
| Spoofing | Fake user identity, forged tool identity, spoofed model endpoint, fake retrieval source, impersonated agent | Identity, API, RAG, agent and tool layer | Strong identity, workload identity, signed tools, source authentication, model endpoint verification |
| Tampering | Prompt injection, RAG corpus poisoning, training data poisoning, model artifact modification, unsafe plugin modification | Prompt, data, model, supply chain, plugin layer | Input validation, retrieval filtering, signed artifacts, dataset provenance, integrity checks, CI/CD controls |
| Repudiation | No record of agent decisions, missing prompt logs, weak approval evidence, inability to prove who triggered tool use | Logging, audit, governance, human-in-the-loop layer | Immutable logs, prompt and response retention, approval records, trace IDs, audit-ready evidence |
| Information disclosure | System prompt leakage, sensitive data leakage, model inversion, membership inference, retrieval leakage, secret exposure through tool output | Model, prompt, data, retrieval, tool layer | Data minimization, output filtering, secret scanning, access control, privacy testing, retrieval permissions |
| Denial of service | Token exhaustion, prompt flooding, expensive tool loops, model endpoint overload, embedding index abuse, agent recursion | Application, model serving, agent, infrastructure layer | Rate limiting, quotas, circuit breakers, cost controls, recursion limits, workload isolation |
| Elevation of privilege | Agent uses unauthorized tools, prompt bypasses approval gate, model triggers privileged API, cross-tenant access through RAG or plugin | Agent, tool, API, authorization layer | Least privilege, policy-as-code, scoped tool tokens, human approval gates, sandboxing, authorization checks |

## AI STRIDE checklist

| Question | STRIDE category | Why it matters |
| --- | --- | --- |
| Can an attacker impersonate a user, tool, model, data source, or agent? | Spoofing | AI systems often trust identity claims from APIs, plugins, documents, and tool manifests |
| Can untrusted input modify prompts, retrieved content, datasets, model artifacts, or tool parameters? | Tampering | AI systems are vulnerable to integrity attacks across both data and instructions |
| Can the organization reconstruct who asked what, what the model answered, and which tool was used? | Repudiation | AI incidents require evidence, traceability, and accountability |
| Can sensitive information leak through model output, logs, retrieval, embeddings, or tool calls? | Information disclosure | AI systems can expose confidential data through direct and indirect channels |
| Can attackers exhaust tokens, cost budgets, compute, API quotas, or agent execution loops? | Denial of service | AI systems can be attacked through resource amplification and expensive reasoning loops |
| Can the model or agent gain more permissions than intended? | Elevation of privilege | AI agents often combine identity, planning, tools, and automation in ways that can bypass controls |

## AI STRIDE mapping to control families

| Control family | Relevant STRIDE categories | Example evidence |
| --- | --- | --- |
| Identity and access management | Spoofing, elevation of privilege | Role matrix, service identity list, scoped token policy, tool authorization design |
| Secure prompt and context handling | Tampering, information disclosure, elevation of privilege | Prompt-injection tests, context filtering rules, system prompt protection evidence |
| Data and model supply chain | Tampering, information disclosure | Dataset provenance, model hash, signed artifacts, model registry controls |
| Agent tool governance | Spoofing, tampering, denial of service, elevation of privilege | Tool registry, permission scopes, approval gates, sandbox policy, execution limits |
| Monitoring and auditability | Repudiation, information disclosure, denial of service | Prompt logs, response logs, tool-call logs, trace IDs, incident evidence records |
| Resilience and cost protection | Denial of service | Rate limits, quotas, timeout rules, recursion limits, circuit breaker tests |
| Privacy and confidentiality | Information disclosure | Data classification, redaction rules, privacy tests, retrieval access reviews |

## AI-specific threat modeling layers

| Layer | Example threats |
| --- | --- |
| Business and mission layer | Unsafe use case, unlawful processing, mission dependency, systemic impact |
| User and identity layer | Account takeover, role confusion, privilege escalation, weak human approval gates |
| Prompt and context layer | Direct prompt injection, indirect prompt injection, context poisoning, instruction conflict |
| Retrieval layer | RAG corpus poisoning, malicious documents, embedding manipulation, source spoofing |
| Model layer | Model extraction, inversion, membership inference, jailbreaks, adversarial examples |
| Data layer | Training data poisoning, labeling compromise, sensitive-data leakage, data provenance gaps |
| Agent and tool layer | Excessive agency, tool misuse, unsafe delegation, hidden multi-step execution |
| Infrastructure layer | Insecure endpoints, exposed model registry, compromised CI/CD, secrets leakage |
| Supply-chain layer | Malicious models, vulnerable dependencies, unsafe plugins, compromised datasets |
| Monitoring and response layer | Logging gaps, weak abuse detection, untested rollback, incident evidence loss |

## Suggested workflow

1. Define the AI system boundary, including users, models, tools, data stores, APIs, agents, and external services.
2. Identify the AI lifecycle stage: design, data collection, training, fine-tuning, deployment, inference, monitoring, or retirement.
3. Map threats using MITRE ATLAS, OWASP LLM Top 10, AI STRIDE, STRIDE, and AI RMF risk categories.
4. Score risks using likelihood, exploitability, business impact, safety impact, legal impact, and control maturity.
5. Map mitigations to controls, owners, evidence, and test cases.
6. Validate controls through AI red teaming, security testing, abuse monitoring, and incident exercises.

## Threat modeling questions

| Question | Why it matters |
| --- | --- |
| What decisions can the AI system influence? | Determines safety, legal, and mission impact |
| What tools can the model or agent call? | Identifies excessive agency and privilege risks |
| What data can the system retrieve or modify? | Identifies confidentiality and integrity risks |
| Can untrusted content enter the context window? | Identifies prompt injection and RAG poisoning risks |
| Can outputs trigger real-world actions? | Identifies automation and human approval requirements |
| Are logs sufficient for incident response? | Determines forensic readiness and accountability |
| Can the model be replaced or rolled back? | Determines resilience and recovery capability |

## APA 7 references

Cybersecurity and Infrastructure Security Agency, National Security Agency, Federal Bureau of Investigation, National Cyber Security Centre, and international partners. (2023). *Guidelines for secure AI system development*. https://www.cisa.gov/

European Union Agency for Cybersecurity. (2020). *Artificial intelligence cybersecurity challenges*. https://www.enisa.europa.eu/

Google. (2023). *Secure AI framework*. https://saif.google/

LINDDUN. (n.d.). *LINDDUN privacy threat modeling*. https://www.linddun.org/

MITRE. (n.d.). *MITRE ATT&CK*. https://attack.mitre.org/

MITRE. (n.d.). *MITRE ATLAS: Adversarial threat landscape for artificial-intelligence systems*. https://atlas.mitre.org/

National Institute of Standards and Technology. (2023). *Artificial intelligence risk management framework (AI RMF 1.0)*. https://doi.org/10.6028/NIST.AI.100-1

National Institute of Standards and Technology. (2024). *Adversarial machine learning: A taxonomy and terminology of attacks and mitigations*. https://csrc.nist.gov/

Open Worldwide Application Security Project. (2025). *OWASP Top 10 for large language model applications*. https://genai.owasp.org/

Shostack, A. (2014). *Threat modeling: Designing for security*. Wiley.

UcedaVelez, T., & Morana, M. M. (2015). *Risk centric threat modeling: Process for attack simulation and threat analysis*. Wiley.