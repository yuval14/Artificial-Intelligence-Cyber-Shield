# Google DeepMind Frontier Safety Framework (FSF)

**Current version:** 3.1  
**Published:** April 17, 2026  
**Organization:** Google DeepMind  
**Category:** Frontier AI safety, capability-risk governance, model security, deployment assurance

## Overview

Google DeepMind's **Frontier Safety Framework (FSF)** is a capability-based risk management framework for identifying, evaluating, and mitigating significant or severe risks that may arise from frontier AI models. The Framework complements Google's broader AI responsibility and safety practices and is intended to support responsible development and deployment as frontier model capabilities increase.

The FSF is designed around four recurring functions:

1. Identify capability levels at which frontier AI models could create significant or severe risk without additional mitigations.
2. Detect whether models are approaching or have reached those capability levels throughout the model lifecycle.
3. Prepare and apply proportionate security and deployment mitigations.
4. Involve external parties, including government or independent experts, where required or appropriate.

Version 3.1 strengthens the Framework's risk management process, introduces **Tracked Capability Levels (TCLs)** in selected domains, expands governance detail, and strengthens recommended security for several Critical Capability Levels.

## Why the FSF matters for cybersecurity

The FSF is important to cybersecurity because it treats advanced AI capability itself as a security-relevant risk factor. In particular, it recognizes that highly capable models may:

- provide meaningful uplift to cyber threat actors;
- increase the feasibility, scale, or speed of high-impact cyber operations;
- become valuable targets for model-weight theft or unauthorized modification;
- require stronger protection against insider threats and well-resourced external actors;
- introduce risks from high-risk internal deployments, including advanced AI agents with access to sensitive systems;
- require continuous evaluation, monitoring, residual-risk assessment, and governance rather than one-time certification.

For cybersecurity leaders, the Framework provides a useful model for linking **capability thresholds to progressively stronger controls**.

## Core concepts

### Critical Capability Levels (CCLs)

**Critical Capability Levels** are thresholds at which, absent additional mitigations, a frontier AI model or system may pose a heightened risk of **severe harm**.

CCLs are not simply model-performance scores. They are derived from threat scenarios and from analysis of the minimum capabilities required for a model to materially contribute to severe harm.

### Tracked Capability Levels (TCLs)

Version 3.1 introduces **Tracked Capability Levels** for selected risk domains. TCLs represent lower thresholds than CCLs and are intended to identify **significant but not yet severe risk** earlier, allowing proportionate mitigations and risk-management processes to begin before a model reaches a CCL.

In FSF 3.1, TCLs are defined for:

- CBRN risk; and
- ML R&D and misalignment risk.

### Alert thresholds

Google DeepMind also uses **alert thresholds** positioned before CCLs. Their purpose is to provide an operational safety buffer so that mitigation and governance actions can begin before model capability progresses past a critical threshold.

## Risk domains in FSF 3.1

| Risk domain | Primary concern | Capability governance mechanism |
| --- | --- | --- |
| CBRN | AI assistance in the development, preparation, or execution of chemical, biological, radiological, or nuclear threats | TCLs, CCLs, security and deployment mitigations |
| Cyber | AI assistance in the development, preparation, or execution of cyber attacks | Cyber CCL, security and deployment mitigations |
| Harmful manipulation | AI capabilities that could systematically and substantially change beliefs or behavior in high-stakes contexts and contribute to severe harm | Exploratory CCL, security and deployment mitigations |
| ML R&D and misalignment | AI capabilities or propensities that could reduce society's ability to manage advanced-AI risks, including through accelerated AI development or loss of human control | TCLs, ML R&D CCLs, security and deployment mitigations |

## Cyber Critical Capability Level

FSF 3.1 defines a cyber CCL called **Cyber uplift level 1**.

The threshold concerns a model that provides sufficient uplift in high-impact cyber attacks to create additional expected harm at severe scale.

Google DeepMind recommends **Security Level 2+** for models reaching this cyber threshold.

This is operationally significant because the Framework explicitly connects advanced offensive cyber capability with stronger protection of model weights and infrastructure. The threat model is not limited to misuse through a public interface. It also considers risks created if model weights are exfiltrated, modified, or otherwise accessed outside the intended control environment.

## Security Level 2+

FSF 3.1 uses the RAND model-weight security framework as a reference for security goals and introduces **Security Level 2+** as an enhanced baseline.

Security Level 2+ builds on RAND Security Level 2 and adds protections intended to address risks from insider threats and well-resourced non-state actors.

Examples identified by Google DeepMind include:

- dedicated insider-risk capabilities;
- background checks and identity verification for personnel with sensitive access;
- review of model training data for signs of tampering;
- sandboxing for processing untrusted inputs;
- advanced red teaming that simulates well-resourced adversaries, including APT-like actors;
- proactive threat hunting; and
- 24/7 incident response capability.

