# AI Incident Repositories

This section catalogs public repositories, trackers, and case-study collections concerning AI security, AI safety, and agentic AI incidents. These resources support incident-led threat modeling, security architecture, red teaming, detection engineering, threat hunting, assurance, and executive risk communication.

## Repository index

| # | Resource | Primary focus | Security use | Validation note |
| --- | --- | --- | --- | --- |
| 1 | [OWASP Agentic AI Security Incidents & Exploits](OWASP-Agentic-AI-Security-Incidents.md) | Security incidents, exploits, and failure patterns involving agentic AI systems | Agent threat modeling, control validation, red-team scenarios, detection and hunting use cases, and CISO briefings | The tracker is hosted on a third-party `lovable.app` domain. Validate material incidents against primary disclosures, advisories, CVE records, vendor reports, or official OWASP publications before operational use. |
| 2 | [AI Incident Database (AIID)](https://incidentdatabase.ai/) | Reports of real-world AI incidents and harms | Discover incidents and compare failure patterns across deployments | Corroborate reported facts with primary sources. |
| 3 | [MIT AI Incident Tracker](https://airisk.mit.edu/ai-incident-tracker) | Classifies AIID reports by risk, cause, harm type, and severity | Filter and compare reported incidents by risk and severity | Review the source reports and validate classifications before relying on them. |

## Recommended assessment fields

When incorporating an incident into an organizational knowledge base, capture at least:

1. Incident or campaign name.
2. Disclosure and occurrence dates.
3. Affected agent, model, framework, tool, or integration.
4. Initial access or triggering condition.
5. Agentic failure mode or attacker technique.
6. Tools, identities, permissions, memory, and data involved.
7. Technical and business impact.
8. Detection opportunities and required telemetry.
9. Preventive, detective, and responsive controls.
10. Source provenance, corroboration status, and confidence level.
11. Mapping to the OWASP Top 10 for Agentic Applications, MITRE ATLAS, NIST AI RMF, and applicable organizational controls.

## Use and verification principle

Incident trackers are discovery and analysis resources. They should not be treated as authoritative evidence without corroboration. Security teams should preserve the original source, distinguish confirmed incidents from demonstrations or research findings, and document uncertainty when facts remain incomplete or disputed.
