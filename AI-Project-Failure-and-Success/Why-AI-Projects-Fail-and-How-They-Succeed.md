# Why AI Projects Fail and How They Can Succeed

This page examines why artificial intelligence projects fail, why many prototypes never become dependable production systems, and how governance, cybersecurity, data engineering, product management, and operational assurance can improve the probability of success.

The primary source is the RAND Corporation study by Ryseff, De Bruhl, and Newberry (2024), supplemented by the NIST AI Risk Management Framework, the U.S. Government Accountability Office AI accountability framework, and research on AI functionality and deployment.

## Executive summary

AI project failure is rarely caused by model accuracy alone. The recurring causes are usually socio-technical:

1. The organization selects or communicates the wrong problem.
2. The available data are unsuitable, incomplete, poorly governed, or misunderstood.
3. Teams pursue fashionable technology rather than user and mission value.
4. The organization lacks the infrastructure and engineering capability needed for production.
5. The proposed use case exceeds the practical limitations of the technology.
6. Governance, security, assurance, and operational ownership are introduced too late.

A successful AI project therefore requires more than a capable model. It requires a durable problem, measurable value, reliable data, domain expertise, secure architecture, production engineering, continuous evaluation, accountable ownership, and an explicit decision to stop when the evidence does not justify deployment.

## RAND study at a glance

Ryseff et al. (2024) conducted semi-structured interviews with 65 experienced AI practitioners. The sample included 50 industry participants and 15 academic participants. Industry interviewees had at least five years of AI or machine-learning experience and represented multiple organization sizes and sectors.

The RAND study focused mainly on machine-learning projects, including supervised, unsupervised, reinforcement-learning, and customized large-language-model applications. Projects limited to prompt engineering with a pretrained model were outside the study scope.

### Important interpretation of the often-cited 80 percent figure

RAND reports that, by some estimates, more than 80 percent of AI projects fail. This figure was not calculated from RAND's 65 interviews. It is an external estimate cited by the report. The strongest contribution of the RAND study is therefore not a universal failure-rate statistic, but its qualitative identification of recurring anti-patterns and root causes from experienced practitioners.

Organizations should define failure explicitly for each initiative. Failure may include:

- cancellation before deployment;
- deployment without measurable user or mission value;
- unacceptable security, safety, legal, or privacy risk;
- inability to integrate the model into operational workflows;
- excessive cost or latency;
- deterioration after deployment because of drift or changing context;
- inability to maintain, audit, explain, or retire the system safely.

## Five leading root causes identified by RAND

| Root cause | Typical anti-pattern | Operational consequence | Cybersecurity and assurance consequence | Corrective action |
| --- | --- | --- | --- | --- |
| Leadership-driven failure | The team is asked to build AI before the problem, user, workflow, decision, and success metric are understood | A technically impressive model optimizes the wrong outcome or is not adopted | Threat modeling and control selection are performed against an unstable or misunderstood use case | Establish a named business or mission owner, document the decision to be improved, define measurable value, and validate the workflow before model development |
| Data-driven failure | Leaders assume that large volumes of historical data are automatically suitable for training | Models are inaccurate, biased, brittle, or impossible to reproduce | Unknown provenance, poisoned or manipulated records, excessive sensitive data, and weak lineage undermine trust | Perform data-readiness assessment, document provenance and purpose, test quality and representativeness, and assign data owners and stewards |
| Bottom-up technology failure | Data scientists pursue the newest model, framework, or architecture regardless of fit | Cost and complexity increase without proportional benefit | New dependencies, models, plugins, and services expand the attack surface and supply-chain risk | Require comparison with simple rules, conventional software, statistical baselines, and established models before approving a complex approach |
| Underinvestment in infrastructure | The organization funds experimentation but not data pipelines, deployment automation, monitoring, identity, logging, or rollback | A prototype cannot be deployed or maintained reliably | Security controls become manual and inconsistent; drift, abuse, exfiltration, and unauthorized changes may go undetected | Fund DataOps, MLOps or ModelOps, secure CI/CD, model registries, observability, access control, incident response, and recovery capabilities |
| Immature or unsuitable technology | AI is applied to a problem that requires certainty, unavailable context, rare-event data, or subjective judgment beyond the system's capability | The project fails even with strong execution | Teams may compensate with excessive permissions, unsafe autonomy, weak human oversight, or misleading confidence | Conduct feasibility analysis, define uncertainty and abstention behavior, limit autonomy, retain human authority, and stop projects whose residual risk exceeds value |

