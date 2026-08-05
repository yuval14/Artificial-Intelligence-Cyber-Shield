# OWASP State of Agentic AI Security and Governance

## Overview

The OWASP GenAI Security Project published *State of Agentic AI Security and Governance 2.01* on June 1, 2026. The report provides an integrated view of security architecture, governance, maturity, identity, supply-chain provenance, regulatory alignment, runtime monitoring, and operational risk for autonomous and semi-autonomous AI systems.

This page translates the report into implementation guidance for the Artificial Intelligence Cyber Shield repository.

Official resource: https://genai.owasp.org/resource/state-of-agentic-ai-security-and-governance/

## Why this resource matters

The report closes an important gap between technical agent security and enterprise governance. It should be used together with the repository's existing agent security, governance, assurance, red-team, maturity, and incident-response resources.

Key contributions include:

- A structured taxonomy for agentic systems.
- Governance maturity aligned to deployment complexity and autonomy.
- Non-human identity and delegated authorization requirements.
- AI software bill of materials and provenance expectations.
- Composition-specific risks for single-agent, multi-agent, distributed, and dynamically spawned architectures.
- Continuous runtime governance rather than periodic compliance review alone.
- Operational controls for fully autonomous agents.
- Integration of real-world agentic AI incidents and exploits into governance and control design.

## Agentic AI classification model

Security and governance decisions should begin by classifying each agentic system across four dimensions.

| Dimension | Example classifications | Security relevance |
| --- | --- | --- |
| Operational role | Enterprise, coding, client-facing, personal, infrastructure | Determines data sensitivity, operational impact, and accountability |
| Implementation pattern | Orchestration framework, SDK composition, low-code platform, custom application | Determines dependency, plug-in, and platform risks |
| Composition pattern | Single agent, multi-agent system, distributed chain, parallel fleet, dynamic spawning | Determines trust propagation, identity, memory, and blast-radius risks |
| Autonomy level | Advisory, assisted, supervised, bounded autonomous, fully autonomous | Determines approval, monitoring, runtime enforcement, and recovery requirements |

The generic label "AI agent" is insufficient for control selection. The operational role, architecture, and autonomy level must be recorded in the agent inventory.

## Governance-to-deployment alignment

The governance capability of an organization should match the most advanced agent deployment it operates.

> Raise governance maturity to match the deployment, or reduce the deployment's autonomy, access, and operational scope.

Governance mismatch indicators include:

- Autonomous agents operating under policies designed for chatbots.
- Production agents that are absent from the asset inventory.
- Low-code or departmental agents using enterprise data without centralized review.
- Agents with external-action permissions but no pre-action authorization.
- Multi-agent workflows without identity preservation across delegation chains.
- Runtime behavior that cannot be reconstructed after an incident.

## Agent inventory and Shadow Agentic AI

An organization cannot govern agents it has not discovered. The inventory should include approved, experimental, embedded, third-party, departmental, low-code, and unsanctioned agents.

Minimum inventory fields:

| Field | Required evidence |
| --- | --- |
| Agent name and unique identifier | Registry entry and technical identity |
| Business owner | Named accountable person or function |
| Operational role | Recorded use case and intended users |
| Autonomy level | Approved autonomy classification |
| Composition pattern | Architecture diagram and trust boundaries |
| Models and providers | Model inventory, versions, and hosting location |
| Tools and external actions | Tool inventory, scopes, and transaction limits |
| Data and memory access | Data classification, sources, retention, and write permissions |
| Identities and credentials | Service identity, delegated authority, token scope, and rotation policy |
| Runtime environment | Platform, network access, sandboxing, and isolation controls |
| Monitoring and response | Logs, traces, alerts, kill switch, rollback, and incident owner |
| Regulatory scope | Applicable sectoral, privacy, safety, and AI obligations |

Discovery controls should cover cloud services, SaaS integrations, browser extensions, developer tools, workflow automation platforms, API keys, service accounts, model endpoints, and outbound connections to agent platforms.

