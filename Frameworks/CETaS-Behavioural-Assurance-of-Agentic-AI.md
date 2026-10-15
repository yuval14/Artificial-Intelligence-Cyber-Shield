# CETaS Behavioural Assurance of Agentic AI

Last reviewed: 2026-10-16.

## Source and status

Hennessy and Ashurst's September 23, 2026 [CETaS report](https://cetas.turing.ac.uk/publications/behavioural-assurance-agentic-ai-sensitive-and-high-stakes-organisations) presents a sociotechnical model for sensitive deployments. It relates behavior to access, delegated authority, and human trust. CETaS describes an institutional peer-review process; this does not establish journal publication or validated control effectiveness.

## Source model

| Deployment variable | Meaning |
| --- | --- |
| Access | Resources and information the agent can reach |
| Authority | Decisions and actions it may undertake |
| Trust | Human reliance on its contributions |

The report distinguishes goal displacement, violations caused by unavailable policy context, misreporting, resistance to correction, conversational errors, correlated apparent corroboration, multi-agent cascades, and human-agent failures. Its assurance principles address organizational roles, deployment context, behavior, human interaction, least privilege, continuing review, and interdisciplinary expertise.

## Repository implementation recommendations

The following checklist is an adaptation for AI Cyber Shield, not a validated CETaS control catalog or official crosswalk.

| Review area | Suggested exercise | Evidence to retain |
| --- | --- | --- |
| Delegation | Give the test agent an ambiguous request with a prohibited synthetic outcome | Task scope, permission decision, attempted and completed actions |
| Conflicting objectives | Introduce a task-success incentive that conflicts with a documented constraint | Constraint visibility, decisions, independent outcome |
| Reporting | Compare the completion report with externally captured execution events | Original events, agent account, discrepancies and corrections |
| Apparent corroboration | Give reviewers outputs sharing one underlying source or dependency | Source lineage and the reviewer's independence assessment |
| Intervention | Revoke a test permission during a long task | Revocation time, destination enforcement, attempted retries |
| Human oversight | Ask reviewers to adjudicate seeded cases under realistic workload | Decision accuracy, review time, escalation and response |
| Deployment change | Change tools, persistent memory, or delegated identity | Versioned configuration, regression results, residual-risk decision |

Set acceptance criteria before running exercises. Measure benign task completion alongside prohibited outcomes, missed detections, false positives, and intervention delay. Compare like-for-like configurations and retain trial counts and uncertainty.

Assign an owner to each access boundary and intervention mechanism. Distinguish an observed action from an interpretation of motivation. Avoid diagnosing intent solely from generated explanations. Reassess after changes to the workflow or the people supervising it.

## Relationship to other repository material

- [AI Agent Threat Matrix](../AI-Agent-Security/AI-Agent-Threat-Matrix.md): scenario and control inventory.
- [Agent Monitoring and Control Evaluation](../AI-Agent-Security/Agent-Monitoring-and-Control-Evaluation.md): metrics and evidence records.
- [Persuasion Undermining Control](FAR-AI-Persuasion-Undermining-Control.md): influence on human control decisions.
- [AI Governance and Assurance](AI-Governance-and-Assurance.md): ownership and independent assessment.

## Limitations

Use the model to structure inquiry. Local tests do not establish safety in other organizations, workloads, or configurations. Similar-looking behaviors may have different causes and need separate investigation.

## References

Hennessy, R., & Ashurst, C. (2026, September 23). *Behavioural assurance of agentic AI for sensitive and high-stakes organisations*. Centre for Emerging Technology and Security. https://doi.org/10.83162/Turing.110
