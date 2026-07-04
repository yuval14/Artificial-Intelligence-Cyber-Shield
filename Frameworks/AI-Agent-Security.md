# AI Agent Security

This page lists frameworks, control patterns, and security principles for AI agents. The focus is on systems that can reason across steps, use tools, call APIs, retrieve data, maintain memory, delegate tasks, or perform actions in digital or physical environments.

## Framework comparison

| # | Vendor / organization | Framework / resource | Goal / function | Release date | Open source / public | Primary use |
| --- | --- | --- | --- | --- | --- | --- |
| 1 | OWASP | Agentic AI Threats and Mitigations | Identify security risks unique to agentic AI systems | 2025 | Yes | Agent threat modeling and control design |
| 2 | OWASP | Top 10 for LLM Applications | Address prompt injection, insecure output handling, sensitive information disclosure, and excessive agency | 2023, updated 2025 | Yes | LLM agent application security |
| 3 | Cloud Security Alliance | Agentic AI security and red teaming guidance | Address autonomy, identity, tool use, permissions, and multi-step risk | 2025 | Yes | Enterprise agent security and red teaming |
| 4 | Google | Secure AI Framework and Secure Agents | Secure AI systems, including agentic workflows, supply chain, monitoring, response, and trusted agent design | 2023, expanded 2026 | Yes | Secure architecture baseline |
| 5 | Microsoft | AI agent security guidance | Secure agent identity, tool use, data access, and human oversight | 2024 onwards | Yes | Enterprise agent deployment |
| 6 | NIST | AI RMF and GenAI Profile | Govern, map, measure, and manage agentic AI risks | 2023, 2024 | Yes | Risk governance for AI agents |
| 7 | MITRE | ATLAS | Map adversary behavior against AI systems and agent workflows | 2020 | Yes | Threat-informed agent defense |
| 8 | CISA, NSA, FBI, UK NCSC, and partners | Guidelines for Secure AI System Development | Secure design, development, deployment, and operation of AI systems | 2023 | Yes | Secure AI lifecycle controls |
| 9 | Model Context Protocol community | MCP security guidance and threat discussions | Secure tool connections, context exchange, and server-client trust boundaries | 2024 onwards | Public | MCP and tool ecosystem security |
| 10 | ETSI | Securing Artificial Intelligence reports and guidance | Address AI threats, data supply-chain risks, security testing, vulnerability disclosure, privacy, and mitigation strategies | 2019 onwards | Public standards and reports | AI system and agent security governance |
| 11 | Research community | ASTRA, WASP, AI-Infra-Guard, and related agent benchmarks | Evaluate agent steerability, prompt-injection resilience, web-agent security, and multi-layer agent attacks | 2025 onwards | Yes / public research | Agentic AI security evaluation |

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
| Tool-loop denial of service | Agent repeatedly calls tools or consumes tokens, compute, API quota, or budget | Quotas, rate limits, timeout rules, circuit breakers, recursion limits |
| Cross-agent propagation | One compromised agent influences another agent, workflow, or memory store | Agent isolation, signed messages, trust labels, workflow-level policy enforcement |

## Agent security reference architecture

| Layer | Security objective | Minimum controls |
| --- | --- | --- |
| User and requester identity | Ensure the agent knows who is asking and what authority they have | Strong authentication, delegated authorization, role mapping, session binding |
| Agent identity | Ensure every agent has a bounded and auditable identity | Dedicated service identity, scoped credentials, ownership metadata, key rotation |
| Model and policy layer | Keep model behavior within approved policy boundaries | System instruction management, policy-as-code, safety filters, regression tests |
| Context and retrieval layer | Prevent untrusted content from becoming trusted instructions | Source labeling, retrieval filtering, prompt injection detection, context separation |
| Tool and action layer | Prevent unauthorized or unsafe actions | Tool allowlist, parameter validation, sandboxing, approval gates, transaction signing |
| Memory layer | Prevent poisoned, stale, or unauthorized memory from changing behavior | Memory provenance, write controls, expiry rules, review workflows, rollback |
| Monitoring layer | Reconstruct actions and detect abuse | Trace IDs, prompt logs, tool-call logs, anomaly detection, SIEM integration |
| Response and recovery layer | Limit impact when an agent fails or is compromised | Kill switch, rollback, credential revocation, incident playbooks, forensic capture |

