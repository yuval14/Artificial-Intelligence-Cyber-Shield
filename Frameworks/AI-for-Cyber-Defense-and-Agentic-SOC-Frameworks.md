# AI for Cyber Defense and Agentic SOC Frameworks

## Overview

This page covers open frameworks and research that apply AI and AI agents to defensive security operations while preserving human accountability, traceability, and operational control.

The core operational frameworks are:

1. **Agentic Threat Hunting Framework (ATHF)** - a structured framework for repeatable, evidence-based threat hunting.
2. **Agentic Detection Engineering Framework (ADEF)** - a lifecycle and durable-memory layer for developing, governing, tuning, and retiring detection rules.
3. **IAPS Detection-in-Depth for Offensive Cyber Agents** - an ecosystem-level approach combining novel agent detection mechanisms with existing defensive telemetry.
4. **Differential Access for Cyber-Capable Models** - a policy and operational approach for providing advanced cyber-capable AI preferentially or more safely to defenders while limiting misuse risk.

Together, these concepts provide a continuum from threat hypothesis to governed production detection and from local SOC operations to broader agentic threat detection and disruption.

```text
Threat intelligence or anomaly
        ↓
ATHF threat hunt
        ↓
Validated and repeatable signal
        ↓
ADEF detection promotion
        ↓
Production detection
        ↓
Detection-in-depth enrichment
        ↓
Governance, triage, sharing, tuning, and response
```

## 1. Agentic Threat Hunting Framework - ATHF

ATHF structures threat hunting through the **LOCK** lifecycle:

- **Learn** - establish the threat hypothesis, intelligence basis, scope, and assumptions.
- **Observe** - inspect available telemetry and establish relevant behavioral baselines.
- **Check** - test the hypothesis using repeatable queries, analytics, and evidence.
- **Keep** - preserve findings, decisions, queries, evidence, and lessons for future hunts.

ATHF helps transform threat hunting from an analyst-dependent activity into a repeatable and searchable body of operational knowledge. Its value is particularly relevant when AI agents assist analysts because agents require explicit context, evidence, and previous decisions rather than undocumented institutional knowledge.

### Primary value

- Standardizes threat-hunting activities.
- Preserves hunt reasoning and evidence.
- Supports collaboration between analysts and AI agents.
- Improves repeatability and organizational learning.
- Creates a potential pathway from hunt findings to detection engineering.

## 2. Agentic Detection Engineering Framework - ADEF

ADEF provides a durable-memory and lifecycle layer for detection engineering. It complements existing rules without requiring organizations to replace their SIEM, query language, or detection repository.

ADEF uses the **FORGE** lifecycle:

- **Find** - identify a coverage gap, threat-intelligence requirement, or validated hunt result.
- **Observe** - analyze baseline telemetry and expected behavior.
- **Refine** - test, backtest, compare, validate, and improve the detection logic.
- **Govern** - apply ownership, quality gates, approval, deployment controls, and review schedules.
- **Evolve** - tune, replace, deprecate, or retire the detection based on operational evidence.

ADEF places a structured journal and metadata record beside each detection. The record preserves why the detection exists, how it was validated, what tuning decisions were made, who approved changes, and when the rule should be reviewed again.

### Primary value

- Preserves institutional memory for detection rules.
- Supports native rule formats rather than introducing another query language.
- Provides cataloging, lifecycle tracking, schema checking, and ATT&CK coverage analysis.
- Enables AI assistants through CLI, skills, and MCP interfaces.
- Maintains a human-in-the-loop model in which agents propose and engineers approve.

## 3. ATHF and ADEF as complementary frameworks

| Dimension | ATHF | ADEF |
| --- | --- | --- |
| Primary discipline | Threat hunting | Detection engineering |
| Core question | Is this activity present in our environment? | How should this behavior become a governed production alert? |
| Lifecycle | LOCK | FORGE |
| Unit of work | Hunt | Detection rule and journal |
| Main output | Validated hunt finding and retained evidence | Tested, governed, and maintained detection |
| AI role | Assist hypothesis development, analysis, and knowledge retrieval | Assist authoring, validation, comparison, schema checking, and lifecycle recommendations |
| Human role | Approve scope, conclusions, and escalation | Approve rule logic, deployment, tuning, and retirement |

