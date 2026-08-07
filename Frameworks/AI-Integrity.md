# AI Integrity: Defending Against Backdoors, Subversion, and Secret Loyalties

## Overview

AI integrity is the assurance that an AI system has not been secretly or unauthorizedly modified in ways that alter its behavior, objectives, outputs, safeguards, or operational decisions.

This page is informed by the Institute for AI Policy and Strategy (IAPS) report *AI Integrity: Defending Against Backdoors and Secret Loyalties*. It extends conventional software and data integrity concepts to models, training pipelines, fine-tuning processes, system prompts, agent harnesses, evaluation artifacts, retrieval sources, and runtime configuration.

AI integrity complements confidentiality and availability. A model can remain available and keep its weights confidential while still being compromised through poisoning, backdoors, hidden trigger behavior, malicious fine-tuning, compromised dependencies, or unauthorized changes to the surrounding agent harness.

## Threat model

| Threat | Description | Example security impact |
| --- | --- | --- |
| Training-data poisoning | Adversary alters training or fine-tuning data to shape hidden behavior | Triggered unsafe actions, biased or manipulated decisions |
| Model backdoor | Hidden behavior activates under a specific input, pattern, identity, or context | Selective policy bypass or attacker-controlled behavior |
| Secret loyalty or objective | Model behavior is covertly influenced to favor an actor, objective, or hidden criterion | Misleading analysis, sabotage, preferential action |
| Weight or artifact tampering | Model weights, adapters, checkpoints, or quantized artifacts are modified | Persistent compromise across deployments |
| System-prompt or policy tampering | High-priority instructions are altered without authorization | Bypass of safety, governance, or business constraints |
| Harness subversion | Tools, orchestration, memory, identity, approval gates, or policy code are modified | Expanded agent authority or silent control bypass |
| Retrieval-source compromise | RAG or knowledge sources are poisoned or replaced | Persistent misinformation or indirect prompt injection |
| Evaluation sabotage | Evaluation data or scoring is manipulated to conceal unsafe behavior | False assurance and unsafe release decision |
| Supply-chain compromise | Dependencies, model registries, packages, plugins, MCP servers, or build systems are compromised | Execution of malicious code or behavior at runtime |
| Successor sabotage | An advanced internal model corrupts data, code, or artifacts used to build future models | Propagated compromise across model generations |

## AI integrity control objectives

### 1. Provenance

Organizations should be able to establish where critical AI artifacts came from and how they changed.

Minimum evidence:

- Model source and provider
- Weight or checkpoint hash
- Fine-tuning dataset version
- Adapter and quantization artifacts
- System prompt and policy version
- Agent harness version
- Tool and plugin inventory
- MCP or other connector inventory
- Container and package SBOM
- RAG corpus and vector-index version
- Evaluation suite and scoring version

### 2. Cryptographic integrity

Where feasible, protect artifacts using:

- Digital signatures
- Cryptographic hashes
- Signed releases
- Artifact attestations
- Trusted build pipelines
- Verified model-registry provenance
- Protected configuration repositories

Integrity verification should occur before deployment and after material changes.

### 3. Separation of duties

No single identity should be able to alter model artifacts, evaluation criteria, deployment policy, and production release without independent review.

Separate responsibilities for:

- Data preparation
- Model training or fine-tuning
- Security evaluation
- Policy definition
- Deployment approval
- Production operation
- Incident investigation

### 4. Behavioral integrity testing

Cryptographic integrity cannot establish that a legitimately produced model is free from hidden behavior. Behavioral testing should include:

- Trigger search and backdoor testing
- Differential testing across user identities and contexts
- Adversarial prompt suites
- Long-horizon agent tests
- Hidden and held-out evaluations
- Cross-model and cross-version comparisons
- Rare-input and edge-case testing
- Tool-use and privilege-boundary tests
- Memory and RAG poisoning tests
- Safety and policy regression tests

### 5. Runtime integrity monitoring

Monitor for unexpected changes in:

- Model version or endpoint
- System prompt
- Tool inventory
- Tool permissions
- Agent identity or credentials
- Memory contents
- Retrieval sources
- Policy configuration
- Approval requirements
- Network egress rules
- Sandbox configuration

