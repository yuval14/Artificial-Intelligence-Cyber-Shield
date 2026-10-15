# AI Cyber Deception

## Overview
AI cyber deception applies honeypots, honeytokens, canaries, decoy tools, false paths, and adversarial context to detect, delay, divert, or study malicious AI agents. Context Bombs are one emerging technique in this area: carefully placed instructions or signals intended to influence an autonomous adversarial agent that reads them.

## Deception Techniques

| Technique | Description | Primary Goal | Example Use |
|---|---|---|---|
| Context Bomb | Adversarial instructions embedded in content likely to be processed by an AI agent | Disrupt, redirect, or expose hostile agent behavior | Instructions placed in decoy files or web content |
| Canary Prompt | A unique instruction or phrase that triggers an alert when processed | Detection | Hidden marker in sensitive documents |
| Honeytoken | Fake credential, API key, account, or secret monitored for use | Detection and attribution | Decoy cloud key or database token |
| Honeypot | Instrumented system or service designed to attract attackers | Observation and delay | Fake server, application, or admin portal |
| Honey Tool | Decoy agent tool that records invocation attempts | Detect compromised agents | Fake file reader or privileged API |
| Decoy Memory | Synthetic memory entry designed to reveal unauthorized retrieval | Detect memory scraping or poisoning | Fake project secret in vector memory |
| False Path | Plausible but controlled route that diverts the agent | Delay and containment | Decoy privilege-escalation path |
| Deceptive RAG Corpus | Instrumented retrieval content with controlled false leads | Detection and behavior analysis | Synthetic documents in a monitored index |
| Tripwire Action | A prohibited action that immediately triggers containment | Rapid response | Agent request for a forbidden credential |

## Context Bomb Lifecycle

| Phase | Defender Action | Expected Agent Interaction | Defensive Outcome |
|---|---|---|---|
| Design | Create a plausible instruction or deceptive signal | Agent interprets content as relevant context | Establishes behavioral trigger |
| Placement | Insert into decoy files, pages, tools, or memory | Agent discovers the artifact | Increases likelihood of engagement |
| Observation | Monitor access and downstream behavior | Agent follows, ignores, or sanitizes the instruction | Reveals agent capabilities and safeguards |
| Containment | Restrict tools, credentials, and network access | Agent attempts an action | Prevents real damage |
| Analysis | Correlate telemetry across the attack path | Agent behavior is reconstructed | Supports detection engineering and attribution |
| Adaptation | Update deception patterns and decoys | Future agents face revised traps | Maintains effectiveness against adaptation |

## Defensive Value and Limitations

| Dimension | Value | Limitation |
|---|---|---|
| Detection | Can identify automated reconnaissance and tool use | Sophisticated agents may avoid or sanitize suspicious content |
| Delay | Diverts agents into controlled paths | Delay may be brief against adaptive planners |
| Intelligence | Reveals prompts, tools, models, and decision patterns | Observations may not uniquely identify the operator |
| Containment | Works well when paired with sandboxing and scoped access | Deception alone does not block authorized pathways |
| Cost asymmetry | Low-cost artifacts may consume attacker resources | Maintenance is required to remain believable |
| Research | Enables controlled study of agent behavior | Results may not generalize across models and architectures |

## Recommended Architecture

| Component | Function | Security Requirement |
|---|---|---|
| Deception Orchestrator | Creates and rotates decoys | Must prevent collision with legitimate production assets |
| Context Bomb Repository | Stores tested defensive context patterns | Version control, approval, and safety review |
| Canary Telemetry | Records access and activation | Tamper-resistant logging and correlation |
| Policy Enforcement Point | Blocks unauthorized actions | Deterministic enforcement outside the model |
| Sandbox | Isolates suspicious agent activity | Restricted filesystem, network, and credentials |
| Response Engine | Quarantines sessions and rotates exposed secrets | Fast, auditable, and reversible actions |
| Analysis Layer | Reconstructs agent trajectories | Full provenance and time synchronization |

## Operational Scenarios

| Scenario | Deception Asset | Detection Signal | Recommended Response |
|---|---|---|---|
| AI agent scans source repositories | Decoy configuration file with canary secret | File access or secret use | Block session and rotate adjacent credentials |
| Agent browses internal documentation | Context Bomb in a restricted decoy page | Navigation to controlled endpoint | Isolate browser tool and preserve evidence |
| Agent searches long-term memory | Decoy memory entry | Retrieval or action based on decoy | Quarantine memory and inspect write history |
| Agent probes privileged tools | Honey Tool | Invocation attempt | Revoke capability token and terminate execution |
| Agent conducts autonomous lateral movement | False administrative path | Access to decoy account or host | Trigger high-priority incident response |

## Safety and Governance

| Governance Question | Required Control |
|---|---|
| Could the deception affect legitimate users or agents? | Scope decoys to controlled environments and authenticated threat paths |
| Could false data enter business decisions? | Separate deception infrastructure from production data planes |
| Are interactions legally and ethically monitored? | Obtain legal approval and document monitoring boundaries |
| Can responders distinguish decoys from real assets? | Maintain authoritative inventory and labeling outside attacker-visible channels |
| Can deception actions be audited? | Log creation, deployment, activation, and response decisions |
| Could a Context Bomb cause uncontrolled actions? | Use only in sandboxed or policy-constrained environments |

