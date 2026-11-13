# MLSecOps Practical Reference Guide

## Overview

The **MLSecOps Practical Reference Guide** by Moslem Haghighian is a practitioner-oriented reference for integrating security into machine learning and AI operations. It covers security considerations across AI/ML development, deployment, and operation, including LLM applications, retrieval-augmented generation (RAG), and AI agents.

- **Author:** Moslem Haghighian
- **Resource type:** Practical security engineering guide
- **Publication record:** https://zenodo.org/records/23570649
- **DOI:** https://doi.org/10.5281/zenodo.23570649
- **Project website:** https://mhaghighian.github.io/MLSecOps/
- **Source repository:** https://github.com/MHaghighian/MLSecOps

## Security engineering relevance

| Area | Practical relevance |
| --- | --- |
| Secure AI/ML lifecycle | Incorporating security reviews, risk assessments, and operational controls into ML workflows |
| LLM and RAG security | Evaluating application-specific trust boundaries, retrieved content, and sensitive-data exposure |
| Agentic AI | Examining tool permissions, autonomy, runtime monitoring, and human oversight |
| Release governance | Applying documented checks and decision gates before deployment |
| Monitoring and privacy | Establishing operational visibility while respecting data protection requirements |
| Supply chain | Reviewing datasets, model artifacts, dependencies, and software integrity |
| Standards mapping | Supporting comparisons with NIST, OpenSSF, and related security guidance, subject to verification of specific mappings |

## How to use

1. Consult the original guide when designing or reviewing secure ML and AI delivery pipelines.
2. Convert relevant recommendations into verifiable engineering requirements and evidence-producing release gates.
3. Evaluate applicability separately for conventional ML, LLM/RAG, and autonomous agents.
4. Verify individual control identifiers, release dates, and normative claims against the source before adopting them as compliance requirements.

## Secure deployment of open-weight AI models

The Australian Signals Directorate's [Open-Weight AI Models: Selecting, Deploying and Operating Open-Weight AI Models Securely](https://www.cyber.gov.au/publication/open-weight-ai-models-selecting-deploying-and-operating-open-weight-ai-models-securely) covers model selection, deployment, and ongoing assurance. Verify the specific release, its provenance, and the distributor before adoption. Enforce access and network egress restrictions outside the model, and require approval for high-risk or irreversible actions. Carry the same controls into reevaluation when the deployed model or its environment changes.

## AI data supply chain security

| Resource | Practical use |
| --- | --- |
| [ETSI GR SAI 002 V1.1.1 - Data Supply Chain Security](https://www.etsi.org/deliver/etsi_gr/SAI/001_099/002/01.01.01_60/gr_SAI002v010101p.pdf) | Use the group report to identify supply-chain paths for data manipulation and poisoning during AI development and operation. |
| [AI Data Security - Joint Cybersecurity Information Sheet](https://www.nsa.gov/Press-Room/Press-Releases-Statements/Press-Release-View/Article/4192332/nsas-aisc-releases-joint-guidance-on-the-risks-and-best-practices-in-ai-data-se/) | Track data provenance, authenticate trusted revisions with signatures, and address malicious modification and data drift across training, testing, and operation. |

## References

Australian Signals Directorate. (2026, November 5). *Open-weight AI models: Selecting, deploying and operating open-weight AI models securely*. https://www.cyber.gov.au/publication/open-weight-ai-models-selecting-deploying-and-operating-open-weight-ai-models-securely

European Telecommunications Standards Institute. (2021, August). *Securing artificial intelligence (SAI): Data supply chain security* (ETSI GR SAI 002 V1.1.1). https://www.etsi.org/deliver/etsi_gr/SAI/001_099/002/01.01.01_60/gr_SAI002v010101p.pdf

Haghighian, M. (2026). *MLSecOps practical reference guide* [Practical guide]. Zenodo. https://doi.org/10.5281/zenodo.23570649

National Security Agency. (2025, May 22). *NSA's AISC releases joint guidance on the risks and best practices in AI data security* [Press release]. https://www.nsa.gov/Press-Room/Press-Releases-Statements/Press-Release-View/Article/4192332/nsas-aisc-releases-joint-guidance-on-the-risks-and-best-practices-in-ai-data-se/

**Editorial note:** This is a curated resource description, not a reproduction of the original guide. The source's detailed controls and maturity claims should be checked against its latest version.
