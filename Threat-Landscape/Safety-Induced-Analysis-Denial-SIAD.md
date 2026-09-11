# Safety-Induced Analysis Denial (SIAD)

**Author:** Yuval Sinay  
**Version:** 1.0  
**Date:** 11 September 2026

## Overview

Safety-Induced Analysis Denial (SIAD) is a proposed term for an AI-native defense-evasion pattern in which an adversary deliberately introduces policy-sensitive semantic content into malware, logs, documents, telemetry, or other attacker-controlled artifacts in order to trigger AI safety controls and degrade legitimate defensive analysis.

The core idea is counterintuitive: the attacker does not necessarily try to bypass the AI system's safety controls. Instead, the attacker attempts to make those controls activate against the defender.

A simplified attack path is:

**Malicious artifact -> AI-assisted analysis -> Safety trigger -> Refusal, redaction, omission, or workflow interruption -> Detection blind spot**

## Why This Matters

AI is increasingly used in malware analysis, SOC triage, threat intelligence, reverse engineering, log analysis, vulnerability assessment, digital forensics, and incident response. This creates a new dependency on semantic reasoning and policy-enforcement layers.

If attacker-controlled content can influence those layers, AI safety mechanisms may become part of the defensive attack surface.

Examples of possible policy-sensitive content include unrelated references to restricted or high-risk domains such as biological threats, nuclear research, weapons, self-harm, or other categories that may cause a model or moderation layer to restrict output.

The defensive risk is not limited to a complete refusal. Selective omission may be more dangerous because an analyst may receive an apparently complete answer that silently excludes operationally important findings.

## Relationship to Existing Research

SIAD is related to, but distinct from, conventional prompt injection.

Security research has already demonstrated that attacker-controlled text embedded in malicious artifacts or security telemetry can influence AI-assisted analysis. Check Point Research documented malware containing prompt-injection content intended to influence AI-based analysis. JFrog Security Research subsequently demonstrated cases in which guardrails interrupted malware-analysis output. Research presented at USENIX Security 2026 also showed that malicious content embedded in security logs can contaminate LLM-based analysis and conceal activity.

These observations support the broader conclusion that attacker-controlled evidence can manipulate AI-assisted defensive workflows.

## SIAD vs. Indirect Prompt Injection

| Characteristic | Indirect Prompt Injection | Safety-Induced Analysis Denial |
| --- | --- | --- |
| Primary objective | Hijack model behavior | Degrade or suppress defensive analysis |
| Attacker wants model cooperation | Usually | Not necessarily |
| Uses attacker-controlled content | Yes | Yes |
| Explicit malicious instruction required | Often | No |
| Relationship to safety controls | Often attempts to bypass them | Deliberately attempts to trigger them |
| Primary defensive impact | Integrity | Availability and analytical integrity |
| Typical outcome | Incorrect model action | Refusal, omission, redaction, or investigation interruption |

## Threat Model

### 1. Adversary Anticipation

The adversary assumes that defenders use AI somewhere in the investigation pipeline, including:

- SOC copilots
- Malware-analysis assistants
- Threat-intelligence platforms
- AI-assisted reverse engineering
- SIEM investigation copilots
- EDR investigation systems
- Autonomous or semi-autonomous incident-response agents
- Email-security and document-analysis systems
- Digital-forensics platforms

### 2. Semantic Contamination

The adversary introduces policy-sensitive content into an artifact or telemetry stream. The content may be operationally irrelevant to the malware itself and exist only to influence the AI analysis layer.

### 3. AI Ingestion

The security platform ingests the attacker-controlled content into the same reasoning context as trusted analyst instructions.

### 4. Safety Activation

A model, moderation layer, application guardrail, or policy engine interprets the combined context as unsafe or restricted.

### 5. Defensive Degradation

The AI system refuses, truncates, redacts, omits, or terminates part of the defensive workflow.

## Variants

### Refusal Triggering

The AI system refuses to analyze the artifact or a significant portion of it.

### Selective Analysis Suppression

The AI system completes the investigation but omits specific functions, code regions, indicators, or behavioral findings.

### Agent Workflow Interruption

An autonomous or semi-autonomous investigation chain stops after a safety-control decision, preventing enrichment, sandboxing, IOC extraction, escalation, or containment recommendations.

## Architectural Principle

> Attacker-controlled content must be treated as evidence, not as an instruction to the model and not as an indication of the analyst's intent.

AI-enabled defensive systems should separately evaluate:

1. **User intent** - What authorized defensive task is the analyst attempting to perform?
2. **Evidence risk** - What sensitive or dangerous content exists inside the artifact?
3. **Action risk** - What real-world action is the system being asked to perform?

These dimensions should not be collapsed into a single content-safety decision.

## Defensive Controls

### Preserve Raw Evidence

Original artifacts and extracted evidence must remain available independently of AI output. An AI refusal must never remove evidence from the investigative pipeline.

### Separate Trusted Instructions from Untrusted Evidence

Security architectures should explicitly distinguish analyst instructions, system policy, retrieved evidence, tool output, and attacker-controlled content.

### Maintain Deterministic Analysis Paths

AI should augment, not replace, deterministic security analysis. Hashing, strings extraction, metadata inspection, import/export parsing, sandbox telemetry, process behavior, network indicators, signatures, and memory artifacts should remain independently available.

### Separate Safety Classification from Investigation Authorization

A system should distinguish between:

