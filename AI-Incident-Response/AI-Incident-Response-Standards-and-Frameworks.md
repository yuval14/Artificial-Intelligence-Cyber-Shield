# AI Incident Response Standards and Frameworks

**Author:** Yuval Sinay  
**Last updated:** 16 August 2026

## Scope

This page includes only standards, frameworks, playbooks, and regulatory reporting mechanisms that address incident response, incident handling, incident reporting, or structured incident information exchange specifically for artificial intelligence systems.

General cybersecurity incident-response standards and general AI security or risk-management frameworks are intentionally excluded unless the referenced document is directly focused on AI incidents.

## Direct AI Incident Response and Reporting Standards and Frameworks

| Organization | Standard / Framework | Type | Direct AI Incident Response Relevance | Status |
| --- | --- | --- | --- | --- |
| ETSI | **ETSI TS 104 158-1 V1.1.1 (2026-03), Securing Artificial Intelligence (SAI); AI Incident Reporting; Part 1: AI Common Incident Expression (AICIE) Global Framework** | Technical Specification | Defines a global framework for expressing AI incidents and a Common Incident Scoring System to support interoperable incident information exchange. | Published |
| ETSI | **ETSI TS 104 158-2 V1.1.1 (2026-03), Securing Artificial Intelligence (SAI); AI Incident Reporting; Part 2: AI Common Incident Expression (AICIE) Common Container** | Technical Specification | Defines the AICIE record container and profiles for structured AI incident records and exchange. | Published |
| ETSI | **ETSI TS 104 158-3, Securing Artificial Intelligence (SAI); AI Incident Reporting; Part 3: AI Common Incident Expression (AICIE) Security Container** | Technical Specification | Defines a record structure for sharing AI security information, including information related to adversarial threats. | In development / ETSI work programme |
| CISA | **JCDC AI Cybersecurity Collaboration Playbook** | Operational Playbook | Provides voluntary processes for sharing information about cybersecurity incidents and vulnerabilities associated with AI systems and for coordinating operational collaboration among government, industry, and international partners. | Published, January 2025 |
| OECD | **Towards a Common Reporting Framework for AI Incidents** | International Reporting Framework | Provides a common framework and global benchmark for reporting AI incidents across jurisdictions and sectors, using a structured set of reporting criteria. | Published, February 2025 |

## Regulatory AI Incident Reporting

The following is not an incident-response framework, but it directly creates an AI-specific serious-incident reporting obligation and should therefore be integrated into AI incident-response procedures where applicable.

| Authority | Requirement | Direct Relevance |
| --- | --- | --- |
| European Union | **Regulation (EU) 2024/1689, Article 73 - Reporting of serious incidents** | Requires providers of applicable high-risk AI systems to report serious incidents to relevant market-surveillance authorities according to the timelines and conditions defined by the AI Act. |

## Recommended Operational Use

These direct sources can be combined into a focused AI incident-response reporting layer:

1. **ETSI AICIE Part 1** for the common AI incident expression and scoring framework.
2. **ETSI AICIE Part 2** for the structured incident record container.
3. **ETSI AICIE Part 3** for security and adversarial-threat information sharing as the specification matures.
4. **CISA JCDC AI Cybersecurity Collaboration Playbook** for operational cybersecurity information sharing and multi-party coordination.
5. **OECD Common Reporting Framework for AI Incidents** for cross-sector and cross-jurisdiction incident reporting consistency.
6. **EU AI Act Article 73** for regulatory reporting workflows when the affected system falls within the applicable scope.

## Excluded from This Page

The following important resources are not included because they are not dedicated AI incident-response or AI incident-reporting frameworks:

- NIST SP 800-61 Rev. 3
- NIST Cybersecurity Framework 2.0
- NIST AI Risk Management Framework
- NIST AI 600-1 Generative AI Profile
- ISO/IEC 27035 series
- ISO/IEC 42001
- ISO/IEC 23894
- MITRE ATLAS
- OWASP Top 10 for LLM Applications
- OWASP Agentic AI guidance
- Google Secure AI Framework

These resources may support preparation, detection, investigation, containment, recovery, governance, or threat mapping, but they are broader than the strict scope of this page.

## References

Cybersecurity and Infrastructure Security Agency. (2025, January 14). *JCDC AI cybersecurity collaboration playbook*. U.S. Department of Homeland Security. https://www.cisa.gov/resources-tools/resources/ai-cybersecurity-collaboration-playbook

European Parliament & Council of the European Union. (2024). *Regulation (EU) 2024/1689 laying down harmonised rules on artificial intelligence (Artificial Intelligence Act)*, Article 73. *Official Journal of the European Union*. https://eur-lex.europa.eu/eli/reg/2024/1689/oj

European Telecommunications Standards Institute. (2026a). *ETSI TS 104 158-1 V1.1.1: Securing Artificial Intelligence (SAI); AI Incident Reporting; Part 1: AI Common Incident Expression (AICIE) Global Framework*. ETSI.

European Telecommunications Standards Institute. (2026b). *ETSI TS 104 158-2 V1.1.1: Securing Artificial Intelligence (SAI); AI Incident Reporting; Part 2: AI Common Incident Expression (AICIE) Common Container*. ETSI.

European Telecommunications Standards Institute. (2026). *ETSI TS 104 158-3: Securing Artificial Intelligence (SAI); AI Incident Reporting; Part 3: AI Common Incident Expression (AICIE) Security Container* [Work item]. ETSI.

Organisation for Economic Co-operation and Development. (2025). *Towards a common reporting framework for AI incidents*. OECD.AI. https://oecd.ai/en/ai-publications/towards-a-common-reporting-framework-for-ai-incidents