## Research Priorities

| Research Area | Key Question |
|---|---|
| Agent-aware honeypots | How should decoys change when the attacker is an autonomous model rather than a human? |
| Context Bomb robustness | Which defensive instructions remain effective across models and agent frameworks? |
| Counter-sanitization | How can defenders detect agents that summarize or strip adversarial context before reasoning? |
| Attribution | Which behavioral signals help distinguish tools, models, operators, and campaigns? |
| Adaptive deception | Can decoys change safely in response to observed agent behavior? |
| Deception metrics | How should delay, diversion, detection, and intelligence value be measured? |

## Selected Research and Evidence

Last reviewed: 2026-10-16. This is a selected comparison, not a systematic literature review. Numerical results belong to their reported experimental conditions.

| Work and status | Mechanism and setting | Reported evidence | Limitation |
|---|---|---|---|
| [CHeaT](https://www.usenix.org/conference/usenixsecurity25/presentation/ayzenshteyn), USENIX Security 2025, peer-reviewed | Ben-Gurion University researchers combine asset cloaking, honeytokens, and traps against autonomous penetration-testing agents | Authors report protection of 11 CTF machines with 100% success in their evaluated setup; most techniques do not require prompt injection | CTF results do not establish production reliability or transfer to later models |
| [AgentTrap](https://arxiv.org/abs/2610.02869), October 2, 2026, arXiv preprint | Stateful feedback deception against eight penetration-testing agents in a web application | Reported aggregate real-target attack success fell from 95.8% without defense to 79.2%; attacker API keys were elicited in 18.8% of runs | Substantial residual attack success; limited setting; peer review not established by the arXiv record |
| [Honeyval](https://arxiv.org/abs/2605.29963), May 28, 2026, arXiv preprint | Evaluation of LLM-powered HTTP honeypots grounded in 16 backend applications with AI hacking agents and control tasks | Authors report longer interactions and less frequent detection than rule-based baselines | Evaluates HTTP simulation and attacker interaction, not a universal containment boundary |
| [IAPS insider-threat report](https://www.iaps.ai/research/honeypots-for-ai-agent-insider-threats), October 15, 2026, research report | Decoy opportunities for unauthorized actions by internal agents | Separates detection, evidence gathering, and deterrence; evidence is strongest for detection | Production evidence for distinguishing mistakes from deliberate misconduct is limited; deterrence remains a research hypothesis |

### Interpretation for deployment

These works address different targets: external hostile agents, simulated services, and trusted-access internal agents. Their success rates are not interchangeable. A trigger does not by itself establish malicious intent, model identity, or operator attribution.

The research includes counter-offensive techniques. Their inclusion in this survey is not an operational recommendation to execute code on third-party systems or collect real attacker credentials. Defensive pilots should use isolated assets and synthetic secrets with explicit engagement scope.

### Evaluation checklist

The following is repository engineering guidance, rather than a published benchmark:

- Compare against no-deception and static-deception baselines under the same attack budget.
- Include legitimate agents to measure false alerts and disruption of authorized work.
- Separate decoy discovery, access, attempted use, successful diversion, and blocked impact.
- Record target compromise as well as interaction duration; delay alone is not protection.
- Repeat across models, harnesses, retries, and previously unseen decoy variants.
- Record cost, time to alert, time to containment, and the attack paths without decoy coverage.

See [Agent Monitoring and Control Evaluation](Agent-Monitoring-and-Control-Evaluation.md) for reporting definitions.

## References

Ayzenshteyn, D., Weiss, R., & Mirsky, Y. (2025). Cloak, honey, trap: Proactive defenses against LLM agents. In *34th USENIX Security Symposium (USENIX Security 25)* (pp. 8095-8114). USENIX Association. https://www.usenix.org/conference/usenixsecurity25/presentation/ayzenshteyn

Vero, M., Kaczmarczyck, F., Petrov, I., Shumailov, I., Hayes, J., Heinen, N., Fan, T., Invernizzi, L., & Vechev, M. (2026). *Honeyval: A comprehensive evaluation framework for LLM-powered HTTP honeypots* [Preprint]. arXiv. https://arxiv.org/abs/2605.29963

Wang, Y., Yu, J., & Sun, Y. (2026). *AgentTrap: Stateful feedback deception against autonomous penetration testing agents* [Preprint]. arXiv. https://arxiv.org/abs/2610.02869

Wehner, J., & Kraprayoon, J. (2026, October 15). *Honeypots for AI agent insider threats*. Institute for AI Policy and Strategy. https://www.iaps.ai/research/honeypots-for-ai-agent-insider-threats

## Key Principle
Context Bombs should not be treated as a standalone security boundary. Their strongest use is within a layered design combining deception, canary telemetry, external authorization, least privilege, sandboxing, and automated containment.