- sensitive content found inside evidence, and
- an analyst requesting prohibited assistance.

Authorized defensive investigation of dangerous material should not be treated as equivalent to operational misuse.

### Treat AI Refusal as Security Telemetry

Unexpected refusals, truncations, or safety-trigger events during malware or incident analysis should be logged and correlated as potential security events.

A useful detection concept is:

**AI_ANALYSIS_REFUSAL**

This should be treated similarly to parser failure, sandbox timeout, telemetry loss, or tool-chain interruption.

### Use Multi-Path Analysis

High-risk objects should be analyzed through independent paths, for example:

**Static analysis + sandbox + deterministic extraction + LLM interpretation**

rather than:

**Artifact -> LLM -> verdict**

## Proposed Metrics

### AI Analysis Completion Rate

`AACR = Successfully completed AI investigations / Total AI investigations initiated`

### Safety-Triggered Investigation Failure Rate

`STIFR = Investigations interrupted by safety controls / Total investigations`

Unexpected changes in these metrics may indicate either policy misconfiguration or deliberate adversarial manipulation.

## Proposed MITRE ATT&CK and MITRE ATLAS Extension

SIAD exposes a gap between traditional cyber defense-evasion modeling and adversarial manipulation of AI-enabled security tooling.

### MITRE ATT&CK

A potential mapping is under **Defense Evasion**, describing adversarial manipulation of AI-enabled defensive tools to suppress, interrupt, or distort security analysis.

A future ATT&CK sub-technique could capture behaviors in which attackers modify artifacts or telemetry specifically to alter the behavior of AI-assisted security systems.

### MITRE ATLAS

MITRE ATLAS already covers AI-specific adversarial behaviors including prompt injection, evasion, and broader defense-evasion concepts. However, SIAD represents a distinct pattern in which the attack objective is to activate safety controls rather than bypass them.

A proposed ATLAS technique could be defined as:

**Safety-Induced Analysis Denial**

> Adversaries introduce policy-sensitive semantic content into artifacts or telemetry with the objective of triggering AI safety mechanisms and causing refusal, redaction, selective omission, or termination of defensive analysis.

### Cross-Framework Relationship

A conceptual mapping is:

**MITRE ATT&CK: Defense Evasion**  
-> **AI-enabled defensive analysis**  
-> **MITRE ATLAS: Safety-Induced Analysis Denial**  
-> **Safety trigger -> Analysis suppression -> Detection blind spot**

This mapping would strengthen the connection between conventional cyber TTPs and adversarial behaviors targeting AI-enabled defensive infrastructure.

## Detection Opportunities

Defenders should monitor for:

1. Sudden increases in AI refusals associated with suspicious artifacts.
2. Repeated safety-policy triggers associated with the same malware family, campaign, or source.
3. Discrepancies between deterministic tools and AI-generated summaries.
4. AI outputs that omit artifacts or behaviors present in raw telemetry.
5. Agent workflows that terminate immediately after content-safety classification.
6. Repeated semantic patterns that appear unrelated to the operational purpose of the analyzed object.

## Security Testing Guidance

Organizations using AI for security analysis should include SIAD-style tests in red-team and assurance programs.

Testing should focus on defensive resilience and avoid developing operationally useful evasion payloads. Relevant questions include:

- Does the system distinguish analyst intent from artifact content?
- Can safety controls silently suppress findings?
- Are refusals visible to the analyst and SOC telemetry?
- Does analysis continue through deterministic paths when AI refuses?
- Can downstream response actions continue when one AI component fails?
- Can the system identify semantic content whose primary purpose appears to be manipulation of the analysis pipeline?

## Broader Implications

SIAD illustrates a general AI-security principle:

> Any predictable model behavior may become part of an adversary's attack surface.

In traditional security, adversaries commonly attempt to evade or disable controls. In AI-enabled security, adversaries may also attempt to induce defenders to enforce their own controls against themselves.

This pattern may be relevant beyond malware analysis, including:

- Threat intelligence
- Digital forensics
- Vulnerability analysis
- Fraud investigation
- Phishing analysis
- Insider-risk investigation
- National-security intelligence analysis

## Key Takeaway

The question is no longer only:

**How can attackers bypass AI safety mechanisms?**

Defenders must also ask:

**How can attackers make our AI safety mechanisms protect them from us?**

## References

Check Point Research. (2025). *AI evasion: Prompt injection as a new malware evasion technique*. Check Point Software Technologies. https://research.checkpoint.com/2025/ai-evasion-prompt-injection/

JFrog Security Research. (2026). *Prompt injection vs. scanners: Can AI guardrails interfere with malware analysis?* JFrog. https://research.jfrog.com/post/prompt-injection-vs-scanners/

Karanjai, R., Lu, Y., Madhavarao, H. H., Xu, L., & Shi, W. (2026). *Context contamination in LLM analysis of network security logs: Poison with passive prompt injection and mitigation evaluation*. 35th USENIX Security Symposium. https://www.usenix.org/conference/usenixsecurity26/presentation/karanjai

MITRE. (n.d.). *MITRE ATT&CK*. https://attack.mitre.org/

MITRE. (n.d.). *MITRE ATLAS*. https://atlas.mitre.org/

OWASP Foundation. (2025). *LLM01: Prompt injection*. OWASP Generative AI Security Project. https://genai.owasp.org/llmrisk/llm01-prompt-injection/
