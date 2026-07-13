# AI Agent Threat Matrix

## Overview
This matrix connects common AI agent threats with defensive controls and governance frameworks. The mappings are analytical and should be validated against the current official versions of MITRE ATLAS, OWASP guidance, and the NIST AI Risk Management Framework before use in formal compliance documentation.

## Threat and Control Matrix

| Threat | Attack Vector | Likely Impact | Preventive Controls | Detective Controls | Response Controls |
|---|---|---|---|---|---|
| Direct prompt injection | User input | Policy bypass and unsafe output | Instruction hierarchy, input validation, policy checks | Prompt anomaly detection, trace review | Session termination and policy update |
| Indirect prompt injection | Web, documents, email, RAG | Task redirection and tool misuse | Context segmentation, provenance, untrusted-content handling | Canary content, task-deviation monitoring | Quarantine source and revoke tool access |
| Context poisoning | Retrieved or generated context | Corrupted reasoning and decisions | Trusted retrieval, source validation, context isolation | Context-drift detection and provenance tracing | Remove poisoned context and rerun task |
| Memory poisoning | Long-term memory or vector store | Persistent compromise | Restricted memory writes, validation, temporal decay | Memory change monitoring and canary memories | Quarantine entries and restore clean state |
| Tool abuse | Agent tool invocation | Unauthorized actions | Least privilege, capability tokens, allowlists | Tool-call anomaly detection | Revoke credentials and isolate runtime |
| Excessive agency | Broad autonomy and permissions | High-impact unintended actions | Transaction limits, human approval, scoped objectives | Behavioral baselines and action tracing | Rollback and suspend agent |
| Secret leakage | Prompt, memory, logs, tools | Credential or data exposure | Secret isolation, redaction, scoped credentials | DLP, honeytokens, egress monitoring | Rotate secrets and investigate access |
| RAG poisoning | Compromised knowledge source | Misinformation and malicious instructions | Signed sources, ingestion validation, source ranking | Retrieval anomaly detection | Remove source and rebuild index |
| Supply-chain compromise | Model, plugin, library, tool | System-wide compromise | SBOM, signed artifacts, dependency review | Integrity monitoring and runtime attestation | Disable component and restore trusted version |
| Model or agent impersonation | Fake endpoint or identity | Misrouting and trust abuse | Strong workload identity and mutual authentication | Identity anomaly detection | Revoke identity and block endpoint |
| Multimodal injection | Image, PDF, audio, video | Hidden instruction execution | Modality-aware sanitization and isolated parsing | Cross-modal content inspection | Remove artifact and inspect trajectory |
| Data exfiltration through tools | Email, browser, API, code execution | Confidentiality loss | Egress controls, destination allowlists, data minimization | DLP and network monitoring | Block transfer and rotate access tokens |
| Denial of service and resource exhaustion | Recursive tasks, token flooding, tool loops | Cost and availability impact | Quotas, timeouts, recursion limits | Cost and loop monitoring | Terminate job and rate-limit source |
| Agent-to-agent manipulation | Messages between agents | Delegation abuse and cascading compromise | Mutual authentication, scoped delegation, message provenance | Inter-agent trace analysis | Isolate compromised agent and invalidate delegation |
| Deceptive or compromised tool output | API or connector response | Unsafe downstream action | Schema validation and trust boundaries | Output anomaly detection | Disable tool and revert action |

## Framework Mapping

