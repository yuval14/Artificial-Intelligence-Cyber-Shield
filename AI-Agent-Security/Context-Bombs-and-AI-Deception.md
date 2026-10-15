# Context Bombs and AI Deception

Last reviewed: 2026-10-16.

## Scope and terminology

This page distinguishes attacks on legitimate agents from deception deployed against hostile agents. It is a focused overview with links to the repository's detailed controls and research summaries.

"Context bomb" is used here as a descriptive label for adversarial instructions or signals placed in material an agent may read. It is not a standardized threat category or a guarantee of disruption.

| Direction | Mechanism | Security question |
|---|---|---|
| Attack against a legitimate agent | Instructions embedded in documents, websites, tool output, or retrieved content | Does untrusted data redirect the agent or gain authority? |
| Persistent compromise | Poisoned memory or retrieval content influences later sessions | Can the influence survive a task or session boundary? |
| Defensive deception against a hostile agent | Decoy resources, instrumented tools, misleading paths, or controlled context | Does the interaction expose, delay, or divert unauthorized activity? |
| Assessment of an internal agent | A controlled opportunity for a prohibited action | Does the agent cross an explicit authorization boundary? |

## Defensive architecture

Treat retrieved material and tool output as data with provenance. Enforce access and consequential actions outside the model. Isolate memory writes, preserve original artifacts, and correlate tool and identity events across delegated tasks. A refusal, a canary hit, or a suspicious phrase is an observation requiring context, not a determination of intent.

See [Prompt Injection Defenses](Prompt-Injection-Defenses.md), [AI Agent Threat Matrix](AI-Agent-Threat-Matrix.md), and [AI Agent Security](../Frameworks/AI-Agent-Security.md).

## Research and evidence

- **External hostile agents:** CHeaT is a peer-reviewed USENIX Security 2025 paper from Ben-Gurion University of the Negev (Ayzenshteyn et al., 2025).
- **Adaptive deception:** AgentTrap is an arXiv preprint, initially submitted October 2, 2026 (Wang et al., 2026). Its experimental results do not establish general protection.
- **Evaluation methodology:** Honeyval is an arXiv preprint, initially submitted May 28, 2026 (Vero et al., 2026).

The [AI Cyber Deception](AI-Cyber-Deception.md) page contains the comparative evidence table, limitations, and complete references. Preprint status does not establish peer review. Names without a verified primary source are not included as evidence.

## Evaluation and operational use

Use a matched baseline without deception, benign-agent controls, repeated trials, and an independent success oracle. Distinguish discovery of a decoy from attempted use and actual execution. Report model and harness versions, permissions, retry budgets, and changes in legitimate task completion.

See [Agent Monitoring and Control Evaluation](Agent-Monitoring-and-Control-Evaluation.md) for test records and metrics. Framework mappings in this repository are analytical unless an official mapping is explicitly identified. No complete technique-level MITRE or OWASP mapping is claimed on this page.