The two frameworks should be treated as paired operational frameworks rather than competing methodologies. ATHF develops and validates knowledge about adversary behavior. ADEF converts resilient and repeatable findings into maintained detections.

## 4. Offensive Cyber Agent Detection-in-Depth

IAPS argues that offensive cyber agents may create a detection gap because they combine autonomous tool use, rapid adaptation, scale, and low-cost iteration. Traditional EDR, NDR, identity, SIEM, and threat-intelligence controls remain necessary, but defenders may need additional layers designed specifically for agentic activity.

### Five IAPS mechanisms

| Mechanism | Defensive role | SOC integration |
| --- | --- | --- |
| Agent Identifiers for Critical Infrastructure | Persistent, cryptographically verifiable credentials or attestations attached to agent traffic | Ingest agent identifier, issuer, signature, workload binding, target, and revocation state into SIEM |
| Agent Honeypots | Decoys designed to attract autonomous attackers and reveal how they operate | Correlate decoy discovery, tool selection, honeytoken use, adaptation, and downstream actions |
| AI-Automated Alert Analysis and Triage | Use AI to filter and interpret high-volume agentic detection signals | Preserve source alerts, model analysis, confidence, rationale, policy decision, and analyst disposition |
| Agentic Security Alert Standard | Standardize the reporting of suspected agentic threats | Define a common schema for agent identity, evidence, actions, targets, confidence, and recommended response |
| Agentic Cybersecurity Exchange (ACE) | Coordinate model-provider and cloud-provider detection and disruption | Support provider-origin intelligence, cross-target correlation, revocation, and ecosystem disruption |

### Detection principle

```text
Agent-origin evidence
  + endpoint/network/identity telemetry
  + deception telemetry
  + policy and containment events
  + provider/cloud evidence
  = stronger agentic threat assessment
```

No single layer should be treated as definitive attribution.

### SOC telemetry additions

Agentic SOC programs should add:

- Agent and workload identity
- Model and provider
- Tool-call traces
- Prompt or protected prompt metadata
- Memory changes
- Sandbox and container boundary events
- Policy allow/deny decisions
- Approval state
- Kill-switch and stop events
- Credential revocations
- Egress-control events
- Deception and canary activation

