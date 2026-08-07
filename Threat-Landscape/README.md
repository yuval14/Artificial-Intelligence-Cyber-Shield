# AI Threat Landscape

This directory contains defender-oriented research and executive guidance on emerging threats associated with artificial intelligence, AI agents, model services, local inference, AI-enabled cyber operations, persistent always-on agents, and highly autonomous cyber-capable systems.

## Pages

- [Covert Use of AI in Offensive Cyber Operations](./Covert-Use-of-AI-in-Offensive-Cyber-Operations.md)
- [Highly Autonomous Cyber-Capable Agents (HACCAs)](./Highly-Autonomous-Cyber-Capable-Agents.md)
- [OpenAI/Hugging Face Autonomous-Agent Incident, July 2026](./OpenAI-Hugging-Face-Autonomous-Agent-Incident.md)
- [Kimi Claw and the Security Risks of Always-On AI Agents](./Kimi-Claw-Always-On-Agent-Risk.md)
- [Frontier AI Cyber-Capability Acceleration](./Frontier-Cyber-Capability-Acceleration.md)

## 2026 IAPS Research Themes Added

The threat-landscape coverage now incorporates five related shifts identified in 2026 research by the Institute for AI Policy and Strategy (IAPS):

1. **Autonomous cyber capability** - HACCAs represent a potential class of AI systems able to plan, execute, adapt, and sustain sophisticated cyber campaigns with little meaningful human direction.
2. **Detection-in-depth** - defenders may need agent identity, agent-aware deception, AI-assisted alert triage, standardized agentic threat reporting, and provider/cloud information sharing in addition to conventional telemetry.
3. **Containment and loss of control** - the July 2026 OpenAI/Hugging Face incident illustrates the security significance of technical boundaries around cyber-capable model evaluation, including egress control, target allowlists, workload identity, independent stop mechanisms, and complete auditability.
4. **Persistent always-on agents** - cross-application access to files, browser sessions, messages, skills, and external services can concentrate identity, privacy, supply-chain, and national-security risk in one persistent agent platform.
5. **Compressed cyber timelines** - faster vulnerability discovery, exploit generation, and automated attack execution increase pressure on detection, vulnerability management, remediation, and critical-infrastructure compensating controls.

## Related Repositories

- [Cybersecurity Detection Engineering](https://github.com/yuval14/Cybersecurity-Detection-Engineering)
- [AIDAF - Adversarial AI Detection and Assessment Framework](https://github.com/yuval14/Cybersecurity-Detection-Engineering/tree/main/AIDAF-Adversarial-AI-Detection-and-Assessment-Framework)
- [AI Security Tooling](https://github.com/yuval14/AI-Security-Tooling)

## Intended Audience

- CISOs and security executives
- SOC and threat-intelligence leaders
- Security architects and engineers
- AI governance and assurance teams
- Researchers and national-security practitioners

## Analytic Principle

AI involvement should be assessed through evidence and workflow correlation. Speed, sophistication, adaptation, generated text, or generated code do not independently prove that an adversary used AI.

Autonomous-agent capability should also be separated from incident-level evidence. A system may demonstrate autonomous behavior in a constrained task without meeting the broader HACCA concept, and defenders should avoid assuming that every machine-speed or adaptive intrusion is agentic.

Product- or jurisdiction-specific case studies should be used to identify general control requirements while preserving source quality, legal context, and alternative explanations.

## Key References

Bearman, T. (2026, February 25). *Kimi Claw: Risks from Chinese-hosted 'always on' AI agents*. Institute for AI Policy and Strategy. https://www.iaps.ai/research/kimi-claw-risks

Bearman, T., Covino, C., Mittelsteadt, M., & O'Brien, J. (2026, July 27). *The OpenAI/Hugging Face incident: Challenges in controlling and containing cyber-capable AI systems*. Institute for AI Policy and Strategy. https://www.iaps.ai/research/the-openaihugging-face-incident-challenges-in-controlling-and-containing-cyber-capable-ai-systems

Covino, C. (2026, April 16). *Mythos and the evolving cyber landscape: Implications and policy priorities*. Institute for AI Policy and Strategy. https://www.iaps.ai/research/mythos-and-the-evolving-cyber-landscape-implications-and-policy-priorities-Bu4xs

Kraprayoon, J., Ee, S., Rosen, B., Matthew, Y., Singh, A., Covino, C., & Gershovich, A. B. (2026, March 11). *Highly autonomous cyber-capable agents: Anticipating capabilities, tactics, and strategic implications*. Institute for AI Policy and Strategy. https://www.iaps.ai/research/highly-autonomous-cyber-capable-agents

Mittelsteadt, M., Kraprayoon, J., Staes-Polet, R., Galeev, O., Wehner, J., Covino, C., & Ee, S. (2026, May 19). *Detecting offensive cyber agents: A detection-in-depth approach*. Institute for AI Policy and Strategy. https://www.iaps.ai/research/detecting-offensive-cyber-agents
