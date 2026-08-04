# Covert Use of AI in Offensive Cyber Operations

## Executive Threat-Landscape Overview

**Author:** Yuval Sinay  
**Version:** 1.0  
**Date:** 2026-08-05

## Executive Summary

Adversarial use of artificial intelligence is evolving from isolated assistance with research, translation, phishing, and scripting toward direct integration with malware, coding agents, local inference runtimes, tool orchestration, post-compromise analysis, identity deception, and attack decision-making.

The primary security risk is not a distinct category of "AI malware." It is the covert integration of AI into otherwise familiar cyber operations. Model calls may be hidden behind legitimate APIs, model-compatible proxies, local runtimes, approved development tools, cloud services, service accounts, and trusted web platforms.

The most important defensive shift is therefore from identifying generated content to correlating operational workflows:

```text
Identity -> Model or Agent -> Tool -> Data -> Execution -> System Effect
```

## Threat Evolution

| Stage | Description | Typical examples |
|---|---|---|
| AI-assisted | Human operator uses AI for individual tasks | Research, translation, phishing, scripting, debugging |
| AI-augmented | AI materially improves speed, scale, targeting, or adaptation | Vulnerability analysis, personalized lures, data prioritization |
| Runtime-integrated | Malware or automation calls a model during execution | Dynamic command generation, script creation, self-modification |
| AI-orchestrated | AI coordinates multiple attack tools or stages | Scanning, exploitation, credential access, lateral movement |
| Semi-autonomous | AI performs iterative loops with periodic human control | Tool selection, result evaluation, adaptation, operational documentation |

## Publicly Documented Patterns

### General-purpose model misuse

State-linked and criminal actors have used commercial models for reconnaissance, coding, translation, lure creation, vulnerability research, infrastructure configuration, and analysis.

### Runtime AI malware

Public reporting has described PROMPTSTEAL, PROMPTFLUX, PROMPTLOCK, QUIETVAULT, HONESTCUE, and other samples involving direct model calls, generated scripts, local inference, AI-assisted secret discovery, or self-modification.

### Agentic intrusion workflows

Provider reports have described operations in which coding agents or agentic systems supported scanning, credential access, exploitation, data analysis, lateral movement, and extortion. The most important distinguishing feature is repeated tool-inference-tool execution rather than a single generated artifact.

### AI-assisted identity deception

North Korean fraudulent remote-worker activity demonstrates how AI can support identity fabrication, language consistency, interview preparation, technical work, and long-term persistence through legitimate employee access.

### Trusted AI and cloud infrastructure

Shared AI conversations, low-code development platforms, CDNs, GitHub, model hubs, Backend-as-a-Service platforms, and model-compatible proxies can host content, relay requests, receive data, or reduce the effectiveness of reputation-based controls.

## Concealment Techniques

1. **Task decomposition:** malicious objectives are divided into individually plausible prompts or development tasks.
2. **Model hopping:** the workflow is distributed across several providers and local models.
3. **Local inference:** open-weight or local models avoid provider-side logging and safeguards.
4. **Living off the AI-enabled environment:** attackers abuse approved coding agents, AI CLIs, notebooks, model gateways, or IDE extensions.
5. **Just-in-time generation:** commands, scripts, obfuscation, and payload components are produced after execution starts.
6. **Trusted-infrastructure laundering:** reputable AI, CDN, cloud, Git, or Backend-as-a-Service domains are used as part of the attack path.
7. **Identity and API-key pooling:** disposable accounts, stolen keys, relays, and rapid rotation weaken account-level enforcement.
8. **AI-maintained human persistence:** AI helps fraudulent workers or operators preserve a credible professional identity after access is granted.

## Priority Risks for CISO