The companion [Cybersecurity Detection Engineering repository](https://github.com/yuval14/Cybersecurity-Detection-Engineering) implements these concepts as detection and correlation scenarios.

## 5. Differential Access for Cyber-Capable Models

IAPS proposes **differential access** as a way to shape access to advanced cyber-capable AI so that defenders can benefit from the capability while risks from unrestricted offensive use are reduced.

The security objective is not simply to give defenders a more powerful model. Differential access should combine identity, authorization, capability limits, telemetry, evaluation, and governance.

### Defensive use cases

- Vulnerability discovery and prioritization
- Secure code review
- Detection engineering
- Threat hunting
- Malware analysis
- Incident triage
- Attack-path analysis
- Cyber-range testing
- Rapid remediation support

### Security requirements

| Requirement | Rationale |
| --- | --- |
| Verified organizational and user identity | Advanced capability should be attributable to approved defenders |
| Purpose-bound access | Access should be tied to defined defensive missions or use cases |
| Scoped tools and targets | Prevent model capability from silently expanding into unrestricted offensive use |
| Strong logging and provenance | Preserve prompts, tool calls, targets, actions, and approvals |
| Cyber-capability evaluation | Measure both defensive value and offensive misuse potential |
| Independent containment | High-capability models should not be able to bypass network, target, or tool boundaries |
| Tiered access | More capable models or tools may require stronger assurance and oversight |
| Abuse detection and revocation | Misuse signals should trigger investigation, step-up controls, suspension, or revocation |
| Post-deployment monitoring | Capability and behavior can change with tools, scaffolding, memory, and model updates |

### SOC interpretation

Differential access can be integrated with zero trust:

```text
Verified defender identity
  -> approved defensive purpose
  -> scoped cyber-capable model
  -> approved tools and target set
  -> policy gate
  -> monitored action
  -> evidence and review
```

## 6. Adoption considerations

A practical adoption sequence is:

1. Select one representative hunt and one production detection.
2. Document the hunt using the LOCK lifecycle.
3. Catalog the existing detection repository using ADEF in read-only mode.
4. Declare and validate the relevant telemetry schema.
5. Create or enrich the detection journal.
6. Test the rule against historical and representative data.
7. Require peer review and human approval before deployment.
8. Measure false-positive rate, alert volume, precision, data-source dependency, and review status.
9. Add agent identity, tool-call, containment, deception, and policy telemetry where AI agents are deployed.
10. Establish periodic tuning and retirement reviews.
11. For high-capability defensive models, implement differential access with purpose binding, target restrictions, and revocation.
12. Expand only after validating operational value and governance effectiveness.

## 7. Security and assurance assessment

Agentic SOC frameworks introduce additional security risks because AI assistants may access threat intelligence, detection logic, telemetry schemas, incident context, sensitive evidence, and operational tooling.

Required controls should include:

- Least-privilege access to repositories, SIEM exports, case data, and MCP tools.
- Read-only access by default.
- Explicit approval before rule creation, modification, deployment, suppression, or retirement.
- Provenance for intelligence, prompts, tool calls, generated queries, recommendations, and approvals.
- Validation of external threat-intelligence content against prompt injection and malicious instructions.
- Schema validation and semantic testing, not syntax validation alone.
- Separation of duties between authoring, testing, approval, and production deployment.
- Protection of detection logic and telemetry schemas as sensitive defensive information.
- Signed commits, branch protection, peer review, and auditable change management.
- Monitoring for poisoned journals, fabricated evidence, manipulated performance metrics, and automation bias.
- Independent testing of agent recommendations before production use.
- Defined rollback, kill-switch, and manual operating procedures.
- Default-deny egress and explicit target allowlists for offensive-cyber evaluation workloads.
- Independent containment controls that remain effective if the model or agent acts unexpectedly.

## 8. Limitations

- A syntactically correct rule may still be operationally ineffective.
- AI-generated detections may reflect incomplete telemetry or invalid assumptions.
- Historical backtesting does not guarantee future effectiveness.
- ATT&CK coverage counts can create false confidence if data quality and rule reliability are not considered.
- Institutional memory is useful only when journals are accurate, maintained, and protected from unauthorized modification.
- The ATHF-to-ADEF hunt-promotion bridge should be treated according to its implemented status rather than its planned architecture.
- Human approval does not eliminate automation bias; reviewers require sufficient time, evidence, and expertise.
- Agent identifiers and provider-origin evidence can improve confidence but do not eliminate identity theft, implementation defects, or attribution uncertainty.
- Differential access can reduce misuse risk but cannot by itself guarantee that powerful cyber capability remains defensive.

## 9. Relationship to other repositories

- This repository documents ATHF and ADEF as **AI-enabled cyber-defense and agentic SOC frameworks**.
- The [Cybersecurity Detection Engineering](https://github.com/yuval14/Cybersecurity-Detection-Engineering) repository implements detection-in-depth concepts as AIDAF, hunting scenarios, and SIEM correlations.
- The [AI Security Tooling](https://github.com/yuval14/AI-Security-Tooling) repository may reference CLI, MCP, skills, schema-validation, cataloging, and workbook capabilities as technical tooling.

## References

Covino, C., Kraprayoon, J., & Mittelsteadt, M. (2026, April 30). *Advancing America's cyber strategy with differential access*. Institute for AI Policy and Strategy. https://www.iaps.ai/research

Mittelsteadt, M., Kraprayoon, J., Staes-Polet, R., Galeev, O., Wehner, J., Covino, C., & Ee, S. (2026, May 19). *Detecting offensive cyber agents: A detection-in-depth approach*. Institute for AI Policy and Strategy. https://www.iaps.ai/research/detecting-offensive-cyber-agents

Nebulock Detection Engineering and Threat Hunting Team. (2026, July 28). *Agentic detection engineering framework: Durable memory for detections*. Nebulock. https://nebulock.io/blog/agentic-detection-engineering-framework

Nebulock, Inc. (2026). *Agentic detection engineering framework* [Computer software]. GitHub. https://github.com/Nebulock-Inc/agentic-detection-engineering-framework

Nebulock, Inc. (2026). *Agentic threat hunting framework* [Computer software]. GitHub. https://github.com/Nebulock-Inc/agentic-threat-hunting-framework
