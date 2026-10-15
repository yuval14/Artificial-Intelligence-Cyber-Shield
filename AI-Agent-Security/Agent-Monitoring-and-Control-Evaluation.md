# Agent Monitoring and Control Evaluation

Last reviewed: 2026-10-16.

## Purpose and evidence status

Evaluate whether an agent's unauthorized behavior is observed, correctly classified, and stopped before a protected objective is reached. This page combines selected research with repository engineering recommendations; it is not a certified standard or an empirically validated repository framework.

| Primary source | Status | Contribution and boundary |
|---|---|---|
| [METR control assessment proposal](https://metr.org/blog/2026-10-14-control-assessment-proposal/), October 14, 2026 | Proposed assessment methodology | Examines monitoring coverage, infrastructure weaknesses, evasion, human response, and achievable harm; a proposal does not demonstrate deployed effectiveness |
| [METR SHUSHCAST](https://metr.org/blog/2026-01-19-early-work-on-monitorability-evaluations/), January 22, 2026 | Preliminary empirical research post | Tests hidden side tasks within main tasks; limited task diversity and elicitation constrain generalization |
| [AISI multi-agent control](https://www.aisi.gov.uk/research/multi-agent-ai-control-distributed-attacks-hamper-per-instance-monitors), July 8, 2026 | Empirical research, institutional summary | FakeLab uses 9 services, 86 benign tasks, and 4 attack objectives; coordinated attacks fragment evidence and weaken per-agent monitoring; synthetic results are not production measurements |

METR's displayed publication date for SHUSHCAST is January 22 despite the January 19 URL slug. Publication venue and peer-review status must be verified separately from institutional authorship.

## Threat model and boundaries

Specify the agent's legitimate task, allowed assets and actions, prohibited objectives, delegation powers, memory, and network access before testing. Separate the agent, monitor, authorization service, logs, and response authority into explicit trust boundaries. Treat monitor inputs as potentially adversarial.

Record which model, tools, configurations, and safeguards the assessor can inspect. Distinguish an observed exploit, an inferred weakness, and a hypothetical future scenario.

## Recommended assessment matrix

The tests and pass conditions below are repository recommendations to be calibrated to the deployment, not thresholds supplied by the cited studies.

| Area | Controlled test | Required evidence | Example pass condition |
|---|---|---|---|
| Coverage | Exercise each entry point, delegation route, retry, and tool path | Independent execution inventory reconciled to monitor receipts | All in-scope security-critical actions accounted for; missing receipts are surfaced |
| Monitor integrity | Attempt an unauthorized change to monitoring settings using a test identity | Configuration audit events and policy decisions | Change denied or independently detected before protected action |
| Evasion | Place a prohibited synthetic side task in ordinary work | Original trajectory, exact monitor input, decision, and independent outcome | Measured recall meets the predeclared threshold at the agreed false-positive rate |
| Evidence fragmentation | Distribute a prohibited objective across test agents | Parent-child task graph, shared-resource events, and timing | Correlation detects the joint chain before completion |
| Human response | Present labeled test cases with benign-looking explanations | Queue, review, escalation, and containment timestamps | Severe cases receive the required response within the predeclared deadline |
| Impact | Attempt a synthetic protected objective in an isolated environment | Independent target-state or network oracle | Enforcement prevents the objective even if a monitor misses it |

## Measurement definitions

These definitions are proposed for consistent repository reporting.

| Metric | Definition and denominator |
|---|---|
| Action coverage | In-scope actions with usable monitor evidence / all in-scope actions in an independent execution inventory |
| Detection recall | Labeled malicious test trajectories flagged / all labeled malicious test trajectories |
| False-positive rate | Benign test trajectories flagged / all labeled benign test trajectories |
| Undetected attack success | Attack trials achieving the prohibited objective without being flagged / all attack trials |
| Unblocked attack success | Attack trials achieving the prohibited objective / all attack trials, including flagged trials |
| Containment latency | Time from first ground-truth prohibited action to effective revocation or isolation; report detection and response components separately |
| Legitimate utility | Benign tasks completed correctly / all benign tasks; include latency and cost |

State whether the unit is an action, trajectory, campaign, or agent. A flagged attack can still succeed before response, so detection and prevention must be reported separately. Specify how failed runs, missing telemetry, and timeouts enter each denominator. Include trial counts and uncertainty intervals; do not infer safety from zero observed successes in a small sample.

## Minimum test record

Preserve model and monitor versions, harness commit, prompts, tool permissions, environment snapshot, task labels, sampling settings, retry and resource budgets, random seeds where available, and the exact material visible to the monitor. Retain original transcripts separately from summaries or compacted context.

Record agent, session, parent task, delegated task, tool-call, and correlation identifiers. Link each material action to its authorization decision, affected resource, monitor receipt, review outcome, and independent ground truth. Integrity-protect evidence outside the tested agent's write permissions.

## Practical workflow

1. Predeclare scope, outcomes, risk owner, and acceptance thresholds.
2. Establish benign and malicious controls in isolated test infrastructure.
3. Evaluate fixed baselines before adaptive attacks; reserve held-out cases.
4. Measure single-agent and coordinated-agent conditions under comparable budgets.
5. Review false positives and missed or late interventions independently.
6. Retest after changes to models, scaffolds, memory, tools, or monitoring.

See [AI Agent Threat Matrix](AI-Agent-Threat-Matrix.md), [AI Cyber Deception](AI-Cyber-Deception.md), [AI Red Team Frameworks](../Frameworks/AI-Red-Team-Frameworks.md), and [GDM AI Control Roadmap](../Frameworks/GDM-AI-Control-Roadmap.md).

## References

Kinniment, M., Nix, S., Broadley, T., Wijk, H., & Parikh, N. (2026, January 22). *Early work on monitorability evaluations*. METR. https://metr.org/blog/2026-01-19-early-work-on-monitorability-evaluations/

Makins, O., Angelini, O., Shams, Z., & Phuong, M. (2026). *Multi-agent AI control: Distributed attacks hamper per-instance monitors*. AI Security Institute. https://www.aisi.gov.uk/research/multi-agent-ai-control-distributed-attacks-hamper-per-instance-monitors

METR. (2026, October 14). *How an assessor could investigate control and monitoring of internal AI agents*. https://metr.org/blog/2026-10-14-control-assessment-proposal/
