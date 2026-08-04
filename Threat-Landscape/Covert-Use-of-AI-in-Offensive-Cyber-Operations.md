# Covert Use of AI in Offensive Cyber Operations

**Author:** Yuval Sinay  
**Version:** 1.0  
**Date:** 2026-08-05

## Executive Summary

Threat actors increasingly use artificial intelligence as an embedded operational capability within conventional cyberattacks. The relevant risk is broader than AI-generated phishing or malware code. Models and agents may support reconnaissance, vulnerability analysis, command generation, runtime code creation, credential discovery, lateral movement, data analysis, extortion, and multi-tool orchestration.

The most important change for defenders is that AI use may be hidden inside legitimate developer tools, approved accounts, cloud services, local model runtimes, service identities, or trusted infrastructure. There is rarely a unique indicator that proves AI involvement.

Organizations should therefore detect the operational chain rather than the writing style or apparent sophistication of an artifact.

## Threat Evolution

| Stage | Description |
|---|---|
| AI as an assistant | Supports research, translation, drafting, scripting, debugging, and vulnerability analysis. |
| AI as an operational component | Generates commands, scripts, code, or decisions during the attack workflow. |
| AI inside malware | A malicious process invokes a model or local inference runtime during execution. |
| AI as an orchestrator | An agent coordinates tools, evaluates results, and selects the next action. |
| AI ecosystem as an attack path | Plugins, skills, MCP servers, coding agents, model gateways, and supply-chain components become trusted access paths. |

## Covert-Use Patterns

### Task decomposition

A malicious objective may be divided into apparently legitimate requests. Individual prompts can resemble ordinary programming, troubleshooting, translation, or research.

### Multi-provider model hopping

Different models may be used for research, code, translation, media generation, and orchestration. No provider sees the complete workflow.

### Local models

Local inference can avoid provider-side monitoring, process stolen data offline, and support payload generation without direct cloud-model traffic.

### Living off the AI-enabled environment

A compromised account or endpoint may reuse an approved coding assistant, AI CLI, browser agent, local model, or service identity that already has repository, shell, cloud, or secret access.

### Just-in-time functionality

Commands, scripts, or source code may be generated only after execution begins. The initial malware sample may not contain its complete operational capability.

### Trusted infrastructure laundering

AI providers, GitHub, Hugging Face, CDNs, Backend-as-a-Service platforms, and cloud services may provide hosting, relay, delivery, or command-generation functionality that cannot be blocked globally without business impact.

### Account and API-key pooling

Disposable accounts, pooled API keys, relay services, proxies, and OpenAI-compatible interfaces can distribute activity and reduce the effectiveness of account-level enforcement.

## Publicly Reported Capability Areas

Public reporting from model providers and security vendors has described or investigated:

- State-linked and criminal use of general-purpose models for reconnaissance, translation, phishing, scripting, and debugging
- Runtime model interaction by malware or malware prototypes
- AI-assisted secret discovery using tools already installed on compromised systems
- Dynamic code generation, rewriting, and obfuscation
- Public AI conversation links used in ClickFix-style social engineering
- AI-assisted phishing development using trusted web and Backend-as-a-Service infrastructure
- Agentic workflows supporting several cyberattack stages
- AI-assisted identity fabrication and fraudulent remote employment
- AI-supported vulnerability discovery and exploit development

These reports vary in evidence depth. Provider-confirmed account misuse, recovered prompts, runtime artifacts, and agent traces are stronger evidence than generated-output characteristics or behavioral similarity.

## Detection Principle

The recommended evidence chain is:

```text
Identity -> device -> process -> model or agent -> tool call -> data access -> system action -> external effect
```

High-value examples include:

```text
Unexpected process -> AI endpoint -> generated source -> runtime compiler -> child process
```

```text
AI coding agent -> secret access -> Git or cloud action -> new external destination
```

```text
Public AI share link -> terminal launch -> encoded or download-and-execute command
```

## Priority Defensive Actions

1. Inventory approved AI providers, model APIs, local models, coding agents, plugins, skills, MCP servers, and service identities.
2. Route enterprise model access through an AI gateway where feasible.
3. Assign a unique identity and least-privilege permissions to every agent and workload.
4. Require human approval for irreversible, high-impact, or externally visible actions.
5. Log prompts or protected prompt metadata, model sessions, tool calls, memory changes, policy decisions, and downstream actions.
6. Correlate AI use with endpoint, identity, cloud, network, Git, CI/CD, DLP, and secret-manager telemetry.
7. Detect unauthorized local inference through process, model-file, container, GPU, and local-port telemetry.
8. Include AI-enabled intrusion and supply-chain scenarios in red-team, purple-team, and incident-response exercises.
9. Preserve failed commands and correction loops because they can reveal adaptive workflows.
10. Treat AI involvement as a confidence-based assessment, separate from actor attribution and the underlying MITRE ATT&CK technique.

## Executive Questions

- Which AI systems can perform actions rather than only provide recommendations?
- Can every agent tool call be linked to an identity, session, purpose, and authorization decision?
- Which coding agents can access secrets, production systems, cloud administration, or CI/CD?
- Are local models and GPU runtimes inventoried and monitored?
- Can the organization rapidly suspend an agent without disabling an entire business service?
- Does incident response preserve prompts, memory, traces, model configuration, and tool-call evidence?
- Are public AI share links, unapproved providers, and trusted BaaS platforms included in phishing detection and threat hunting?

## Related Operational Resources

- [Covert AI-Enabled Offensive Cyber Operations Research](https://github.com/yuval14/Cybersecurity-Detection-Engineering/blob/main/AIDAF-Adversarial-AI-Detection-and-Assessment-Framework/Covert-AI-Enabled-Offensive-Cyber-Operations.md)
- [AI-Enabled Detection and Hunting Catalog](https://github.com/yuval14/Cybersecurity-Detection-Engineering/blob/main/AIDAF-Adversarial-AI-Detection-and-Assessment-Framework/AI-Enabled-Detection-and-Hunting-Catalog.md)
- [AIDAF Framework](https://github.com/yuval14/Cybersecurity-Detection-Engineering/tree/main/AIDAF-Adversarial-AI-Detection-and-Assessment-Framework)
- [AIDAF Sigma Detection Pack](https://github.com/yuval14/Cybersecurity-Detection-Engineering/tree/main/AIDAF-Adversarial-AI-Detection-and-Assessment-Framework/sigma)
- [AI-Enabled Threat Detection and Hunting Workbook](https://github.com/yuval14/AI-Security-Tooling/tree/main/AI_Enabled_Threat_Detection_and_Hunting_Workbook)

## Selected Sources

- Anthropic threat-disruption and AI-enabled cyber-threat reports
- Google Threat Intelligence Group AI Threat Tracker reports
- Microsoft Threat Intelligence reporting on AI as tradecraft
- OpenAI reports on disruption of malicious AI use
- NIST AI 100-2, *Adversarial Machine Learning: A Taxonomy and Terminology of Attacks and Mitigations*
- OWASP Top 10 for Agentic Applications
- MITRE ATLAS and MITRE ATT&CK

## Analytic Caution

Adaptive, fast, multilingual, or technically sophisticated activity does not independently demonstrate AI use. Defenders should distinguish confirmed model integration, provider-reported misuse, plausible behavioral inference, and experimental capability.