The Framework emphasizes security goals rather than treating the RAND reference levels as a complete compliance standard.

## ML R&D security escalation

FSF 3.1 recommends stronger security as AI models become capable of materially accelerating or automating AI research and development.

| ML R&D capability threshold | Recommended security level | Security implication |
| --- | --- | --- |
| ML R&D acceleration level 1 | Security Level 3 | Strengthened protection against unilateral access, infrastructure compromise, and data exfiltration |
| ML R&D automation level 1 | Security Level 4 | Exceptional security, stronger isolation of model weights, enhanced data-center security, infrastructure hardening, and attack-surface reduction |

This reflects the Framework's concern that unrestricted access to models capable of substantially accelerating AI development could enable rapid progression toward still more powerful capabilities.

## Risk management lifecycle

FSF 3.1 describes a lifecycle-oriented risk-management process.

### 1. Risk identification

Potential significant and severe risks are identified using threat scenarios, model characteristics, internal risk taxonomies, expert judgment, external research, and operational evidence.

### 2. Inherent risk assessment

Google DeepMind assesses whether models are approaching or crossing TCLs or CCLs. The process includes:

- material capability change assessments;
- critical capability assessments;
- early-warning evaluations;
- expert assessment;
- model-independent information;
- external evaluations where appropriate; and
- post-market monitoring.

### 3. Risk mitigation

The FSF distinguishes between two broad categories of mitigation.

**Security mitigations** are intended to prevent unauthorized modification or exfiltration of model weights and related critical assets.

**Deployment mitigations** are intended to prevent or reduce misuse or misaligned expression of dangerous capabilities during deployment.

### 4. Residual risk assessment

The effectiveness and limitations of mitigations are evaluated after controls are applied. Security controls may be tested through penetration testing and related security assessments. Deployment controls may be assessed through threat modeling, empirical testing, automated evaluations, and red teaming.

When a model reaches a CCL, the residual-risk assessment is supplemented with a **safety case**.

### 5. Risk acceptance determination

Further development or deployment depends on whether the appropriate governance function determines that residual risk has been reduced to an acceptable level.

This makes risk acceptance an explicit governance decision rather than an implicit consequence of technical testing.

## Deployment mitigations

For misuse-related T/CCLs, Google DeepMind describes a structured mitigation process that can include:

- safety post-training;
- monitoring and analysis;
- account moderation;
- jailbreak detection and patching;
- user verification;
- bug bounty programs;
- automated evaluations;
- red teaming;
- threat modeling; and
- post-deployment monitoring and reassessment.

For ML R&D and misalignment risks, safeguards may additionally include:

- limiting model affordances;
- monitoring and escalation;
- auditing;
- alignment training; and
- controls for high-risk internal deployments.

## High-risk internal deployment

A notable security implication of FSF 3.1 is its explicit treatment of **high-risk internal deployment**.

Internal use is not automatically treated as low risk. Internal deployments may require enhanced assessment and safeguards when they could enable severe threat scenarios, for example when advanced models are used to build security infrastructure or automate ML R&D.

This is particularly relevant to agentic AI systems with privileged identities, access to source code, cloud environments, development pipelines, sensitive data, or security tooling.

## Stealth and Situational Awareness TCL

FSF 3.1 introduces a **Stealth and Situational Awareness TCL** within the ML R&D and misalignment domain.

The threshold is intended to identify models whose instrumental reasoning provides sufficient situational awareness and stealth that, without additional safeguards, the possibility of significant erosion of human control cannot be ruled out.

When this TCL is reached, Google DeepMind describes periodic residual-risk assessment and potentially additional safeguards for high-risk internal use.

This concept is particularly relevant to:

- autonomous AI agents;
- privileged AI identities;
- insider-threat modeling for AI;
- monitor-evasion risk;
- multi-agent coordination;
- AI control and containment architectures.

## Governance and accountability

FSF 3.1 describes an internal governance structure with responsibility allocated across organizational levels and including legal, compliance, and safety review with escalation mechanisms.

The Framework also commits to periodic review. Google DeepMind states that the FSF will be reviewed at least annually and more frequently if there are reasonable grounds to believe that the Framework's adequacy or adherence to it has been materially undermined.

Where a model reaches a CCL that creates an unmitigated and material public-safety risk, Google DeepMind states that it aims to share relevant information with appropriate government authorities where doing so would facilitate frontier AI safety.

## Relationship to Google SAIF

The **Frontier Safety Framework** and **Secure AI Framework (SAIF)** are complementary but serve different purposes.