## Non-human identity and delegated authorization

Each agent and material sub-agent should have a bounded, attributable, and revocable identity.

Minimum controls:

1. Assign a unique identity to each production agent and high-risk sub-agent.
2. Record the initiating user, acting agent, delegated authority, model, tool, action, and result.
3. Use short-lived, narrowly scoped credentials.
4. Prevent dynamically spawned agents from inheriting unrestricted parent permissions.
5. Authenticate agent-to-agent communications.
6. Preserve authorization context across delegation chains.
7. Separate agent credentials from developer and administrator credentials.
8. Support immediate revocation and emergency isolation.
9. Review dormant, orphaned, shared, and over-privileged agent identities.
10. Require independent approval for privilege elevation and high-impact transactions.

## AI SBOM and provenance

Agentic systems introduce dependencies beyond traditional software components. An AI software bill of materials should record the components that influence decisions and actions.

Minimum AI SBOM scope:

- Models, versions, providers, and hosting environments.
- Agent frameworks, orchestration libraries, and SDKs.
- Tools, plug-ins, connectors, and external APIs.
- MCP, A2A, ACP, or other agent communication protocols.
- System prompts, policies, templates, and configuration versions.
- Retrieval sources, vector stores, memory services, and data pipelines.
- External agents and delegated services.
- Traditional packages, containers, and transitive dependencies.
- Security advisories, vulnerabilities, and compensating controls.
- Provenance, integrity evidence, signatures, or attestations where feasible.

Changes to models, prompts, policies, tools, memory schemas, or external-agent dependencies should trigger security review and regression testing.

## Composition-specific risks and controls

| Composition pattern | Primary risks | Minimum controls |
| --- | --- | --- |
| Single agent with tools | Unsafe combinations of data access and action capability | Tool allowlists, least privilege, parameter validation, approval gates |
| Multi-agent system | Shared-memory poisoning, orchestrator compromise, cascading instructions | Agent isolation, trust labels, signed messages, memory segmentation, workflow policy enforcement |
| Distributed agent chain | Trust transitivity, identity dilution, incomplete evidence | End-to-end identity preservation, authorization propagation, signed handoffs, complete tracing |
| Dynamically spawned agents | Permission inheritance, uncontrolled scale, expanding blast radius | Spawn limits, restricted child identities, maximum depth, quotas, automatic expiry |
| Parallel agent fleet | Correlated failures, aggregate cost, review overload | Fleet-level limits, diversity testing, coordinated stop controls, aggregate anomaly detection |

## Runtime governance

Periodic reviews alone are inadequate for agents that can act at machine speed. Governance controls should operate continuously before, during, and after execution.

Required capabilities:

- Deterministic pre-action authorization for sensitive operations.
- Continuous policy evaluation.
- Behavioral baselines and drift detection.
- Monitoring of action sequences, not only individual tool calls.
- Detection of cumulative slow-and-low behavior.
- Runtime limits for cost, tokens, compute, API calls, transactions, and execution time.
- Circuit breakers for recursion, repeated failures, and unusual tool sequences.
- Automated permission reduction or isolation when high-confidence anomalies occur.
- Escalation routes for safety, security, privacy, legal, and operational incidents.
- Stop mechanisms that can operate within the time required by the deployment risk.
- Evidence capture sufficient for forensic reconstruction and accountability.

## Controls for fully autonomous agents

Fully autonomous or externally acting agents require stronger controls than advisory or supervised systems.

| Control area | Minimum requirement |
| --- | --- |
| Resource consumption | Compute, token, API, budget, and execution-time limits |
| Transactions | Per-action and cumulative transaction limits |
| Delegation | Maximum delegation depth and maximum spawned-agent count |
| Identity | Dedicated identity with narrowly scoped permissions |
| Authorization | Deterministic policy enforcement before high-impact actions |
| Human oversight | Independent approval for irreversible or exceptional actions |
| Monitoring | Real-time traces, sequence analytics, anomaly detection, and alerting |
| Containment | Kill switch, credential revocation, network isolation, and tool disablement |
| Recovery | Rollback, state restoration, memory correction, and forensic preservation |
| Assurance | Adversarial testing, failure-injection exercises, and periodic red-team assessment |

