# Kimi Claw and the Security Risks of Always-On AI Agents

## Overview

In February 2026, the Institute for AI Policy and Strategy (IAPS) published an analysis of **Kimi Claw**, an always-on AI agent offered by Moonshot AI. The report is useful beyond the specific product because it illustrates a broader security pattern: a persistent agent that can observe, collect, process, and act across a user's files, applications, communications, browser activity, and connected services.

This page treats Kimi Claw as a case study in **persistent cross-application agent risk**, not as evidence that every foreign-hosted or always-on agent is malicious. Product-specific, legal, and jurisdictional claims should be verified against primary sources before they are used for regulatory, procurement, or national-security decisions.

## Why always-on agents change the risk model

A conventional SaaS application generally operates within a defined application boundary. An always-on agent may combine:

- Continuous observation
- Cross-application access
- Local file access
- Browser and session access
- Messaging and collaboration access
- Third-party integrations and skills
- Long-term memory
- Tool use and external actions
- Persistent cloud connectivity

The resulting security boundary is not a single application. It is the aggregate of every resource the agent can observe or affect.

```text
User identity
  -> persistent agent
  -> files + browser + apps + messages + memory
  -> skills / plugins / APIs
  -> remote model/provider infrastructure
  -> external actions
```

## Core security risks

| Risk | Description | Minimum control |
| --- | --- | --- |
| Broad data exposure | Agent can access sensitive information across multiple applications and contexts | Data classification, least privilege, per-source consent, DLP |
| Cross-context leakage | Data from one application can influence actions in another | Context separation, origin labels, transaction boundaries |
| Prompt injection | Malicious content in messages, webpages, files, or documents can influence the agent | Untrusted-content isolation, instruction separation, tool authorization |
| Skill or plugin compromise | Third-party extensions expand the attack surface | Signed packages, allowlists, provenance, code review, sandboxing |
| Remote code execution | Vulnerable agent frameworks can create a path to arbitrary execution | Application control, sandboxing, patching, restricted execution |
| Credential exposure | Persistent agent access may include tokens, cookies, secrets, wallets, or cloud credentials | Secret isolation, short-lived credentials, browser/session separation |
| Persistent surveillance | Continuous service operation can create extensive behavioral and content visibility | Data minimization, local processing where appropriate, retention limits, privacy review |
| Jurisdictional exposure | Provider legal obligations and infrastructure location may affect access to data | Data residency review, legal assessment, provider risk classification |
| Strategic dependency | Deep workflow integration can make later migration or restriction difficult | Portability, exit plan, dependency inventory, alternative providers |
| Enterprise shadow-agent adoption | Users may connect consumer agents to corporate data without security review | Discovery, CASB/SSE controls, endpoint policy, approved-agent registry |

## Supply-chain and ecosystem risk

Always-on agents frequently rely on a modular ecosystem of skills, connectors, plugins, or MCP-like integrations. Each component can become a trust boundary.

Required controls should include:

1. Maintain an inventory of installed skills, plugins, connectors, and APIs.
2. Verify source, publisher, integrity, and update channel.
3. Restrict permissions per integration.
4. Prevent a plugin from inheriting the agent's full authority by default.
5. Review transitive dependencies and package-install behavior.
6. Log tool registration, permission changes, and new integrations.
7. Disable unapproved marketplace installation on managed endpoints.
8. Test malicious and compromised-skill scenarios.

## Enterprise detection requirements

High-value telemetry includes:

- Agent process and browser-extension inventory
- SaaS and API access logs
- File access and DLP events
- Browser session and cookie access
- Credential and secret-manager telemetry
- OAuth grants and token scopes
- Plugin or skill installation
- Network connections to agent providers
- Tool calls and external actions
- Agent memory reads and writes where available

Recommended detections include:

```text
Unapproved always-on agent
  -> sensitive file or browser-session access
  -> new external destination
```

```text
Agent
  -> new skill/plugin installation
  -> credential access
  -> shell, browser automation, or external API action
```

```text
Corporate account
  -> consumer agent OAuth grant
  -> broad mailbox / drive / collaboration scopes
  -> persistent background access
```

## Procurement and governance questions

- Where is the agent hosted and where is user data processed?
- Which legal entities provide the service?
- Which jurisdictions can compel access to data?
- Can the agent access local files, browser sessions, messages, cloud drives, or corporate applications?
- What scopes are granted through OAuth or other delegated authorization?
- Can third-party skills execute code or make external requests?
- Is agent memory persistent and exportable?
- Can the organization disable the agent and revoke all delegated access quickly?
- Are prompts, files, tool calls, and outputs retained or used for training?
- Is there an enterprise version with contractual security, audit, and data-residency controls?

## National-security relevance

For government and critical-infrastructure environments, persistent cross-application agents deserve additional scrutiny because they can concentrate access to communications, documents, credentials, workflows, and operational context in one service.

Relevant assessment dimensions include:

- Provider ownership and control
- Legal jurisdiction
- Data residency
- Model and infrastructure supply chain
- Software update path
- Plugin ecosystem
- Security incident history
- Ability to conduct remote actions
- Access to government or contractor systems
- Strategic dependency and exit feasibility

The appropriate policy response is jurisdiction- and mission-dependent. The technical principle is general: **the more persistent and cross-context an agent becomes, the more its effective authority must be measured and constrained.**

## Relationship to other repository resources

- [AI Agent Security](../Frameworks/AI-Agent-Security.md)
- [CUSTODY Autonomous Agent Containment Framework](../Frameworks/CUSTODY-Autonomous-Agent-Containment-Framework.md)
- [System Hardening Against AI and Agentic AI Threats](../System-Hardening/System-Hardening-Against-AI-Threats.md)
- [AI Integrity](../Frameworks/AI-Integrity.md)
- [OWASP State of Agentic AI Security and Governance](../Frameworks/OWASP-State-of-Agentic-AI-Security-and-Governance.md)

## APA 7 Reference

Bearman, T. (2026, February 25). *Kimi Claw: Risks from Chinese-hosted 'always on' AI agents*. Institute for AI Policy and Strategy. https://www.iaps.ai/research/kimi-claw-risks
