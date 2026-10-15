# FAR.AI Persuasion Undermining Control (PUC)

Last reviewed: 2026-10-16.

## Source and status

Levy, Yang, and Pelrine's September 17, 2026 [research summary](https://www.far.ai/blog/persuasion-undermining-control) describes AI communication that influences people toward decisions weakening development, containment, oversight, or governance. The framework separates scenarios and risk variables.

Its preliminary survey involved eight experts with substantially differing judgments. Those judgments are not experimentally measured persuasion success rates. Peer-review status was not independently verified.

## Source approach

| Element | Summary |
| --- | --- |
| Scenario construction | Combine a sensitive setting with a control process |
| Risk decomposition | Consider hazardous-decision frequency, conditional harm probability, and harm impact |
| Measurement | Separate propensity to persuade from susceptibility to persuasion |
| Evidence boundary | Expert elicitation informs uncertainty; behavioral experiments are still needed |

## Repository implementation recommendations

The following scenarios and controls are AI Cyber Shield adaptations, not official FAR.AI requirements or proven defenses.

| Protected decision | Controlled test | Suggested safeguard | Measurement |
| --- | --- | --- | --- |
| Permission expansion | An agent requests broader access with a plausible task rationale | Authorization checked independently against task scope | Unauthorized grants and legitimate approvals |
| Security review | An agent argues that a seeded finding should be dismissed | Independent verification of the technical claim | Correct dispositions and unsupported dismissals |
| Incident escalation | An agent minimizes a labeled incident | Predefined escalation triggers and a separate reporting path | Missed escalation and response delay |
| Containment change | An agent requests removal of a test restriction | A second authorized reviewer for material changes | Approved boundary violations |
| Safety investment | An agent recommends abandoning a protective activity | Document assumptions and compare independent evidence | Unsupported changes in risk acceptance |

Use consenting participants, synthetic assets, and bounded scenarios. Predeclare the correct decision where one exists. Separate changes in factual accuracy from changes in preferences; agreement with the agent is not automatically a failure.

Record what evidence the human could access, the agent's request, the approval path, the final decision, and its independently verified consequence. Compare ordinary assistance with adversarial conditions under similar workloads. Report sample size, uncertainty, benign utility, and false-positive burden.

Integrate the tests with access enforcement outside the conversation. Keep the person requesting a change separate from the authority deciding it where practical. Audit any exceptions and preserve the ability to revoke privileges.

## Relationship to other repository material

- [CETaS Behavioural Assurance](CETaS-Behavioural-Assurance-of-Agentic-AI.md): broader organizational behavior.
- [AI Governance and Assurance](AI-Governance-and-Assurance.md): accountability and evidence.
- [AI Agent Threat Matrix](../AI-Agent-Security/AI-Agent-Threat-Matrix.md): human-review evasion scenarios.
- [Agent Monitoring and Control Evaluation](../AI-Agent-Security/Agent-Monitoring-and-Control-Evaluation.md): review and containment metrics.

## Limitations

A persuasive statement can be correct and useful. Evaluate authorization and evidence quality rather than persuasive style alone. Success in a seeded exercise does not prove malicious intent, general effectiveness, or real-world prevalence.

## References

Levy, J., Yang, M., & Pelrine, K. (2026, September 17). *Persuasion undermining control: Can AI talk its way out of human control?* FAR.AI. https://www.far.ai/blog/persuasion-undermining-control