| Framework | Primary purpose |
| --- | --- |
| Google DeepMind FSF | Capability-threshold governance for significant and severe frontier-AI risks |
| Google SAIF | Secure engineering and defense-in-depth principles for AI systems and their lifecycle |

FSF uses SAIF and Google's common security infrastructure as part of the security foundation for protecting frontier models.

A useful enterprise interpretation is:

**FSF helps determine when risk requires stronger controls; SAIF helps structure how AI systems should be secured.**

## Mapping to Artificial Intelligence Cyber Shield

| Repository area | FSF contribution |
| --- | --- |
| AI Governance and Assurance | Adds capability-threshold governance, residual-risk assessment, explicit risk acceptance, safety cases, and escalation |
| AI Security Frameworks | Links frontier-model capability to progressive security levels and model-weight protection |
| AI Agent Security | Supports stronger controls for high-risk internal agent deployments and models with stealth or situational awareness |
| AI Threat Modeling | Provides severe-risk domains and capability thresholds that can be integrated into threat scenarios |
| AI Red Teaming | Supports early-warning evaluations, adversarial testing, safeguard testing, and capability assessment |
| AI Integrity | Reinforces protections against unauthorized model modification, tampering, and misaligned behavior |
| AI Incident Response | Connects post-market monitoring and incidents to reassessment of residual risk and mitigation adequacy |
| GDM AI Control Roadmap | FSF defines capability-risk governance thresholds; AI Control focuses on system-level control of potentially misaligned internal agents |

## Recommended enterprise security interpretation

Organizations do not need to operate a frontier-model lab to learn from the FSF. Several principles can be adapted to enterprise AI governance:

1. **Capability-based control escalation**: increase controls as model autonomy, cyber capability, tool use, reasoning, or access increases.
2. **Pre-deployment gates**: require formal assessment before models with high-impact capabilities receive sensitive tools, data, identities, or network access.
3. **Continuous capability reassessment**: reassess security when post-training, new tools, agentic orchestration, memory, or expanded permissions materially change effective capability.
4. **Explicit risk acceptance**: ensure a defined governance authority owns the decision to accept residual AI risk.
5. **Safety and security cases**: require structured evidence that severe-risk scenarios are adequately controlled before high-risk deployment.
6. **Independent control planes**: separate monitoring, policy enforcement, and shutdown authority from the AI systems being governed.
7. **Model-weight and artifact security**: treat weights, adapters, system prompts, policies, training data, evaluation assets, secrets, and agent memory as security-sensitive assets.
8. **High-risk internal-use controls**: do not assume internal AI agents are safe merely because they operate inside the enterprise boundary.
9. **Red-team validation**: test whether safeguards continue to work against realistic evasion, privilege misuse, insider scenarios, and sophisticated threat actors.
10. **Post-deployment feedback**: feed incidents, observed misuse, jailbreaks, anomalies, and newly discovered capabilities back into the risk assessment.

## Key changes in Version 3.1

According to Google DeepMind, Version 3.1 includes the following major changes:

- introduction of CBRN TCLs and associated mitigation and risk-acceptance processes;
- consolidation of the earlier exploratory misalignment domain into a combined **ML R&D and Misalignment** domain;
- a TCL addressing stealth and situational awareness;
- enhanced security recommendations for CBRN, Cyber, and Harmful Manipulation CCLs to **Security Level 2+**;
- more detail on the end-to-end risk-management process;
- additional detail on internal governance; and
- a formal glossary.

## Limitations

The FSF should not be interpreted as a complete enterprise AI security standard or compliance regime.

Important limitations include:

- it is primarily designed for frontier AI development and severe-risk scenarios;
- several capability thresholds depend on evolving research and expert judgment;
- harmful-manipulation thresholds remain explicitly exploratory;
- concrete mitigations may evolve as model capability and the threat landscape change;
- many enterprise AI risks fall outside the severe-risk scope of the Framework and require broader security, privacy, safety, legal, and governance controls.

## Official sources

- [Google DeepMind - Frontier Safety](https://deepmind.google/frontier-safety/)
- [Frontier Safety Framework, Version 3.1 - PDF](https://storage.googleapis.com/deepmind-media/DeepMind.com/Blog/strengthening-our-frontier-safety-framework/frontier-safety-framework_3-1.pdf)
- [Google DeepMind - Strengthening our Frontier Safety Framework](https://deepmind.google/blog/strengthening-our-frontier-safety-framework/)
- [Google Secure AI Framework (SAIF)](https://saif.google/)

## APA 7 reference

Google DeepMind. (2026). *Frontier safety framework* (Version 3.1). https://storage.googleapis.com/deepmind-media/DeepMind.com/Blog/strengthening-our-frontier-safety-framework/frontier-safety-framework_3-1.pdf
