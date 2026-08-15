# CyberAI Field Guide

## Overview

The **CyberAI Field Guide** is a practical educational resource developed by the SPEX research group at the University of North Carolina at Charlotte. It connects cybersecurity assessment, AI security, risk management, qualitative interviewing, organizational behavior, and socio-technical threat modeling.

The guide is particularly useful for practitioners assessing real-world AI-enabled systems because it treats AI risk as broader than model vulnerabilities alone. It emphasizes the interaction between technology, models, data, dependencies, people, organizational processes, incentives, and governance.

**Primary source:** https://spexlab.org/CyberAI_Field_Guide.html

## Core Components

### 1. Interviewing for Impact

The guide encourages practitioners to move beyond checklist-oriented auditing and understand how security and AI controls operate in practice. Interviews should identify operational constraints, workarounds, incentives, friction, and the reasons controls may be bypassed or fail.

### 2. Qualitative Interview Moderating

The methodology emphasizes neutral questions, probing, reconstruction of concrete events, active listening, and avoiding leading questions. This supports stronger evidence collection during cybersecurity and AI risk assessments.

### 3. Algorithmic Dependencies

AI systems should be assessed as dependency chains rather than isolated models. Relevant dependencies may include:

- Applications and user interfaces
- Orchestration and middleware
- APIs
- Foundation models
- Cloud services
- Open-source libraries
- Vector databases
- External datasets and services

This perspective helps expose risks involving third-party providers, credentials, data retention, availability, model drift, prompt injection, evasion, and supply-chain dependencies.

### 4. Problem Diagnosis and Reframing

The requested technical solution may not represent the underlying organizational problem. Practitioners should identify root causes before recommending technologies. For example, a request for an AI security chatbot may mask deficiencies in access control, knowledge management, data governance, or operational processes.

### 5. Cybersecurity and AI Asset Inventory

The guide expands traditional asset inventory concepts to AI-specific assets, including:

- Training data
- Evaluation datasets
- Embeddings
- Synthetic data
- Model weights
- Checkpoints
- Fine-tuned models
- Third-party AI APIs

This complements established approaches such as NIST CSF 2.0, NIST AI RMF, ISO/IEC 27001, ISO/IEC 42001, MITRE ATT&CK, STRIDE, and CIS Controls.

### 6. Socio-Technical Threat Modeling

A central contribution of the guide is the explicit integration of technical and socio-organizational risk. Threat modeling should consider not only how an attacker can compromise a system, but also how people, processes, incentives, trust, governance, and AI behavior combine to create risk.

The guide adapts familiar threat-modeling concepts to issues such as:

- Trust in AI-generated outputs
- Data pollution and bias amplification
- Accountability and repudiation gaps
- Privacy and consent failures
- Excessive control friction that encourages workarounds
- Organizational dependence on AI services

## Relevance to AI Cybersecurity

A useful abstraction of the guide's perspective is:

> **CyberAI Risk = Technology + AI Models + Data + Dependencies + Humans + Processes + Governance**

This is especially relevant to Generative AI and Agentic AI, where security failures may emerge across model, application, identity, tool, data, infrastructure, supply-chain, and human decision layers.

## Recommended Use

The CyberAI Field Guide is best treated as a **practical assessment methodology and educational aid**, not as a normative security standard. It can complement formal frameworks and standards such as:

- NIST AI Risk Management Framework
- NIST Cybersecurity Framework 2.0
- ISO/IEC 42001
- ISO/IEC 27001
- OWASP guidance for LLM and Agentic AI security
- MITRE ATLAS
- Cloud Security Alliance AI security guidance

Recommended use cases include:

1. AI security assessments
2. Cybersecurity clinic engagements
3. AI governance reviews
4. AI threat modeling workshops
5. AI asset and dependency discovery
6. Socio-technical risk assessments
7. Security interviews with business and technical stakeholders
8. Generative AI and Agentic AI architecture reviews

## Repository Classification

| Dimension | Classification |
| --- | --- |
| Type | Practical field guide / assessment methodology |
| Primary focus | Cybersecurity and AI risk assessment |
| Secondary focus | Socio-technical security and organizational risk |
| Applicable lifecycle | Design, assessment, deployment, and operations |
| Primary audience | Security practitioners, consultants, students, architects, governance teams |
| Normative status | Non-normative educational and practitioner guidance |

## Reference

SPEX Research Group. (n.d.). *CyberAI Field Guide*. University of North Carolina at Charlotte. https://spexlab.org/CyberAI_Field_Guide.html

> **Note:** The field guide should be used as a complementary practitioner resource. Formal compliance, assurance, or certification decisions should rely on the applicable authoritative standards, laws, and regulatory requirements.