## Governance and security convergence

At the deployment layer, AI safety, AI security, privacy, compliance, and operational resilience should use an integrated control model. The same identities, permissions, tools, configurations, monitoring systems, and response mechanisms often determine both accidental and adversarial harm.

This does not eliminate separate accountability functions. It requires shared evidence, control ownership, escalation criteria, and runtime enforcement across those functions.

## Maturity model extension

| Level | Description | Agentic AI indicators |
| --- | --- | --- |
| 0 - Unmanaged | Agents are experimental or unknown | No complete inventory, informal access, minimal logs |
| 1 - Identified | Agents and owners are recorded | Basic inventory, approved use cases, manual review |
| 2 - Controlled | Access and actions are bounded | Scoped identities, approval gates, quotas, standard testing |
| 3 - Governed | Policy and monitoring are integrated | Policy-as-code, AI SBOM, runtime telemetry, incident playbooks |
| 4 - Adaptive | Governance responds continuously | Drift detection, automated isolation, continuous evaluation, fleet-level controls |
| 5 - High assurance | High-impact agents operate under independently validated controls | Formal risk acceptance, adversarial testing, provenance, resilient recovery, independent assurance |

An organization should assess maturity separately for governance, identity, architecture, supply chain, runtime monitoring, incident response, and assurance. The lowest material domain may constrain the acceptable autonomy of the deployment.

## Assessment checklist

| Question | Evidence to collect |
| --- | --- |
| Are all production and experimental agents inventoried? | Discovery results, registry, exception records |
| Is each agent classified by role, composition, and autonomy? | Architecture and risk records |
| Does governance maturity match the highest-risk deployment? | Maturity assessment and risk acceptance |
| Can each action be attributed to a user, agent, identity, model, and tool? | Identity mapping and trace records |
| Are agent credentials short-lived and scoped? | IAM configuration and access reviews |
| Can child agents inherit excessive permissions? | Spawn-policy tests and authorization configuration |
| Is there an AI SBOM covering models, prompts, tools, protocols, memory, and dependencies? | Versioned AI SBOM and provenance records |
| Are sensitive actions evaluated by deterministic policy before execution? | Policy-as-code and negative test evidence |
| Are slow-and-low or cumulative behaviors detected? | Sequence analytics, thresholds, and hunting scenarios |
| Can the organization stop and recover an agent quickly? | Kill-switch exercise, revocation test, rollback evidence |
| Are incidents linked back to control and governance improvements? | Post-incident reviews and control backlog |

## Repository integration

Use this resource with:

- [AI Agent Security](AI-Agent-Security.md)
- [AI Governance and Assurance](AI-Governance-and-Assurance.md)
- [AI Governance, Risk, and Assurance Frameworks](AI-Governance-Risk-and-Assurance-Frameworks.md)
- [CUSTODY Autonomous Agent Containment Framework](CUSTODY-Autonomous-Agent-Containment-Framework.md)
- [Layered Attack Surface Model](Layered-Attack-Surface-Model-LASM.md)
- [OWASP AI Maturity Assessment](../AI-Maturity-Model/OWASP-AI-Maturity-Assessment.md)

The OWASP Agentic AI Security Incidents and Exploits repository should also be used to convert documented incidents into threat models, detection logic, red-team tests, and governance improvements:

https://owasp-agentic-ai-security-incidents.lovable.app/

## APA 7 reference

Open Worldwide Application Security Project. (2026, June 1). *State of agentic AI security and governance 2.01*. OWASP GenAI Security Project. https://genai.owasp.org/resource/state-of-agentic-ai-security-and-governance/
