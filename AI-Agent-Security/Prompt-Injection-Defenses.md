# Prompt Injection Defenses

## Overview
Prompt injection is a class of attacks in which adversarial instructions alter an AI system's intended behavior. In agentic systems, injected content may arrive through user input, retrieved documents, websites, email, memory, APIs, images, or tool outputs.

## Threat Types

| Threat | Description | Typical Entry Point | Potential Impact |
|---|---|---|---|
| Direct prompt injection | Malicious instructions are supplied directly by the user | Chat or API input | Policy bypass, data disclosure, unsafe output |
| Indirect prompt injection | Instructions are embedded in external content processed by the model | Web pages, documents, email, RAG sources | Tool abuse, task redirection, secret leakage |
| Context poisoning | Adversarial data changes the model's interpretation of the active task | Retrieved context, logs, tool results | Persistent or situational manipulation |
| Memory poisoning | Malicious content is stored and reused in later sessions | Long-term memory, vector stores | Delayed compromise and repeated unsafe behavior |
| Tool-output injection | A tool returns text that is interpreted as instructions | Browser, shell, database, SaaS connector | Unauthorized actions and lateral movement |
| Multimodal injection | Hidden or visible instructions are placed in images, PDFs, audio, or video | OCR, vision models, document parsers | Cross-modal policy bypass |

## Defensive Techniques

| Technique | Security Objective | Strengths | Limitations |
|---|---|---|---|
| Input filtering | Detect suspicious patterns before model processing | Low cost and easy to deploy | Weak against adaptive and semantic attacks |
| Instruction hierarchy | Preserve priority among system, developer, user, and data content | Reduces simple override attempts | The model may still misclassify data as instructions |
| Context segmentation | Separate policy, user intent, retrieved data, memory, and tool output | Improves provenance and policy enforcement | Requires architectural support |
| Provenance labels | Record source, owner, trust level, and timestamp | Supports trust-aware reasoning and audit | Labels inside the prompt can be ignored or manipulated |
| Task-alignment checks | Verify that proposed actions support the authenticated user goal | Detects task deviation | Needs a reliable verifier and explicit task model |
| Content transformation | Summarize, paraphrase, normalize, or encode untrusted content | Can weaken embedded instructions | May lose useful information and does not guarantee safety |
| External policy engine | Authorize actions outside the model | Deterministic and auditable | Requires policy design and integration |
| Least privilege | Restrict tools, credentials, data, and network access | Limits blast radius | May reduce functionality |
| Human approval | Require confirmation for high-impact actions | Strong safeguard for consequential operations | Adds latency and does not scale to all actions |
| Sandboxing | Isolate execution and restrict side effects | Limits compromise impact | Does not prevent information leakage by itself |
| Canary resources | Detect suspicious access to decoy secrets or tools | Useful for early warning | Primarily detective rather than preventive |
| Continuous adversarial testing | Evaluate full attack trajectories | Identifies system-level weaknesses | Requires realistic environments and frequent updates |

## Recommended Layered Architecture

| Layer | Controls | Example Enforcement Point |
|---|---|---|
| 1. Intake | Validation, malware scanning, content-type checks | API gateway or ingestion service |
| 2. Context | Segmentation, provenance, trust scoring | Prompt and context builder |
| 3. Reasoning | Task-alignment and policy checks | Agent planner or verifier |
| 4. Authorization | Capability tokens, allowlists, transaction limits | External policy engine |
| 5. Execution | Sandboxing, network controls, scoped credentials | Tool runtime |
| 6. Monitoring | Tracing, canaries, anomaly detection | SIEM, agent observability platform |
| 7. Recovery | Session termination, memory rollback, credential rotation | Incident response workflow |

## Research Comparison

| Research Direction | Core Idea | Best Use |
|---|---|---|
| Task-alignment enforcement | Reject actions unrelated to the original authenticated objective | Autonomous agents with multiple tools |
| Provenance-aware reasoning | Track which context elements influence decisions | RAG and multi-source agents |
| Memory security | Separate storage, retrieval, trust, and action authority | Long-running personal or enterprise agents |
| Context transformation | Reduce the influence of embedded instructions | Document and web ingestion pipelines |
| Agent trajectory evaluation | Test complete sequences of observations, plans, and actions | Predeployment assurance and red teaming |
| Deception-based detection | Use decoys and canaries to detect compromised agents | High-risk environments and cyber defense |

## Implementation Checklist

| Control Question | Status |
|---|---|
| Are retrieved documents treated as untrusted data rather than instructions? | ☐ |
| Is every context item tagged with source and trust level? | ☐ |
| Are high-risk tool calls authorized outside the model? | ☐ |
| Are credentials scoped per agent and per task? | ☐ |
| Is long-term memory write access restricted? | ☐ |
| Can memory entries be quarantined or rolled back? | ☐ |
| Are tool outputs sanitized and provenance-checked? | ☐ |
| Are full agent trajectories logged and reviewed? | ☐ |
| Are canary resources deployed for detection? | ☐ |
| Are adaptive prompt-injection tests included in security validation? | ☐ |

## Key Principle
Prompt injection should be treated as a system-security problem rather than only a prompt-engineering problem. The strongest design assumes that some malicious context will reach the model and prevents that context from obtaining authority over tools, secrets, memory, and consequential actions.