## Agent Rule of One

Each AI agent should possess only one of the following three high-risk capabilities at a time:

1. Access to sensitive data.
2. Ability to execute external actions.
3. Ability to modify memory, policy, identity, or configuration.

If an agent requires more than one high-risk capability, add compensating controls such as human approval, separation of duties, sandboxing, rate limits, transaction signing, and independent monitoring.

## Agent security checklist

| Question | Why it matters | Evidence to collect |
| --- | --- | --- |
| What tools can the agent call? | Tool access defines the real blast radius of the agent | Tool inventory, permission scopes, tool risk rating |
| Which identity does the agent use? | Shared or overbroad identities create accountability and privilege risks | Service identity record, token scope, owner mapping |
| Can untrusted content enter the context window? | Indirect prompt injection often enters through web pages, files, emails, tickets, or RAG | Source map, retrieval rules, prompt-injection tests |
| Can the agent modify memory or configuration? | Persistent state can turn a temporary attack into durable compromise | Memory write policy, approval records, rollback plan |
| Which actions require human approval? | High-impact operations should not be delegated blindly to probabilistic systems | Approval matrix, signed transaction records |
| Can the agent spend money, consume compute, or trigger external workflows? | Agents can create denial-of-wallet and cascading automation failures | Quotas, budgets, timeout rules, cost alerts |
| Are tool calls and model decisions logged? | Incidents require reconstruction of prompts, outputs, tools, and approvals | Trace logs, SIEM events, retention policy |
| Can the agent be stopped quickly? | Response speed matters when autonomous systems misbehave | Kill switch, credential revocation plan, runbook |

## Suggested maturity model

| Level | Description | Typical controls |
| --- | --- | --- |
| 0 | Experimental agent | Manual testing, no production data, no external action |
| 1 | Assisted agent | Read-only tools, user confirmation, basic logging |
| 2 | Controlled agent | Scoped tools, approval gates, prompt-injection tests, cost limits |
| 3 | Governed agent | Policy-as-code, least privilege, memory controls, SIEM integration, incident playbooks |
| 4 | High-assurance agent | Independent red team, formal risk acceptance, continuous evaluation, runtime enforcement, post-incident forensics |

## APA 7 references

Cloud Security Alliance. (2025). *Agentic AI security guidance*. https://cloudsecurityalliance.org/

Cybersecurity and Infrastructure Security Agency, National Security Agency, Federal Bureau of Investigation, National Cyber Security Centre, and international partners. (2023). *Guidelines for secure AI system development*. https://www.cisa.gov/

European Telecommunications Standards Institute. (n.d.). *Securing Artificial Intelligence*. https://www.etsi.org/technologies/securing-artificial-intelligence

Evtimov, I., Zharmagambetov, A., Grattafiori, A., Guo, C., & Chaudhuri, K. (2025). *WASP: Benchmarking web agent security against prompt injection attacks*. arXiv. https://arxiv.org/abs/2504.18575

Google. (2026). *Secure AI framework: Secure agents*. https://saif.google/

Hazan, I., Mathov, Y., Shtar, G., Bitton, R., & Mantin, I. (2025). *ASTRA: Agentic steerability and risk assessment framework*. arXiv. https://arxiv.org/abs/2511.18114

MITRE. (n.d.). *MITRE ATLAS: Adversarial threat landscape for artificial-intelligence systems*. https://atlas.mitre.org/

National Institute of Standards and Technology. (2023). *Artificial intelligence risk management framework (AI RMF 1.0)*. https://doi.org/10.6028/NIST.AI.100-1

Open Worldwide Application Security Project. (2025). *OWASP Top 10 for large language model applications*. https://genai.owasp.org/

Yang, Y., Zheng, X., Wu, H., Cheng, H., Shi, X., Guo, J., Yang, B., Zhou, Y., Wu, X., & Ying, Z. (2026). *Securing the AI agent: A unified framework for multi-layer agent red teaming*. arXiv. https://arxiv.org/abs/2606.31227