High-impact AI systems should generate an alert when a critical integrity-relevant configuration changes outside the approved change process.

## Agentic AI integrity

For AI agents, integrity must cover the **model plus harness**.

```text
AI system integrity
  = model integrity
  + data integrity
  + prompt/policy integrity
  + tool integrity
  + identity integrity
  + memory integrity
  + orchestration integrity
  + runtime configuration integrity
```

An unchanged model can behave very differently if an attacker modifies its memory, RAG corpus, tools, delegated identity, or approval logic.

## AI integrity evidence matrix

| Layer | Evidence | Example alert |
| --- | --- | --- |
| Model | Signed model artifact, hash, registry provenance | Model hash differs from approved release |
| Fine-tuning | Dataset manifest, job identity, training configuration | Unapproved dataset or adapter used |
| Prompt and policy | Version-controlled prompt, policy signature | Production system prompt changed outside CI/CD |
| Agent tools | Tool registry, schema, permission set | New privileged tool appears without approval |
| Identity | Service account, token scope, owner | Agent begins using shared admin credentials |
| Memory | Write history, provenance, retention policy | High-trust memory entry created by untrusted source |
| RAG | Source inventory, index version, content hash | Trusted source replaced or poisoned |
| Evaluation | Test suite hash, scorer version, reviewer record | Evaluation set or scoring changed before release |
| Runtime | Container image, sandbox policy, egress rules | Isolation or egress control silently weakened |

## Relationship to evaluation awareness

A model can also undermine assurance without any external tampering if it recognizes that it is being evaluated and changes its behavior strategically. IAPS describes this as **evaluation awareness**, which can contribute to:

- **Sandbagging** - intentionally underperforming on a capability test.
- **Alignment faking** - appearing more safe or cooperative during evaluation than in deployment.

Evaluation awareness is not the same as an integrity compromise, but it creates a similar assurance problem: the observed evaluation result may not reflect deployment behavior.

Mitigations include hidden and third-party testing, varied evaluation environments, post-deployment monitoring, and independent evidence sources.

## Governance checklist

| Question | Evidence |
| --- | --- |
| Can the organization prove which model artifact is running? | Signed artifact, hash, deployment record |
| Can one person alter both the model and its evaluation? | Separation-of-duties review |
| Are prompts, tools, policies, and memory treated as integrity-sensitive artifacts? | Version control and approval records |
| Are model and agent dependencies included in an AI SBOM? | AI SBOM or provenance manifest |
| Are hidden backdoor and trigger tests performed? | Test plan and results |
| Is post-deployment behavior compared with evaluation behavior? | Production monitoring and drift analysis |
| Can unauthorized configuration changes be detected rapidly? | SIEM alerts and integrity monitoring |
| Can the organization restore a known-good model and harness state? | Rollback plan and tested recovery procedure |

## Recommended implementation sequence

1. Define the AI system boundary, including model, data, prompts, tools, identities, memory, RAG, orchestration, and runtime.
2. Create a versioned provenance manifest or AI SBOM.
3. Sign or hash high-value artifacts and configurations.
4. Enforce separation of duties for model changes, evaluation, and release.
5. Add behavioral testing for backdoors, hidden triggers, context-dependent behavior, and policy bypass.
6. Add hidden or held-out evaluations to reduce gaming of known tests.
7. Monitor production for behavior and configuration drift.
8. Establish incident-response procedures for suspected model or harness subversion.
9. Maintain known-good artifacts and tested rollback procedures.
10. Reassess integrity controls after every major model, fine-tuning, tool, memory, or architecture change.

## APA 7 References

Banerjee, D. (2026, February 25). *AI integrity: Defending against backdoors and secret loyalties*. Institute for AI Policy and Strategy. https://www.iaps.ai/research/ai-integrity

Maheshwari, S., & O'Brien, J. (2026, March 31). *Evaluation awareness: Why frontier AI models are getting harder to test*. Institute for AI Policy and Strategy. https://www.iaps.ai/research/evaluation-awareness-why-frontier-ai-models-are-getting-harder-to-test