## Additional anti-patterns

### Optimizing a proxy instead of the real outcome

A model metric is not automatically a business, mission, safety, or security metric. Accuracy, F1 score, BLEU score, reward, or benchmark position may improve while the operational outcome does not.

Examples include:

- optimizing click-through rate when the actual goal is profitable and trustworthy engagement;
- maximizing alert detection while overwhelming analysts with false positives;
- optimizing code generation speed while increasing vulnerabilities and review burden;
- measuring chatbot fluency rather than factual accuracy, task completion, escalation quality, and user harm;
- evaluating an autonomous agent in a laboratory while ignoring its production permissions and accessible tools.

Each project should maintain a traceable chain:

**Organizational objective → user decision or workflow → AI-supported function → model metric → operational metric → risk and control metric.**

### Treating AI as mandatory

The decision process should permit four valid outcomes:

1. Use AI.
2. Use AI only as decision support.
3. Use a deterministic or conventional software solution.
4. Do not automate the task.

A project governance process that cannot select options 2, 3, or 4 is likely to produce technology-driven failure.

### Assuming a prototype is nearly a product

A demonstration usually proves only that a model can produce a promising result under selected conditions. Production requires much more:

- dependable data ingestion;
- secure identity and secrets management;
- version control for data, prompts, models, policies, and tools;
- repeatable testing and evaluation;
- latency, availability, and cost engineering;
- privacy and legal review;
- threat modeling and adversarial testing;
- monitoring for drift, abuse, and policy violations;
- rollback, fallback, and incident response;
- user training and workflow redesign;
- ownership throughout the system lifecycle.

### Rigidly applying traditional software delivery practices

RAND interviewees observed that rigid interpretations of short software-development sprints can be a poor fit for AI work. Data exploration and experimentation are uncertain and cannot always be decomposed into predictable increments.

This does not justify uncontrolled research. AI projects need adaptive governance with time-boxed experiments, documented hypotheses, evidence reviews, frequent stakeholder communication, and explicit continuation or termination decisions.

### Ignoring the people affected by deployment

Domain experts, operators, analysts, users, security teams, legal advisers, and affected communities may hold essential information that is absent from the dataset. Excluding them can produce technically valid but operationally unusable systems.

Resistance should not automatically be interpreted as opposition to innovation. It may reveal:

- missing workflow context;
- unsafe assumptions;
- loss of professional judgment;
- unmanageable alert or review burdens;
- unclear accountability;
- fear of displacement;
- legal, ethical, privacy, or security concerns.

## Why cybersecurity is a project-success requirement

Cybersecurity is often treated as a deployment gate added after model development. This approach can cause both security failure and project failure.

| Security issue discovered late | Project impact |
| --- | --- |
| Training or retrieval data cannot legally or securely be used | The model must be retrained or the use case abandoned |
| The model requires unrestricted network or tool access | Production approval is delayed or denied |
| Sensitive prompts and outputs are logged without adequate protection | Privacy, regulatory, and incident-response risk increases |
| Third-party models or dependencies lack provenance and integrity evidence | Supply-chain assurance becomes impossible |
| The system cannot explain, reproduce, or audit consequential actions | Operational and governance acceptance fails |
| No safe fallback, rollback, or human override exists | The system cannot meet resilience requirements |
| Prompt injection or indirect context manipulation changes tool behavior | The agent may perform unauthorized actions or disclose data |
| Model or data drift is not monitored | Performance and security assumptions silently expire |

Security by design reduces rework by making data classification, trust boundaries, identity, permissions, logging, isolation, human oversight, incident handling, and recovery part of the architecture from the beginning.

## AI project success lifecycle

### Gate 0: Problem and value definition

**Required evidence**

- named business, mission, and risk owners;
- clearly defined user and operational workflow;
- baseline performance without AI;
- measurable benefit and harm criteria;
- comparison with non-AI alternatives;
- expected lifetime of the problem;
- initial legal, ethical, privacy, safety, and cybersecurity screening.

**Stop condition:** The problem is temporary, poorly defined, not valuable enough, or better solved without AI.

### Gate 1: Data and knowledge readiness

**Required evidence**

- data inventory and lineage;
- documented collection purpose and provenance;
- lawful authority, consent, license, and retention rules;
- quality, completeness, timeliness, and representativeness analysis;
- poisoning, tampering, and integrity controls;
- sensitivity classification and access restrictions;
- domain-expert review;
- plan for data updates and changing semantics.

