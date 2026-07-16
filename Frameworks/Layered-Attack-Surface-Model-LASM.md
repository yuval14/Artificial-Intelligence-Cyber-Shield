# Layered Attack Surface Model (LASM) for AI Agent Security

The **Layered Attack Surface Model (LASM)** is a structural threat-modeling framework for LLM-based AI agents. It was proposed by Chu (2026) to address a limitation in conventional AI security taxonomies: classifying attacks only by type does not show **where** an attack originates in the agent architecture or **how long** it may persist before causing harm.

LASM combines:

1. Seven architectural layers, from the foundation model to governance.
2. Four temporal classes, from immediate attacks to persistent and cumulative threats.

The resulting **7 × 4 matrix** helps architects, security teams, red teams, assurance functions, and policymakers locate threats, select controls at the correct architectural layer, and identify gaps in testing and monitoring.

> **Core principle:** AI agent security is a system and architecture problem, not only a prompt or model problem.

## Why LASM matters

An AI agent can retain memory, formulate multi-step plans, invoke external tools, access privileged resources, communicate with other agents, and operate across sessions. These capabilities create attack paths that do not exist in a stateless chatbot.

A control placed at one layer may not detect an attack localized at another layer. For example:

- Prompt filtering does not validate a compromised model checkpoint.
- Package signing does not prevent memory poisoning.
- Output moderation does not prevent an authorized but harmful tool sequence.
- Session-level monitoring may miss a payload written to memory and activated weeks later.

LASM therefore supports **cross-layer defense in depth**, with controls matched to both the affected component and the attack timescale.

## Seven LASM layers

| Layer | Architectural surface | Representative threats | Primary security objectives |
| --- | --- | --- | --- |
| **L1 Foundation** | Model weights, training process, fine-tuning artifacts, embeddings, and core inference behavior | Jailbreaks, adversarial examples, model poisoning, hidden backdoors, compromised checkpoints | Model provenance, integrity verification, adversarial testing, secure training and distribution |
| **L2 Cognitive** | Planning, reasoning, goal formation, task decomposition, and decision logic | Goal hijacking, reasoning manipulation, unsafe decomposition, objective drift | Explicit goals, bounded planning, policy checks, plan validation, stop conditions |
| **L3 Memory** | Short-term state, long-term memory, vector stores, RAG, summaries, and learned preferences | Memory poisoning, cross-session manipulation, stale or unauthorized memory, retrieval corruption | Memory provenance, controlled writes, trust labels, expiry, review, rollback, cross-session correlation |
| **L4 Tool Execution** | APIs, plugins, browsers, code interpreters, files, databases, payment systems, and external actions | Indirect prompt injection, tool misuse, parameter manipulation, data exfiltration, excessive agency | Least privilege, tool allowlists, schema validation, sandboxing, transaction limits, approval gates |
| **L5 Multi-Agent Coordination** | Agent-to-agent messaging, delegation, orchestration, shared state, and peer trust | Compromised sub-agents, collusion, impersonation, malicious delegation, cross-agent propagation | Strong agent identity, signed messages, trust boundaries, scoped delegation, workflow-level authorization |
| **L6 Ecosystem** | MCP servers, packages, models, prompts, skills, plugins, registries, and deployment dependencies | Supply-chain compromise, malicious MCP servers, poisoned templates, dependency substitution | ABOM, signing, provenance, certification, dependency review, integrity verification before loading context |
| **L7 Governance** | Policies, accountability, logging, oversight, assurance, compliance, and incident response | Unattributable actions, emergent misalignment, missing evidence, ineffective oversight, liability gaps | Trajectory attribution, policy-as-code, action logs, assurance evidence, independent review, response and recovery |

## Four temporal classes

