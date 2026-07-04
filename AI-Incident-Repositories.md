# AI Incident Repositories

This page lists public repositories, monitors, databases, and knowledge bases that can support AI incident intelligence, AI safety analysis, AI security research, policy learning, and organizational lessons learned.

AI incident repositories are useful because they create a shared memory of real-world failures, misuse, vulnerabilities, accidents, near misses, and harmful outcomes involving AI systems.

| # | Organization | Repository / Monitor | Goal / Function | Coverage | Release / Launch Date | Public | API / Data Access | Link |
|---:|---|---|---|---|---|:---:|---|---|
| 1 | OECD | OECD AI Incidents Monitor | Tracks AI incidents and hazards to support policy analysis, risk monitoring, and evidence-based AI governance. | AI harms, misuse, safety, rights, discrimination, physical, economic, reputational, and societal impacts | 2024 | Yes | Web access; data access varies | [OECD AI Incidents Monitor](https://oecd.ai/en/incidents) |
| 2 | AI Incident Database | AI Incident Database (AIID) | Public database of real-world AI incidents intended to help researchers and practitioners prevent repeated AI failures. | AI failures, unsafe behavior, societal harms, misuse, bias, accidents, and near misses | 2020 | Yes | Public database and exports | [AI Incident Database](https://incidentdatabase.ai/) |
| 3 | MITRE | MITRE ATLAS Case Studies | Case-study repository and knowledge base for adversarial threats to AI-enabled systems. | AI security incidents, adversarial ML, model compromise, data poisoning, evasion, and related attack patterns | 2020 | Yes | Web access | [MITRE ATLAS Case Studies](https://atlas.mitre.org/studies/) |
| 4 | MITRE | MITRE ATLAS | Knowledge base of tactics, techniques, mitigations, and case studies for adversarial threats to AI systems. | AI attack techniques, adversarial ML, security controls, and threat modeling | 2020 | Yes | Web access and structured content | [MITRE ATLAS](https://atlas.mitre.org/) |
| 5 | AVID | AI Vulnerability Database (AVID) | Public knowledge base for AI vulnerabilities, risks, and evaluation reports. | AI vulnerabilities, model risks, security findings, and responsible disclosure records | 2023 | Yes | Public database; GitHub ecosystem | [AVID](https://avidml.org/) |
| 6 | Partnership on AI | AI Incident Briefs and Responsible Practices | Collects lessons and analysis around AI harms, responsible deployment, and governance practices. | AI harms, synthetic media, responsible deployment, institutional learning | 2020s | Yes | Web publications | [Partnership on AI](https://partnershiponai.org/) |
| 7 | MLCommons | AILuminate | Benchmark and reporting ecosystem for AI risk and reliability across safety categories. | Model behavior, hazardous content, safety evaluations, benchmark results | 2024 / 2025 | Yes | Public benchmark resources | [MLCommons AILuminate](https://mlcommons.org/ailuminate/) |
| 8 | Stanford CRFM | HELM | Holistic language-model evaluation repository covering accuracy, robustness, fairness, toxicity, efficiency, and transparency. | Model evaluation results and behavioral risk indicators | 2022 | Yes | Public results and code | [HELM](https://crfm.stanford.edu/helm/) |
| 9 | UK AI Security Institute | AI Security Institute evaluations and research | Public evaluation and research outputs related to advanced AI safety and security. | Frontier AI evaluation, model capabilities, safety, cyber, autonomy, safeguards | 2024 | Yes | Publications and selected tools | [UK AISI](https://www.aisi.gov.uk/) |
| 10 | CISA | AI Security Resources | Government AI security resources for critical infrastructure, secure AI adoption, and AI system protection. | AI cybersecurity, critical infrastructure risk, secure AI practices | 2023 | Yes | Web publications | [CISA AI](https://www.cisa.gov/ai) |
| 11 | ENISA | AI Cybersecurity Publications | European cybersecurity agency publications addressing AI cybersecurity challenges, machine-learning security, and standardization. | AI cybersecurity, ML security, standards, governance, and risk analysis | 2020 onward | Yes | Web publications | [ENISA AI Publications](https://www.enisa.europa.eu/topics/artificial-intelligence) |
| 12 | NIST | Trustworthy and Responsible AI Resource Center | U.S. government resource center for AI risk management, generative AI risk, evaluations, and trustworthy AI practices. | AI risk management, trustworthy AI, GenAI risks, measurement, and evaluation | 2023 | Yes | Web publications and tools | [NIST Trustworthy AI](https://airc.nist.gov/) |
| 13 | OpenAI | System Cards and Safety Evaluations | Public safety documentation for selected models, including risks, evaluations, mitigations, and limitations. | Frontier-model behavior, safety testing, cyber, autonomy, persuasion, and biological-risk evaluations | 2020s | Yes | Public reports | [OpenAI Safety](https://openai.com/safety/) |
| 14 | Anthropic | System Cards and Responsible Scaling Policy reports | Public safety documentation and policy reports for frontier AI systems. | Model safety, evaluations, safeguards, capability thresholds, and deployment risk | 2020s | Yes | Public reports | [Anthropic Safety](https://www.anthropic.com/safety) |
| 15 | Google DeepMind | Safety and Frontier Safety Framework publications | Public safety research and governance outputs for advanced AI systems. | Frontier AI risks, model evaluations, dangerous capabilities, safeguards, and risk governance | 2020s | Yes | Public reports | [Google DeepMind Safety](https://deepmind.google/responsibility-safety/) |

## Suggested Use

| Use Case | Recommended Sources |
|---|---|
| Policy and regulatory analysis | OECD AI Incidents Monitor, AIID, NIST, ENISA |
| AI security threat analysis | MITRE ATLAS, AVID, CISA, ENISA |
| AI safety and harm analysis | OECD AI Incidents Monitor, AIID, Partnership on AI, MLCommons AILuminate |
| Model evaluation and assurance | HELM, MLCommons AILuminate, UK AISI, NIST |
| Frontier AI safety review | OpenAI, Anthropic, Google DeepMind, UK AISI |
| National cyber and critical infrastructure planning | CISA, ENISA, NIST, MITRE ATLAS |

## Incident Classification Dimensions

AI incident repositories can be analyzed using the following dimensions:

| Dimension | Examples |
|---|---|
| Harm type | Physical, economic, reputational, psychological, rights-based, societal, cybersecurity |
| Lifecycle stage | Design, training, testing, deployment, monitoring, retirement |
| Technical cause | Data issue, model error, misalignment, prompt injection, unsafe automation, tool misuse, integration failure |
| Actor type | Developer, deployer, user, malicious actor, third party, autonomous system |
| System type | Predictive ML, generative AI, recommender system, computer vision, autonomous system, AI agent |
| Sector | Healthcare, finance, education, defense, public sector, social media, transportation, critical infrastructure |
| Severity | Near miss, minor harm, major harm, systemic harm, catastrophic risk indicator |

## Notes

1. Incident repositories differ in scope. Some collect real-world incidents, while others collect vulnerabilities, evaluations, safety reports, or case studies.
2. The OECD AI Incidents Monitor is especially useful for policy-level trend analysis and cross-sector visibility.
3. MITRE ATLAS and AVID are especially useful for AI security and adversarial machine-learning analysis.
4. AIID is especially useful as a general-purpose historical repository of real-world AI failures and harms.

## APA 7 References

AI Incident Database. (n.d.). *AI Incident Database*. https://incidentdatabase.ai/

AI Vulnerability Database. (n.d.). *AVID: AI vulnerability database*. https://avidml.org/

McGregor, S. (2020). *Preventing repeated real world AI failures by cataloging incidents: The AI Incident Database*. arXiv. https://arxiv.org/abs/2011.08512

MITRE. (n.d.). *MITRE ATLAS: Adversarial threat landscape for artificial-intelligence systems*. https://atlas.mitre.org/

Organisation for Economic Co-operation and Development. (n.d.). *OECD AI Incidents Monitor*. OECD.AI Policy Observatory. https://oecd.ai/en/incidents

Stanford Center for Research on Foundation Models. (n.d.). *Holistic evaluation of language models*. https://crfm.stanford.edu/helm/