**Stop condition:** Required data cannot be obtained, trusted, governed, or used responsibly.

### Gate 2: Feasibility and baseline evaluation

**Required evidence**

- simple deterministic and statistical baselines;
- documented model-selection rationale;
- representative evaluation dataset separated from training data;
- uncertainty, calibration, abstention, and failure-mode analysis;
- initial red-team and abuse-case testing;
- cost, latency, compute, and integration estimates;
- assessment of whether the technology is mature enough for the use case.

**Stop condition:** The AI approach does not materially outperform a simpler solution or cannot satisfy minimum risk and performance requirements.

### Gate 3: Production and security readiness

**Required evidence**

- secure architecture and threat model;
- least-privilege identities and scoped credentials;
- model, dataset, prompt, policy, and dependency versioning;
- secure CI/CD and artifact integrity verification;
- automated deployment, rollback, and fallback;
- logging, auditability, observability, and alerting;
- evaluation of prompt injection, data leakage, model abuse, supply-chain compromise, and unauthorized tool use;
- incident-response and vulnerability-disclosure procedures;
- capacity, resilience, cost, and service-level testing.

**Stop condition:** The prototype cannot be operated, monitored, secured, or recovered within acceptable risk.

### Gate 4: Controlled deployment

**Required evidence**

- limited pilot population or environment;
- human review or approval proportionate to impact and autonomy;
- explicit user communication and training;
- canary release, shadow mode, or staged activation where practical;
- comparison against the pre-AI baseline;
- monitoring of operational value, security, safety, fairness, privacy, cost, and user burden;
- authority to pause or disable the system.

**Stop condition:** Operational value is not demonstrated or harms and residual risks exceed approved tolerance.

### Gate 5: Continuous operation and assurance

**Required evidence**

- data, concept, model, and behavior-drift monitoring;
- recurring security and safety evaluation;
- incident, near-miss, override, and abstention analysis;
- benefit-realization tracking;
- periodic access and permission review;
- third-party model and dependency reassessment;
- retraining, revalidation, rollback, and retirement criteria;
- independent assurance for high-impact systems.

**Stop condition:** The system no longer provides sufficient value, cannot be maintained, or has accumulated unacceptable risk.

### Gate 6: Retirement

**Required evidence**

- safe shutdown and replacement plan;
- revocation of credentials, tools, and service access;
- archival or deletion of data and model artifacts according to policy;
- preservation of required audit and incident evidence;
- communication to users and affected stakeholders;
- lessons-learned review.

## Mapping RAND findings to NIST AI RMF

| RAND root cause | GOVERN | MAP | MEASURE | MANAGE |
| --- | --- | --- | --- | --- |
| Wrong or misunderstood problem | Establish accountability, policy, roles, and stakeholder communication | Define context, users, intended purpose, impacts, and assumptions | Measure operational outcomes, not only model performance | Re-scope or stop the project when evidence does not support value |
| Unsuitable data | Define data ownership and governance | Map data sources, provenance, affected groups, and limitations | Test quality, representativeness, integrity, privacy, and bias | Improve, restrict, replace, or reject the dataset |
| Technology-first behavior | Establish selection and architecture decision controls | Compare AI and non-AI alternatives | Benchmark against simple baselines and total lifecycle cost | Select the least complex solution that meets the objective |
| Infrastructure underinvestment | Assign lifecycle and operational ownership | Map integration, supply chain, and deployment dependencies | Test reliability, security, resilience, and observability | Build shared infrastructure, deploy controls, and maintain rollback capability |
| Immature technology | Define risk tolerance and approval authority | Map technical limits and high-impact failure scenarios | Evaluate uncertainty, robustness, adversarial behavior, and human baseline | Limit scope or autonomy, require human control, delay deployment, or terminate |

## Balanced AI project scorecard

A project should not be declared successful on a single model metric.

| Dimension | Example measures |
| --- | --- |
| Mission or business value | time saved, loss reduced, revenue improved, mission effect, decision quality, user task completion |
| Model quality | accuracy, precision, recall, calibration, robustness, abstention quality, subgroup performance |
| Operational performance | availability, latency, throughput, integration success, human review burden, fallback rate |
| Security | prompt-injection resistance, data leakage rate, unauthorized action attempts, privilege violations, vulnerability remediation time |
| Safety and responsibility | harmful-output rate, override rate, near misses, fairness indicators, affected-person complaints |
| Data health | freshness, completeness, lineage coverage, integrity failures, drift indicators |
| Governance and assurance | evidence completeness, approval status, audit findings, control effectiveness, unresolved residual risk |
| Economics | development cost, inference cost, maintenance cost, cost per successful task, realized benefit |
| Adoption | active use, user trust, workflow fit, abandonment rate, training completion |