| Class | Temporal behavior | Example | Required defensive emphasis |
| --- | --- | --- | --- |
| **T1 Instantaneous** | Injection and harmful effect occur in the same interaction | A malicious prompt causes an immediate unauthorized tool call | Runtime validation, prompt and content isolation, pre-action authorization |
| **T2 Session-persistent** | The effect remains active during the current task or session | A compromised instruction influences a multi-step workflow | Session state controls, trace monitoring, bounded execution, rollback |
| **T3 Cross-session cumulative** | A payload is stored in one session and influences later sessions | A poisoned document modifies long-term memory and changes future behavior | Memory provenance, write approval, longitudinal monitoring, cross-session replay and correlation |
| **T4 Sub-session-stack** | The threat exists below or outside the visible session, including drift or dormant compromise | A model backdoor, supply-chain compromise, or emergent behavioral drift | Artifact integrity, behavioral baselines, longitudinal evaluation, supply-chain assurance, governance controls |

## LASM matrix

Threat modeling should assign each scenario to at least one architectural layer and one temporal class.

| Layer / time | T1 Immediate | T2 Session-persistent | T3 Cross-session | T4 Stack-level or drift |
| --- | --- | --- | --- | --- |
| L1 Foundation | Jailbreak or adversarial input | Persistent session bypass | Indirect downstream effects | Backdoor, poisoned model, behavioral drift |
| L2 Cognitive | Goal or plan hijacking | Manipulated multi-step reasoning | Learned objective distortion | Emergent or dormant planning failure |
| L3 Memory | Malicious retrieved context | Poisoned session memory | Long-term memory poisoning | Systemic memory corruption or drift |
| L4 Tool Execution | Unauthorized tool call | Repeated or chained misuse | Delayed tool effects through stored state | Persistent compromise originating from tool infrastructure |
| L5 Multi-Agent Coordination | Malicious message or impersonation | Compromised delegation chain | Propagation across workflows and sessions | Persistent collusion or network-wide compromise |
| L6 Ecosystem | Malicious package, skill, prompt, or MCP response | Compromised dependency during execution | Supply-chain effect appearing in later sessions | Dormant or systemic ecosystem compromise |
| L7 Governance | Policy or approval failure | Incomplete oversight during a workflow | Missing cross-session accountability | Emergent misalignment and long-term assurance failure |

## Principal trust inversion at the tool layer

The paper identifies **principal trust inversion** as the common cause underlying the surveyed L4 attacks. This occurs when data received from an untrusted tool, webpage, document, API, or plugin is interpreted as if it were an instruction from an authorized principal.

This means that text filtering alone is insufficient. The architecture should preserve and enforce:

- The source of every instruction and data element.
- The identity and authority of the requesting principal.
- Trust labels for tool output and retrieved content.
- Separation between control instructions and untrusted data.
- Independent authorization before high-impact actions.

## Cross-layer defense requirements

| Control domain | Minimum requirements |
| --- | --- |
| Identity and authorization | Dedicated agent identities, delegated authorization, short-lived credentials, separation of duties, transaction-level policy |
| Context and instruction security | Instruction-data separation, source labels, trust metadata, context isolation, untrusted-content handling |
| Memory security | Approved write paths, provenance, integrity checks, retention limits, expiry, version history, rollback, cross-session monitoring |
| Tool security | Allowlists, typed schemas, parameter validation, sandboxing, controlled egress, quotas, approval for irreversible actions |
| Multi-agent security | Mutual authentication, signed messages, scoped delegation, peer trust policy, agent isolation, propagation controls |
| Supply-chain security | Model and package provenance, signed artifacts, MCP review, dependency pinning, integrity verification, vulnerability monitoring |
| Governance and assurance | Policy-as-code, complete action logs, trace IDs, trajectory reconstruction, independent evaluation, incident playbooks |
| Recovery | Kill switch, credential revocation, memory rollback, dependency isolation, forensic capture, tested restoration procedures |

## Agent Bill of Materials (ABOM)

LASM introduces the **Agent Bill of Materials (ABOM)** as an extension of the Software Bill of Materials concept. An agent's runtime behavior depends on more than source code and packages.