| Risk | Likelihood | Potential impact |
|---|---|---|
| AI-generated phishing and identity deception | Very high | High |
| AI-assisted malware development | High | High |
| Abuse of approved coding agents and AI CLIs | High | Critical |
| AI share-link ClickFix and trusted-domain lures | High | High |
| Runtime model calls from malware | Medium to high | Very high |
| AI-supported lateral movement | Medium | Critical |
| AI supply-chain compromise | High | Critical |
| AI-assisted zero-day discovery | Medium | Critical |
| Near-autonomous intrusion workflow | Low to medium | Critical |

This table is an analytical assessment rather than a statistical forecast. Organizations should adapt it to their own assets, approved AI use, threat actors, and exposure.

## Defensive Priorities

### Establish an AI asset and identity inventory

Record models, providers, local runtimes, agents, plugins, MCP servers, skills, service accounts, API keys, gateways, tools, data stores, and business owners.

### Treat agents as privileged workloads

Each agent should have a unique identity, short-lived credentials, scoped tool permissions, sandboxing, audit logging, approval requirements, and a kill switch.

### Correlate model activity with system effects

High-value detections link AI-service or runtime activity with:

- Script or source-code creation
- Runtime compilation
- Shell or child-process execution
- Secret access
- Persistence changes
- Remote administration
- Lateral movement
- Data collection or exfiltration

### Monitor local inference

Use endpoint, GPU, container, package, model-file, and local-port telemetry to identify unapproved runtimes and models.

### Secure AI and software supply chains

Apply provenance, code review, version pinning, signing, dependency scanning, controlled egress, least privilege, and revocation to AI SDKs, agents, MCP servers, skills, models, containers, and CI/CD integrations.

### Preserve evidence and confidence

Separate detection from attribution. Record direct artifacts, provider corroboration, alternative explanations, evidence quality, and analytic confidence.

## Priority Detection and Hunting Scenarios

1. Unexpected process calls an LLM.
2. Model response is followed by code execution.
3. Runtime compilation occurs outside development.
4. AI agent or CLI accesses credentials or secrets.
5. Public AI share link is followed by shell execution.
6. New domain uses Backend-as-a-Service for credential collection.
7. Unauthorized server contacts a model service.
8. Process modifies itself after model interaction.
9. Non-ML endpoint runs a local model or shows abnormal GPU activity.
10. Identity rapidly uses multiple AI providers.
11. Service account performs agentic tool actions.
12. File contains excessive dead or generated decoy code.
13. Lateral movement follows agent activity.
14. API keys are rapidly rotated, pooled, or used from inconsistent locations.

## Related Operational Resources

### AIDAF and detection engineering

`https://github.com/yuval14/Cybersecurity-Detection-Engineering/tree/main/AIDAF-Adversarial-AI-Detection-and-Assessment-Framework`

The repository contains:

- AIDAF assessment methodology
- AI involvement and evidence levels
- Research on covert AI-enabled offensive operations
- Detection and hunting catalog
- Case studies
- Sigma rules and correlation patterns

### Detection and hunting workbook

`https://github.com/yuval14/AI-Security-Tooling/tree/main/AI_Enabled_Threat_Detection_and_Hunting_Workbook`

The workbook contains:

- Detection catalog
- Threat-hunt worksheet
- Telemetry matrix
- Risk scoring
- Ownership, status, confidence, and review fields

## Key Sources

- Anthropic. *Detecting and countering misuse of AI: August 2025*.
- Anthropic. *Disrupting the first reported AI-orchestrated cyber espionage campaign*.
- Google Threat Intelligence Group. *GTIG AI Threat Tracker* reports.
- Microsoft Threat Intelligence. *AI as tradecraft: How threat actors operationalize AI*.
- National Institute of Standards and Technology. *Adversarial machine learning: A taxonomy and terminology of attacks and mitigations*.
- OpenAI. *Disrupting malicious uses of AI* reports.
- OWASP Gen AI Security Project. *OWASP Top 10 for Agentic Applications for 2026*.

## Responsible Use

This page is intended for lawful, ethical, authorized, defensive, research, and protective use. It does not provide operational instructions for conducting unauthorized attacks.