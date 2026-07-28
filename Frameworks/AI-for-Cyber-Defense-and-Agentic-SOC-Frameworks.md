# AI for Cyber Defense and Agentic SOC Frameworks

## Overview

This page covers open frameworks that apply AI agents to defensive security operations while preserving human accountability, traceability, and operational control.

The two complementary frameworks reviewed here are:

1. **Agentic Threat Hunting Framework (ATHF)** - a structured framework for repeatable, evidence-based threat hunting.
2. **Agentic Detection Engineering Framework (ADEF)** - a lifecycle and durable-memory layer for developing, governing, tuning, and retiring detection rules.

Together, they provide a conceptual continuum from a threat hypothesis to a governed production detection.

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
Governance, tuning, review, and retirement
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

## 4. Adoption considerations

A practical adoption sequence is:

1. Select one representative hunt and one production detection.
2. Document the hunt using the LOCK lifecycle.
3. Catalog the existing detection repository using ADEF in read-only mode.
4. Declare and validate the relevant telemetry schema.
5. Create or enrich the detection journal.
6. Test the rule against historical and representative data.
7. Require peer review and human approval before deployment.
8. Measure false-positive rate, alert volume, precision, data-source dependency, and review status.
9. Establish periodic tuning and retirement reviews.
10. Expand only after validating operational value and governance effectiveness.

## 5. Security and assurance assessment

Agentic SOC frameworks introduce additional security risks because AI assistants may access threat intelligence, detection logic, telemetry schemas, incident context, and operational tooling.

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

## 6. Limitations

- A syntactically correct rule may still be operationally ineffective.
- AI-generated detections may reflect incomplete telemetry or invalid assumptions.
- Historical backtesting does not guarantee future effectiveness.
- ATT&CK coverage counts can create false confidence if data quality and rule reliability are not considered.
- Institutional memory is useful only when journals are accurate, maintained, and protected from unauthorized modification.
- The ATHF-to-ADEF hunt-promotion bridge should be treated according to its implemented status rather than its planned architecture.
- Human approval does not eliminate automation bias; reviewers require sufficient time, evidence, and expertise.

## 7. Relationship to other repositories

- This repository documents ATHF and ADEF as **AI-enabled cyber-defense and agentic SOC frameworks**.
- The [Cybersecurity Detection Rules](https://github.com/yuval14/Cybersecurity-Detection-Rules) repository documents their operational relevance to threat hunting, detection-as-code, rule quality, and lifecycle management.
- The [AI Security Tooling](https://github.com/yuval14/AI-Security-Tooling) repository may reference their CLI, MCP, skills, schema-validation, and cataloging capabilities as technical tooling.

## References

Nebulock Detection Engineering and Threat Hunting Team. (2026, July 28). *Agentic detection engineering framework: Durable memory for detections*. Nebulock. https://nebulock.io/blog/agentic-detection-engineering-framework

Nebulock, Inc. (2026). *Agentic detection engineering framework* [Computer software]. GitHub. https://github.com/Nebulock-Inc/agentic-detection-engineering-framework

Nebulock, Inc. (2026). *Agentic threat hunting framework* [Computer software]. GitHub. https://github.com/Nebulock-Inc/agentic-threat-hunting-framework