An ABOM should record at least:

| Component | Example evidence |
| --- | --- |
| Models and checkpoints | Model identifier, version, hash, provider, training or fine-tuning provenance |
| Prompts and policies | System instructions, templates, policy version, owner, approval record |
| Tools and MCP servers | Tool identity, endpoint, publisher, permissions, schemas, integrity and certification status |
| Memory and retrieval | Vector stores, data sources, write permissions, retention, trust labels, embedding model |
| Agent relationships | Parent agent, sub-agents, delegation scopes, communication routes, trust policy |
| Runtime environment | Sandbox, container image, network policy, filesystem access, secrets and credential scopes |
| Dependencies | Libraries, plugins, skills, registries, packages, versions, hashes, vulnerability status |
| Governance | Business owner, technical owner, risk classification, approvals, logging policy, incident contact |

The ABOM should be versioned and checked before the agent initializes its context or connects to external tools.

## Testing and evaluation implications

The survey analyzed 116 papers published from 2021 through 2026 and found that research and benchmarks concentrate heavily on immediate and session-level threats. The paper reports that no surveyed benchmark evaluated T3 or T4 threats.

A production evaluation program should therefore include:

1. Multi-session memory-poisoning tests.
2. Delayed activation scenarios.
3. Longitudinal behavioral-drift analysis.
4. Multi-agent propagation and collusion scenarios.
5. Compromised MCP, plugin, prompt-template, and model supply-chain tests.
6. Trajectory-level attribution and action-log reconstruction exercises.
7. Recovery tests for memory rollback, dependency isolation, and credential revocation.

## Five research and engineering gaps

| Gap | LASM region | Practical implication |
| --- | --- | --- |
| Cross-session attack benchmarks | L3 × T3 | Security teams need repeatable multi-session replay, memory serialization, ground-truth labels, and metrics for future-session behavioral change |
| Emergent misalignment detection | L7 × T4 | Longitudinal behavioral baselines and causal analysis are needed to distinguish harmful drift from legitimate adaptation |
| General steganographic-collusion detection | L5 × T1–T2 | Detection must address previously unseen encoding schemes and adaptive multi-agent communication |
| ABOM standardization and MCP certification | L6 × T1–T2 | Common schemas, automated tooling, disclosure requirements, and certification can improve ecosystem assurance |
| System-level accountability frameworks | L7 × T1–T4 | High-stakes deployments require trajectory attribution, plan assurance, evidence retention, and clear allocation of responsibility |

## Practical threat-modeling workflow

1. Define the agent's mission, owners, users, and prohibited outcomes.
2. Inventory the seven LASM layers present in the architecture.
3. Build or update the ABOM.
4. Identify trust boundaries and authorized principals.
5. Map each abuse case to one or more LASM layers.
6. Assign a temporal class from T1 to T4.
7. Place preventive, detective, and recovery controls at the affected layers.
8. Test cross-layer attack paths rather than isolated components only.
9. Validate behavior across multiple sessions and over time.
10. Preserve evidence sufficient to reconstruct the complete action trajectory.

## Architecture principle

> **The model proposes; the governed architecture disposes.**

Prompts can guide behavior, but enforceable controls should reside in identity systems, policy engines, memory services, tool gateways, sandboxes, orchestration logic, supply-chain controls, and audit infrastructure.

## Limitations

LASM is based on a systematic mapping of the published research literature. The quantitative coverage findings should not be interpreted as a complete measurement of unpublished incidents, proprietary red-team results, or controls implemented privately by vendors and organizations. The source is also an arXiv preprint and may be revised.

## APA 7 reference

Chu, K. (2026). *A systematic survey of security threats and defenses in LLM-based AI agents: A layered attack surface framework* [Preprint]. arXiv. https://doi.org/10.48550/arXiv.2604.23338

## Source

- Paper: https://arxiv.org/abs/2604.23338
- Version reviewed: arXiv v2, revised May 6, 2026