| Threat | MITRE ATLAS Theme | OWASP LLM / GenAI Theme | NIST AI RMF Function | Primary Control Family |
|---|---|---|---|---|
| Prompt injection | Adversarial manipulation of model behavior | Prompt Injection | MAP, MEASURE, MANAGE | Input trust and policy enforcement |
| Sensitive information disclosure | Data exposure and model output abuse | Sensitive Information Disclosure | GOVERN, MAP, MANAGE | Data protection and DLP |
| Supply-chain compromise | Compromise of AI dependencies | Supply Chain Vulnerabilities | GOVERN, MAP, MANAGE | Software and model supply-chain security |
| Data or model poisoning | Poisoning and integrity attacks | Data and Model Poisoning | MAP, MEASURE, MANAGE | Provenance, validation, and integrity monitoring |
| Improper output handling | Unsafe use of model-generated content | Improper Output Handling | MEASURE, MANAGE | Output validation and safe execution |
| Excessive agency | Abuse of autonomous capabilities | Excessive Agency | GOVERN, MAP, MANAGE | Least privilege and human oversight |
| System prompt leakage | Disclosure of internal instructions | System Prompt Leakage | GOVERN, MANAGE | Secrets separation and access control |
| Vector and embedding weakness | Manipulated retrieval or similarity search | Vector and Embedding Weaknesses | MAP, MEASURE, MANAGE | Secure RAG and index integrity |
| Misinformation | Incorrect or deceptive model output | Misinformation | MEASURE, MANAGE | Verification and source grounding |
| Unbounded resource consumption | Cost or availability attacks | Unbounded Consumption | MAP, MEASURE, MANAGE | Quotas, budgets, and runtime limits |

## Security Control Domains

| Domain | Minimum Controls | Evidence |
|---|---|---|
| Identity | Workload identity, mutual authentication, scoped delegation | Identity logs and credential inventory |
| Access Control | Least privilege, capability tokens, allowlists, transaction limits | Policy definitions and authorization logs |
| Context Security | Segmentation, provenance, trust labels, source validation | Context manifests and trace records |
| Memory Security | Restricted writes, validation, expiration, rollback | Memory audit logs and version history |
| Tool Security | Sandboxing, schema validation, scoped credentials | Tool inventory and execution telemetry |
| Data Protection | Data minimization, encryption, redaction, DLP | Data-flow maps and DLP events |
| Monitoring | Full trajectory logging, anomaly detection, canaries | SIEM events and agent traces |
| Resilience | Timeouts, quotas, rollback, graceful degradation | Recovery tests and incident exercises |
| Governance | Risk ownership, approval gates, change control, independent assurance | Risk register and review records |

## Risk Scoring Template

| Factor | Scale | Example Question |
|---|---|---|
| Autonomy | 1–5 | How independently can the agent plan and act? |
| Privilege | 1–5 | What systems, data, and tools can it access? |
| Persistence | 1–5 | Can compromise survive across sessions through memory or state? |
| Exposure | 1–5 | How much untrusted content does the agent process? |
| Consequence | 1–5 | What is the maximum operational, financial, safety, or national-security impact? |
| Detectability | 1–5 | How difficult is malicious behavior to detect? |

A simple prioritization score can be calculated as:

`Risk Priority = Autonomy × Privilege × Persistence × Exposure × Consequence × Detectability`

Organizations should calibrate thresholds to their operating environment and avoid treating this illustrative formula as a substitute for formal risk analysis.

## Assessment Checklist

| Assessment Question | Status |
|---|---|
| Is every agent identity uniquely authenticated? | ☐ |
| Are agent permissions scoped to a specific task and duration? | ☐ |
| Are untrusted context and trusted instructions separated? | ☐ |
| Are consequential actions authorized outside the model? | ☐ |
| Is memory governed as a privileged security boundary? | ☐ |
| Are all tool calls and outputs logged with provenance? | ☐ |
| Are secrets inaccessible to the model unless strictly required? | ☐ |
| Are agent-to-agent messages authenticated and authorized? | ☐ |
| Are prompt injection and memory poisoning tested regularly? | ☐ |
| Can the organization suspend, isolate, and roll back an agent quickly? | ☐ |

## Key Principle
AI agent security requires control over authority, not only control over language. Models may interpret untrusted content, but deterministic security mechanisms must decide what the agent is allowed to access, remember, disclose, and execute.