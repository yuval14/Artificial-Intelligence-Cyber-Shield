# AI Agent Security

This page lists frameworks, control patterns, and security principles for AI agents. The focus is on systems that can reason across steps, use tools, call APIs, retrieve data, maintain memory, delegate tasks, or perform actions in digital or physical environments.

## Framework comparison

| # | Vendor / organization | Framework / resource | Goal / function | Release date | Open source / public | Primary use |
| --- | --- | --- | --- | --- | --- | --- |
| 1 | OWASP | Agentic AI Threats and Mitigations | Identify security risks unique to agentic AI systems | 2025 | Yes | Agent threat modeling and control design |
| 2 | Cloud Security Alliance | Agentic AI security and red teaming guidance | Address autonomy, identity, tool use, permissions, and multi-step risk | 2025 | Yes | Enterprise agent security and red teaming |
| 3 | Microsoft | AI agent security guidance | Secure agent identity, tool use, data access, and human oversight | 2024 onwards | Yes | Enterprise agent deployment |
| 4 | Google | Secure AI Framework | Secure AI systems, including agentic workflows, supply chain, monitoring, and response | 2023 | Yes | Secure architecture baseline |
| 5 | NIST | AI RMF and GenAI Profile | Govern, map, measure, and manage agentic AI risks | 2023, 2024 | Yes | Risk governance for AI agents |
| 6 | MITRE | ATLAS | Map adversary behavior against AI systems and agent workflows | 2020 | Yes | Threat-informed agent defense |
| 7 | OWASP | Top 10 for LLM Applications | Address prompt injection, insecure output handling, sensitive information disclosure, and excessive agency | 2023, updated 2025 | Yes | LLM agent application security |
| 8 | CISA, NSA, FBI, UK NCSC, and partners | Guidelines for Secure AI System Development | Secure design, development, deployment, and operation of AI systems | 2023 | Yes | Secure AI lifecycle controls |
| 9 | Model Context Protocol community | MCP security guidance and threat discussions | Secure tool connections, context exchange, and server-client trust boundaries | 2024 onwards | Public | MCP and tool ecosystem security |
| 10 | ETSI | Securing Artificial Intelligence reports and guidance | Address AI threats, data supply-chain risks, security testing, and mitigation strategies | 2019 onwards | Public standards and reports | AI system and agent security governance |

## Agent-specific risk areas

| Risk area | Description | Example control |
| --- | --- | --- |
| Excessive agency | Agent can perform high-impact actions without sufficient restriction | Least-privilege tools, approval gates, policy engine |
| Tool misuse | Agent calls unsafe or unintended tools | Tool allowlists, parameter validation, execution sandbox |
| Identity confusion | Agent acts with unclear or overbroad identity | Dedicated service identity, scoped tokens, user delegation boundaries |
| Memory poisoning | Long-term or session memory is manipulated | Memory validation, source labels, retention limits |
| RAG poisoning | Retrieved content injects malicious instructions | Retrieval filtering, trusted-source ranking, instruction separation |
| Prompt injection | Untrusted content overrides developer or system intent | Instruction hierarchy, context isolation, prompt-injection detection |
| Hidden delegation | Agent delegates actions to other agents or tools without visibility | Delegation logging, explicit authorization, chain-of-action tracing |
| Unsafe autonomy | Agent continues task execution despite uncertainty or elevated risk | Stop conditions, confidence thresholds, human-in-the-loop controls |
| Data exfiltration | Agent leaks sensitive data through outputs or tool calls | Data classification, output filtering, DLP, access controls |
| Weak observability | Actions cannot be reconstructed after an incident | Structured logs, tool-call audit trail, trace IDs, evidence retention |

## Agent Rule of One

Each AI agent should possess only one of the following three high-risk capabilities at a time:

1. Access to sensitive data.
2. Ability to execute external actions.
3. Ability to modify memory, policy, identity, or configuration.

If an agent requires more than one high-risk capability, add compensating controls such as human approval, separation of duties, sandboxing, rate limits, transaction signing, and independent monitoring.

## APA 7 references

Cloud Security Alliance. (2025). *Agentic AI security guidance*. https://cloudsecurityalliance.org/

Cybersecurity and Infrastructure Security Agency, National Security Agency, Federal Bureau of Investigation, National Cyber Security Centre, and international partners. (2023). *Guidelines for secure AI system development*. https://www.cisa.gov/

European Telecommunications Standards Institute. (n.d.). *Securing Artificial Intelligence*. https://www.etsi.org/technologies/securing-artificial-intelligence

Google. (2023). *Secure AI framework*. https://saif.google/

MITRE. (n.d.). *MITRE ATLAS: Adversarial threat landscape for artificial-intelligence systems*. https://atlas.mitre.org/

National Institute of Standards and Technology. (2023). *Artificial intelligence risk management framework (AI RMF 1.0)*. https://doi.org/10.6028/NIST.AI.100-1

Open Worldwide Application Security Project. (2025). *OWASP Top 10 for large language model applications*. https://genai.owasp.org/