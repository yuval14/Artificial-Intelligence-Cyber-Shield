# OWASP Agentic AI Security Incidents & Exploits

## Resource profile

| Field | Description |
| --- | --- |
| Resource | OWASP Agentic AI Security Incidents & Exploits |
| Type | Interactive incident and exploit tracker |
| URL | https://owasp-agentic-ai-security-incidents.lovable.app/ |
| Primary audience | CISOs, security leaders, AI security teams, SOC teams, threat hunters, red teams, architects, researchers, and policymakers |
| Primary focus | Publicly reported security incidents, exploits, abuse cases, and failure patterns involving agentic AI systems |
| Date accessed | August 5, 2026 |

## Overview

The **OWASP Agentic AI Security Incidents & Exploits** tracker is an external interactive resource intended to organize and present security incidents and exploit patterns associated with agentic AI. It can help security practitioners move from abstract risk taxonomies to incident-led analysis based on publicly reported cases, demonstrations, vulnerabilities, and operational failures.

The resource is particularly relevant to systems in which AI agents can plan across multiple steps, use tools, call APIs, access data, maintain memory, delegate tasks, execute code, or perform actions in external environments. These capabilities create security risks that extend beyond conventional prompt-level weaknesses and may involve identity abuse, excessive permissions, unsafe tool use, compromised integrations, persistent memory manipulation, uncontrolled execution, or cascading actions across connected systems.

## Security value

The tracker can support the following activities:

1. **Incident-led threat modeling** - Convert observed incidents into attack paths, abuse cases, trust-boundary failures, and control requirements.
2. **Red-team scenario development** - Build realistic exercises involving prompt injection, tool misuse, privilege abuse, memory poisoning, supply-chain compromise, or unexpected code execution.
3. **Detection engineering and threat hunting** - Identify required telemetry for prompts, retrieved content, agent decisions, tool calls, identities, permissions, memory changes, network activity, and external actions.
4. **Control validation** - Assess whether approval gates, least privilege, sandboxing, policy enforcement, egress controls, transaction limits, and kill switches would prevent or contain similar incidents.
5. **Incident response preparation** - Develop playbooks for disabling agents, revoking credentials, isolating tools, preserving evidence, rolling back memory or configuration, and investigating downstream impact.
6. **Executive risk communication** - Provide concrete examples of how agentic autonomy, tool access, and weak governance can create operational, legal, privacy, safety, and national-security consequences.
7. **Research and trend analysis** - Track recurring failure modes, affected technologies, attack vectors, impact patterns, and gaps in existing security frameworks.

## Recommended analytical workflow

For each relevant incident, security teams should:

1. Record the original disclosure, occurrence date, affected system, and reporting organization.
2. Distinguish confirmed real-world incidents from controlled demonstrations, proof-of-concept research, suspected events, and unverified claims.
3. Identify the initiating instruction, malicious input, vulnerable component, compromised identity, or unsafe environmental condition.
4. Reconstruct the sequence from user or attacker input through model reasoning, tool use, external action, and impact.
5. Map the incident to the OWASP Top 10 for Agentic Applications, MITRE ATLAS, NIST AI RMF, and internal control frameworks.
6. Document prevention, detection, containment, recovery, and assurance requirements.
7. Convert recurring patterns into red-team tests, threat-hunting hypotheses, SIEM analytics, architectural controls, and governance requirements.
8. Revalidate the incident record periodically because tracker content and external reporting may change.

## Suggested telemetry for incident reconstruction

| Layer | Recommended evidence |
| --- | --- |
| Request and identity | Initiating user, delegated identity, authentication context, session, role, and authorization decision |
| Prompt and context | System instructions, user prompt, retrieved content, attachments, web content, and context provenance |
| Agent reasoning and state | Task plan, state transitions, confidence, retry history, delegation, and stop-condition decisions |
| Tool use | Tool name, parameters, response, execution environment, approval status, and error handling |
| Memory | Reads, writes, source labels, persistence scope, modification history, and rollback records |
| Network and external actions | Destinations, DNS, API calls, browser actions, code execution, transactions, messages, and file operations |
| Policy enforcement | Allow or deny decision, policy version, exception, approval, and compensating control |
| Impact and response | Data accessed, systems changed, credentials exposed, containment steps, revocations, recovery, and forensic preservation |

## Source-quality and validation considerations

The resource is hosted on a third-party `lovable.app` domain rather than an official `owasp.org` or `genai.owasp.org` domain. Its title and subject matter indicate an OWASP-related agentic AI security focus, but users should independently verify project ownership, governance, update practices, and individual incident claims.

Material incidents should be corroborated against primary or authoritative sources, such as:

1. Official vulnerability advisories and CVE records.
2. Vendor incident reports or security bulletins.
3. Government or national cybersecurity authority publications.
4. Peer-reviewed or clearly documented security research.
5. Official OWASP project publications.
6. Reputable reporting that cites identifiable evidence and affected parties.

The tracker should therefore be used as a discovery, analysis, and awareness resource rather than as the sole evidentiary basis for attribution, regulatory reporting, legal conclusions, or production security decisions.

## Related repository areas

- [AI Agent Security](../Frameworks/AI-Agent-Security.md)
- [AI Security Frameworks](../Frameworks/AI-Security-Frameworks.md)
- [AI Red Team Frameworks](../Frameworks/AI-Red-Team-Frameworks.md)
- [AI Threat Modeling Frameworks](../Frameworks/AI-Threat-Modeling-Frameworks.md)
- [System Hardening Against AI and Agentic AI Threats](../System-Hardening/System-Hardening-Against-AI-Threats.md)

## APA 7 reference

OWASP Agentic Security Initiative. (n.d.). *Agentic AI security incidents & exploits* [Interactive incident tracker]. Lovable. Retrieved August 5, 2026, from https://owasp-agentic-ai-security-incidents.lovable.app/

## Related OWASP reference

Open Worldwide Application Security Project. (2025, December 9). *OWASP GenAI Security Project releases Top 10 risks and mitigations for agentic AI security*. https://genai.owasp.org/2025/12/09/owasp-genai-security-project-releases-top-10-risks-and-mitigations-for-agentic-ai-security/
