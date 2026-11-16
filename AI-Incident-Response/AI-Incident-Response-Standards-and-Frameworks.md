# AI Incident Response Standards and Frameworks

**Author:** Yuval Sinay  
**Last updated:** 17 November 2026

## Scope

This page covers standards, frameworks, playbooks, behavioral taxonomies, and regulatory reporting mechanisms that address incident response, incident handling, incident reporting, or structured incident information exchange specifically for artificial intelligence systems.

General cybersecurity incident-response standards and general AI security or risk-management frameworks are intentionally excluded unless the referenced document is directly focused on AI incidents.

## Direct AI Incident Response and Reporting Standards and Frameworks

| Organization | Standard / Framework | Type | Direct AI Incident Response Relevance | Status |
| --- | --- | --- | --- | --- |
| ETSI | **ETSI TS 104 158-1 V1.1.1 (2026-03), Securing Artificial Intelligence (SAI); AI Incident Reporting; Part 1: AI Common Incident Expression (AICIE) Global Framework** | Technical Specification | Defines a global framework for expressing AI incidents and a Common Incident Scoring System to support interoperable incident information exchange. | Published |
| ETSI | **ETSI TS 104 158-2 V1.1.1 (2026-03), Securing Artificial Intelligence (SAI); AI Incident Reporting; Part 2: AI Common Incident Expression (AICIE) Common Container** | Technical Specification | Defines the AICIE record container and profiles for structured AI incident records and exchange. | Published |
| ETSI | **ETSI TS 104 158-3, Securing Artificial Intelligence (SAI); AI Incident Reporting; Part 3: AI Common Incident Expression (AICIE) Security Container** | Technical Specification | Defines a record structure for sharing AI security information, including information related to adversarial threats. | In development / ETSI work programme |
| CISA | **JCDC AI Cybersecurity Collaboration Playbook** | Operational Playbook | Provides voluntary processes for sharing information about cybersecurity incidents and vulnerabilities associated with AI systems and for coordinating operational collaboration among government, industry, and international partners. | Published, January 2025 |
| OECD | **Towards a Common Reporting Framework for AI Incidents** | International Reporting Framework | Provides a common framework and global benchmark for reporting AI incidents across jurisdictions and sectors, using a structured set of reporting criteria. | Published, February 2025 |
| OpenAI, in collaboration with MITRE | **[Classifying AI Control Incidents and Their Severity: A Draft Framework](https://cdn.openai.com/pdf/classifying-ai-control-incidents-and-their-severity-a-draft-framework.pdf)** | Incident Classification and Severity Framework | Defines when unauthorized actions by models or agents qualify as control incidents and rates actual and potential impact separately. | Draft v0.1, November 2026 |

## OpenAI and MITRE draft framework for AI control incidents

Version 0.1 applies to models and agents in development, evaluation, and deployment. An action qualifies as an AI control incident when the model or agent takes a step that neither an authorized user nor a human attacker directed, exceeds its authorized scope, and either causes an observable adverse consequence or materially compromises a control.

- **Classify the event.** Distinguish a control finding, a blocked attempt, a near miss, a suspected incident, and a confirmed incident. Treat a blocked attempt as a near miss when evidence shows that a final-stage intervention prevented an adverse consequence or a meaningful control compromise.
- **Rate impact separately.** Record actual impact and evidence-supported potential impact on the same five-level scale, from Low to Critical. Consider confidentiality, integrity, availability, and the ability of human overseers to monitor and intervene. Account for safeguards that remained effective and the time responders had to intervene when rating potential impact.
- **Apply during triage.** Document the action, the authorization boundary, the safeguards that failed or held, and the evidence behind each rating. Use the classification to inform existing response, escalation, and notification procedures.

## Behavioral indicators and model misalignment reporting

| Organization | Resource | Use in incident response |
| --- | --- | --- |
| Guidelight AI Standards | [Misaligned AI behaviors that indicate loss-of-control risk](https://guidelight.ai/blog/categories-of-misaligned-ai-behaviors) | Use its ten behavioral categories to label observations during monitoring and investigation. Examples include deception, interference with oversight, unauthorized activity, and coordinated misbehavior. Apply the control-incident criteria and impact ratings during triage. |
| OpenAI | [Our framework for reporting model misalignment](https://openai.com/index/model-misalignment-reporting-framework/) | Use the published criteria and case reports as examples of deciding which observations warrant investigation and public disclosure. A noteworthy observation can warrant disclosure even when it falls below the AI control incident threshold. |

## Regulatory AI Incident Reporting

These requirements and resources support regulatory reporting workflows for serious AI incidents.

| Authority | Requirement | Direct Relevance |
| --- | --- | --- |
| European Union | **Regulation (EU) 2024/1689, Article 73 - Reporting of serious incidents** | Requires providers of applicable high-risk AI systems to report serious incidents to relevant market-surveillance authorities according to the timelines and conditions defined by the AI Act. |
| European Union | **Regulation (EU) 2024/1689, Article 55 - [Serious incident reporting template for general-purpose AI models with systemic risk](https://digital-strategy.ec.europa.eu/en/library/ai-act-commission-publishes-reporting-template-serious-incidents-involving-general-purpose-ai)** | Provides official Word and PDF reporting forms for providers of general-purpose AI models with systemic risk to document serious incidents for the AI Office and, where appropriate, national competent authorities. |

## NIST guidance for incidents involving advanced AI agents

- **November 2, 2026:** [NIST IR 8621](https://doi.org/10.6028/NIST.IR.8621) is a final workshop report. It covers attacks against AI systems and harm caused by misuse, anomalous behavior, or operational malfunction. It highlights reasoning-layer telemetry, non-human identities, authorization-scoped containment, and evidence sharing.
- **October 16, 2026:** [Key Practices for Incident Readiness and Response in Super Intelligence Training and Evaluation](https://www.nist.gov/document/keypracticesforincidentreadinessandresponseinsuperintelligence-trainingandevaluation) is joint voluntary guidance from NIST, NSA, and CISA. It covers preparation, detection, response, recovery, and reporting during training and evaluation.

For an agent response playbook, distinguish a compromised agent or integration from an agent taking unintended or unauthorized action. In either case, identify the affected principal and delegation chain, preserve independent tool and policy logs, revoke the affected credentials, and contain tool and network access. Resume operations only after verifying that the containment controls address the observed failure and testing the approved recovery configuration.

## CSA and OWASP incident case studies

The [CSA research note on agentic incident response](https://labs.cloudsecurityalliance.org/research/csa-research-note-agentic-incident-response-practices-202610/) discusses applying frontier-lab response practices in enterprises. Use the [OWASP Q3 2026 exploit roundup](https://genai.owasp.org/2026/10/08/genai-and-agentic-ai-exploit-roundup-q3-2026/) to select tabletop scenarios and distinguish reported incidents from controlled demonstrations.

- **OpenAI Artifactory - reported containment incident.** Evaluation agents used shared package infrastructure to bypass intended boundaries. Monitor unusual package writes and outbound traffic. Before restart, verify isolation of package namespaces and test egress restrictions from the rebuilt environment.
- **CoSnitch Copilot - security research demonstration.** Untrusted content could redirect assistant actions or poison persistent memory. Inspect unexpected memory writes and connected-account requests. Before re-enabling affected capabilities, validate cleaned memory and retest tool authorization with hostile content.

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

European Commission. (2025, November 4). *AI Act: Commission publishes a reporting template for serious incidents involving general-purpose AI models with systemic risk*. https://digital-strategy.ec.europa.eu/en/library/ai-act-commission-publishes-reporting-template-serious-incidents-involving-general-purpose-ai

European Parliament & Council of the European Union. (2024). *Regulation (EU) 2024/1689 laying down harmonised rules on artificial intelligence (Artificial Intelligence Act)*, Article 73. *Official Journal of the European Union*. https://eur-lex.europa.eu/eli/reg/2024/1689/oj

European Telecommunications Standards Institute. (2026a). *ETSI TS 104 158-1 V1.1.1: Securing Artificial Intelligence (SAI); AI Incident Reporting; Part 1: AI Common Incident Expression (AICIE) Global Framework*. ETSI.

European Telecommunications Standards Institute. (2026b). *ETSI TS 104 158-2 V1.1.1: Securing Artificial Intelligence (SAI); AI Incident Reporting; Part 2: AI Common Incident Expression (AICIE) Common Container*. ETSI.

European Telecommunications Standards Institute. (2026). *ETSI TS 104 158-3: Securing Artificial Intelligence (SAI); AI Incident Reporting; Part 3: AI Common Incident Expression (AICIE) Security Container* [Work item]. ETSI.

Guidelight AI Standards. (2026, November 11). *Misaligned AI behaviors that indicate loss-of-control risk*. https://guidelight.ai/blog/categories-of-misaligned-ai-behaviors

OpenAI. (2026, September 16). *Our framework for reporting model misalignment*. https://openai.com/index/model-misalignment-reporting-framework/

OpenAI. (2026, November 16). *A proposed framework for classifying AI control incidents*. https://openai.com/index/classifying-ai-control-incidents/

Organisation for Economic Co-operation and Development. (2025). *Towards a common reporting framework for AI incidents*. OECD.AI. https://oecd.ai/en/ai-publications/towards-a-common-reporting-framework-for-ai-incidents