## Executive decision checklist

Before funding or continuing an AI project, leaders should be able to answer:

1. What enduring problem are we solving, for whom, and in which workflow?
2. Why is AI superior to a rule, search system, conventional application, process change, or human decision?
3. Who owns value, risk, data, the model, security, operations, and retirement?
4. What baseline and measurable success criteria will be used?
5. Do we possess lawful, representative, timely, and trustworthy data?
6. What are the system's known limitations and required abstention conditions?
7. How will the system fail safely?
8. What permissions, tools, data, and networks can the system access?
9. How will security, privacy, safety, bias, drift, cost, and benefit be monitored?
10. What evidence is required before each deployment stage?
11. Who has authority to pause, roll back, or terminate the system?
12. Under what conditions will the project be stopped rather than repeatedly extended?

## Early warning indicators

The following conditions indicate elevated failure risk:

- the project name contains a technology but no user problem;
- the sponsor cannot define the decision or workflow to be improved;
- no non-AI baseline is permitted;
- model accuracy is the only success metric;
- data ownership and provenance are unknown;
- security, privacy, legal, and domain experts are scheduled only before launch;
- the prototype depends on manually prepared data or hidden analyst work;
- no production owner exists;
- deployment requires broad administrator, network, database, or tool access;
- stakeholders expect deterministic behavior from a probabilistic system;
- priorities change faster than the team can complete data exploration and validation;
- the project repeatedly changes models without improving operational value;
- there is no budget for monitoring, retraining, incident response, and retirement;
- stopping the project is treated as organizational failure rather than responsible governance.

## Recommended organizational model

High-impact AI initiatives should use a multidisciplinary product and assurance team rather than an isolated data-science team.

| Role | Primary responsibility |
| --- | --- |
| Executive or mission sponsor | enduring objective, funding, risk acceptance, strategic alignment |
| Product or service owner | user need, workflow integration, benefit realization, prioritization |
| Domain expert | real-world context, data meaning, edge cases, professional judgment |
| Data owner and steward | provenance, quality, access, lawful use, retention, lineage |
| Data and ML engineers | pipelines, model development, deployment, reproducibility, monitoring |
| Security architect and engineer | threat model, identity, access, isolation, supply chain, monitoring, response |
| Privacy, legal, ethics, and compliance specialists | rights, obligations, impact assessment, acceptable use |
| Independent evaluator or assurance function | validation independent from the development team |
| Operations and incident-response teams | runtime ownership, escalation, recovery, evidence preservation |
| User and affected-stakeholder representatives | usability, burden, trust, adverse impacts, feedback |

## Key conclusion

AI projects succeed when organizations treat them as governed socio-technical systems, not isolated model-development exercises. The central management question is not, "Which AI technology should we deploy?" It is:

> **Which enduring problem should be solved, what evidence will demonstrate value and acceptable risk, and what secure operational system is required to sustain that result?**

The discipline to reject unsuitable use cases, select simpler solutions, delay unsafe deployment, or terminate projects without sufficient evidence is a sign of AI maturity rather than failure.

## APA 7 references

National Institute of Standards and Technology. (2023). *Artificial intelligence risk management framework (AI RMF 1.0)* (NIST AI 100-1). https://doi.org/10.6028/NIST.AI.100-1

Raji, I. D., Kumar, I. E., Horowitz, A., & Selbst, A. D. (2022). The fallacy of AI functionality. In *Proceedings of the 2022 ACM Conference on Fairness, Accountability, and Transparency* (pp. 959–972). Association for Computing Machinery. https://doi.org/10.1145/3531146.3533158

Ryseff, J., De Bruhl, B. F., & Newberry, S. J. (2024). *The root causes of failure for artificial intelligence projects and how they can succeed: Avoiding the anti-patterns of AI* (RR-A2680-1). RAND Corporation. https://doi.org/10.7249/RRA2680-1

U.S. Government Accountability Office. (2021). *Artificial intelligence: An accountability framework for federal agencies and other entities* (GAO-21-519SP). https://www.gao.gov/products/gao-21-519sp
