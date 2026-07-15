# Why AI Projects Fail and How They Can Succeed

This page examines why artificial intelligence projects fail, why many prototypes never become dependable production systems, and how governance, cybersecurity, data engineering, product management, organizational learning, and operational assurance can improve the probability of success.

The foundational source is the RAND Corporation study by Ryseff, De Bruhl, and Newberry (2024). The page also incorporates research published or released during 2025–2026 on organizational readiness, institutional deployment readiness, AI-system abandonment, human–AI team readiness, production incidents, software-engineering adoption, and workflow transformation.

## Executive summary

AI project failure is rarely caused by model accuracy alone. Recurring causes are usually socio-technical:

1. The organization selects or communicates the wrong problem.
2. The available data are unsuitable, incomplete, poorly governed, or misunderstood.
3. Teams pursue fashionable technology rather than user or mission value.
4. The organization lacks the infrastructure and engineering capability needed for production.
5. The proposed use case exceeds the practical limitations of the technology.
6. The receiving institution is not operationally, fiscally, legally, or organizationally ready.
7. Users are not prepared to rely on the system safely and appropriately.
8. Governance, security, assurance, and operational ownership are introduced too late.
9. Individual task improvements are mistaken for end-to-end organizational transformation.
10. Projects continue without explicit evidence-based stop, abandonment, or retirement criteria.

A successful AI project requires more than a capable model. It requires a durable problem, measurable value, reliable data, domain expertise, secure architecture, production engineering, institutional readiness, human oversight, continuous evaluation, accountable ownership, and the discipline to stop when evidence does not justify deployment.

## RAND study at a glance

Ryseff et al. (2024) conducted semi-structured interviews with 65 experienced AI practitioners. The sample included 50 industry participants and 15 academic participants. Industry interviewees had at least five years of AI or machine-learning experience and represented multiple organization sizes and sectors.

The RAND study focused mainly on machine-learning projects, including supervised, unsupervised, reinforcement-learning, and customized large-language-model applications. Projects limited to prompt engineering with a pretrained model were outside the study scope.

### Important interpretation of the often-cited 80 percent figure

RAND reports that, by some estimates, more than 80 percent of AI projects fail. This figure was not calculated from RAND's 65 interviews. It is an external estimate cited by the report. RAND's strongest contribution is therefore not a universal failure-rate statistic, but its qualitative identification of recurring anti-patterns and root causes from experienced practitioners.

Organizations should define failure explicitly for each initiative. Failure may include:

- cancellation before deployment;
- abandonment during development;
- a technically viable pilot that cannot obtain institutional approval;
- deployment without measurable user, mission, or business value;
- unacceptable security, safety, legal, ethical, or privacy risk;
- inability to integrate the model into operational workflows;
- excessive cost, latency, or human validation burden;
- deterioration after deployment because of drift or changing context;
- inability to maintain, audit, explain, recover, or retire the system safely.

## Five leading root causes identified by RAND

| Root cause | Typical anti-pattern | Operational consequence | Cybersecurity and assurance consequence | Corrective action |
| --- | --- | --- | --- | --- |
| Leadership-driven failure | The team is asked to build AI before the problem, user, workflow, decision, and success metric are understood | A technically impressive model optimizes the wrong outcome or is not adopted | Threat modeling and control selection are performed against an unstable or misunderstood use case | Establish a named business or mission owner, document the decision to be improved, define measurable value, and validate the workflow before model development |
| Data-driven failure | Leaders assume that large volumes of historical data are automatically suitable for training | Models are inaccurate, biased, brittle, or impossible to reproduce | Unknown provenance, poisoned or manipulated records, excessive sensitive data, and weak lineage undermine trust | Perform data-readiness assessment, document provenance and purpose, test quality and representativeness, and assign data owners and stewards |
| Bottom-up technology failure | Data scientists pursue the newest model, framework, or architecture regardless of fit | Cost and complexity increase without proportional benefit | New dependencies, models, plugins, and services expand the attack surface and supply-chain risk | Require comparison with simple rules, conventional software, statistical baselines, and established models before approving a complex approach |
| Underinvestment in infrastructure | The organization funds experimentation but not data pipelines, deployment automation, monitoring, identity, logging, or rollback | A prototype cannot be deployed or maintained reliably | Security controls become manual and inconsistent; drift, abuse, exfiltration, and unauthorized changes may go undetected | Fund DataOps, MLOps or ModelOps, secure CI/CD, model registries, observability, access control, incident response, and recovery capabilities |
| Immature or unsuitable technology | AI is applied to a problem that requires certainty, unavailable context, rare-event data, or subjective judgment beyond the system's capability | The project fails even with strong execution | Teams may compensate with excessive permissions, unsafe autonomy, weak human oversight, or misleading confidence | Conduct feasibility analysis, define uncertainty and abstention behavior, limit autonomy, retain human authority, and stop projects whose residual risk exceeds value |

## Research update: 2025–2026

The following studies extend RAND's analysis. Publication status is shown explicitly because several 2026 contributions are preprints and should not be represented as peer-reviewed studies unless their later publication status is verified.

| Year | Study | Evidence type and status | Main finding | Contribution to project governance |
| --- | --- | --- | --- | --- |
| 2026 | Chappidi and Singh, *To Build or Not to Build?* | Scoping review, incident-database analysis, and practitioner survey; preprint | AI systems are abandoned for diverse reasons, including ethics, stakeholder feedback, lifecycle challenges, organizational dynamics, resources, and legal or regulatory concerns | Treat non-development and abandonment as legitimate governance outcomes; define stop criteria before major investment |
| 2026 | Legara et al., *Beyond Model Readiness* | Two operational public-system cases and readiness framework; preprint | Technically viable systems may fail to scale because the receiving institution lacks operational compatibility, data arrangements, human oversight, fiscal continuity, or regulatory clarity | Add an institutional-readiness gate separate from model evaluation |
| 2026 | McClure and Gerdau, *Why AI Readiness Is an Organizational Learning Problem* | Synthesis of 19 large-scale academic and industry sources; preprint | AI readiness depends on organizational learning across leadership, human capital, data architecture, infrastructure, and governance | Fund capability development and workflow learning rather than treating AI as a technology purchase |
| 2026 | Lee, *From Accuracy to Readiness* | Human–AI evaluation framework; preprint | Accuracy does not show whether people will rely on AI appropriately, recover from errors, or improve over time | Measure reliance calibration, safety signals, error recovery, and team learning before deployment |
| 2026 | Gurgul et al., *The State of Generative AI in Software Development* | Systematic literature review and survey of 65 developers; preprint | Benefits vary by lifecycle phase; weak oversight may create uncritical adoption, technical debt, and skill erosion | Evaluate value by workflow phase and require human review, architectural reasoning, and governance |
| 2025 | Yan et al., *Production Incidents in Generative AI Cloud Services* | Four-year empirical production-incident analysis; preprint | GenAI services introduce distinctive reliability, output-quality, privacy, detection, triage, and mitigation challenges | Make observability, incident response, rollback, privacy protection, and service-quality engineering deployment prerequisites |
| 2025 | Giray et al., *Generative AI Adoption in Software Engineering* | Empirical practitioner study; preprint | Organizations often provide tool access without equivalent investment in training, governance, objective measurement, or validation capacity | Measure productivity and quality objectively; budget for review overhead, security, privacy, and workforce development |
| 2025 | Übellacker, *Making Sense of AI Limitations* | Semi-structured interviews with seven implementation experts; preprint | Sustainable adoption develops through realistic understanding of AI limitations, social learning, peer networks, and formal governance | Create safe experimentation, champions, feedback channels, and mechanisms that convert lessons into policy |
| 2025 | Dillon et al., *Shifting Work Patterns with Generative AI* | Six-month randomized field experiment involving 6,000 workers; preprint | AI changed independently adjustable work, such as email, more than coordination-heavy work, such as meetings | Do not infer organizational transformation from isolated task productivity; redesign processes, incentives, handoffs, and decision rights |

### Consolidated findings from the newer research

#### 1. Model readiness is not institutional readiness

A model can pass technical tests while the institution remains unable to deploy it. Approval pathways, procurement, data-sharing authority, operating procedures, workforce capacity, fiscal sustainability, legal mandates, and accountability arrangements must be assessed separately.

#### 2. AI readiness is a learning capability

Organizations need repeated cycles of experimentation, feedback, training, policy adaptation, workflow redesign, and operational learning. Purchasing a model or platform does not create this capability.

#### 3. Human–AI team performance is the deployment unit

High standalone model accuracy does not guarantee safe or effective decisions. Evaluation must examine:

- appropriate reliance when AI is correct;
- rejection or escalation when AI is wrong;
- recovery after errors;
- override and abstention behavior;
- learning over repeated use;
- workload and validation burden;
- preservation of professional judgment.

#### 4. Production incidents are part of the AI lifecycle

AI-specific incidents may involve unavailable services, degraded output quality, privacy exposure, unsafe responses, model or configuration changes, cost anomalies, and failures that are difficult to detect with conventional availability monitoring.

#### 5. Task productivity is not organizational transformation

AI can reduce effort in tasks that individuals control while leaving coordination-intensive activities unchanged. Real transformation requires process redesign, changes in roles and incentives, integration with systems of record, and revised decision authority.

#### 6. Validation capacity can become the bottleneck

AI may generate outputs faster than qualified people can validate them. Review effort, error detection, source verification, secure-code review, escalation, and accountability must be included in cost and capacity models.

#### 7. Responsible abandonment is a success capability

Stopping an unsuitable project can prevent greater financial, operational, security, legal, and societal harm. Governance should distinguish avoidable project failure from evidence-based non-development, pause, redesign, or retirement.

## Expanded failure model for 2025–2026

| Domain | Failure mode | Required evidence |
| --- | --- | --- |
| Strategic value | No durable problem, beneficiary, baseline, or measurable outcome | Problem statement, baseline, theory of value, benefit and harm metrics |
| Institutional alignment | The receiving organization lacks authority, processes, oversight, funding, or regulatory clarity | Approval map, operating model, fiscal plan, legal analysis, human-oversight capacity |
| Organizational learning | AI is purchased without training, experimentation, feedback, and workflow adaptation | Learning plan, champion network, feedback process, policy-change record |
| Data ecosystem | Data are unavailable, unreliable, ungoverned, semantically inconsistent, or insecure | Inventory, lineage, quality tests, provenance, lawful-use basis, integrity controls |
| Technology suitability | The use case exceeds current capabilities or requires certainty the model cannot provide | Baselines, feasibility tests, uncertainty and abstention analysis, limitation statement |
| Human–AI readiness | Users over-rely, under-rely, cannot detect errors, or face excessive review burden | Reliance metrics, interaction testing, workload analysis, escalation and override tests |
| Workflow integration | The model improves an isolated task but does not improve the end-to-end service | Process map, integration tests, handoff analysis, end-to-end outcome measurement |
| Production engineering | The prototype lacks secure deployment, monitoring, rollback, resilience, or incident response | Threat model, CI/CD evidence, observability, service objectives, recovery exercises |
| Security and governance | Access, data, tools, models, suppliers, and actions are not adequately controlled | Least privilege, supply-chain evidence, red-team results, audit logs, control mapping |
| Economics and continuity | Inference, validation, integration, maintenance, and staffing costs exceed realized value | Total lifecycle cost, cost per successful task, capacity plan, funding continuity |
| Stop and retirement discipline | Projects continue because of sunk costs, prestige, or mandate | Predefined stop criteria, independent review, pause authority, retirement plan |

## Additional anti-patterns

### Optimizing a proxy instead of the real outcome

A model metric is not automatically a business, mission, safety, or security metric. Accuracy, F1 score, benchmark position, or reward may improve while the operational outcome does not.

Maintain a traceable chain:

**Organizational objective → user decision or workflow → AI-supported function → model metric → operational metric → risk and control metric.**

### Treating AI as mandatory

The decision process should permit four valid outcomes:

1. Use AI.
2. Use AI only as decision support.
3. Use a deterministic or conventional software solution.
4. Do not automate the task.

### Assuming a prototype is nearly a product

A demonstration usually proves only that a model can produce a promising result under selected conditions. Production also requires dependable data ingestion, secure identity, versioning, evaluation, integration, monitoring, incident response, rollback, user training, institutional approval, and lifecycle ownership.

### Confusing access with adoption

Licensing an AI tool or making it available to employees does not demonstrate adoption, safe use, productivity, or value. Organizations need training, governance, workflow integration, support, objective measurement, and feedback mechanisms.

### Ignoring coordination costs

Time saved by one employee may be lost elsewhere through additional review, rework, meetings, approvals, security checks, or inconsistent outputs. End-to-end measurement is required.

## Why cybersecurity is a project-success requirement

Cybersecurity is often treated as a deployment gate added after model development. This approach can cause both security failure and project failure.

| Security issue discovered late | Project impact |
| --- | --- |
| Training or retrieval data cannot legally or securely be used | The model must be retrained or the use case abandoned |
| The model requires unrestricted network or tool access | Production approval is delayed or denied |
| Sensitive prompts and outputs are logged without adequate protection | Privacy, regulatory, and incident-response risk increases |
| Third-party models or dependencies lack provenance and integrity evidence | Supply-chain assurance becomes impossible |
| The system cannot reproduce or audit consequential actions | Operational and governance acceptance fails |
| No safe fallback, rollback, or human override exists | The system cannot meet resilience requirements |
| Prompt injection or indirect context manipulation changes tool behavior | The agent may perform unauthorized actions or disclose data |
| Output-quality degradation is not observable | Users receive incorrect results while conventional uptime metrics remain normal |
| Model, data, or behavior drift is not monitored | Performance and security assumptions silently expire |
| Validation capacity is inadequate | Unsafe or incorrect outputs accumulate faster than they can be reviewed |

Security by design reduces rework by making data classification, trust boundaries, identity, permissions, logging, isolation, human oversight, incident handling, and recovery part of the architecture from the beginning.

## AI project success lifecycle

### Gate 0: Problem and value definition

Required evidence:

- named business, mission, product, and risk owners;
- clearly defined user and operational workflow;
- baseline performance without AI;
- measurable benefit and harm criteria;
- comparison with non-AI alternatives;
- expected lifetime of the problem;
- initial legal, ethical, privacy, safety, and cybersecurity screening.

**Stop condition:** The problem is temporary, poorly defined, not valuable enough, or better solved without AI.

### Gate 1: Institutional alignment and organizational readiness

Required evidence:

- authority to deploy and operate the system;
- mapped approval, procurement, legal, and regulatory pathways;
- workforce, human-oversight, and training capacity;
- integration plan for existing processes and systems;
- funding for deployment, operation, validation, monitoring, and retirement;
- accountable decision rights and escalation routes;
- organizational-learning and feedback plan.

**Stop condition:** The institution cannot responsibly receive, fund, govern, or sustain the system.

### Gate 2: Data and knowledge readiness

Required evidence:

- data inventory and lineage;
- documented collection purpose and provenance;
- lawful authority, consent, license, and retention rules;
- quality, completeness, timeliness, and representativeness analysis;
- poisoning, tampering, and integrity controls;
- sensitivity classification and access restrictions;
- domain-expert review;
- plan for data updates and changing semantics.

**Stop condition:** Required data cannot be obtained, trusted, governed, or used responsibly.

### Gate 3: Feasibility and baseline evaluation

Required evidence:

- simple deterministic and statistical baselines;
- documented model-selection rationale;
- representative evaluation data separated from training data;
- uncertainty, calibration, abstention, and failure-mode analysis;
- initial red-team and abuse-case testing;
- cost, latency, compute, integration, and validation estimates;
- assessment of whether the technology is mature enough for the use case.

**Stop condition:** The AI approach does not materially outperform a simpler solution or cannot satisfy minimum risk and performance requirements.

### Gate 4: Human–AI and workflow readiness

Required evidence:

- realistic task and interaction testing;
- appropriate-reliance and error-recovery metrics;
- review-load and validation-capacity analysis;
- escalation, override, abstention, and fallback procedures;
- end-to-end workflow and coordination analysis;
- user training and affected-stakeholder feedback;
- protection against skill erosion and automation bias.

**Stop condition:** Users cannot interact with the system safely, or local task gains do not improve the end-to-end outcome.

### Gate 5: Production and security readiness

Required evidence:

- secure architecture and threat model;
- least-privilege identities and scoped credentials;
- model, dataset, prompt, policy, and dependency versioning;
- secure CI/CD and artifact-integrity verification;
- automated deployment, rollback, and fallback;
- logging, auditability, observability, and alerting;
- evaluation of prompt injection, leakage, model abuse, supply-chain compromise, and unauthorized tool use;
- incident-response and vulnerability-disclosure procedures;
- capacity, resilience, cost, privacy, validation, and service-quality testing.

**Stop condition:** The prototype cannot be operated, monitored, secured, validated, or recovered within acceptable risk.

### Gate 6: Controlled deployment

Required evidence:

- limited pilot population or environment;
- human review or approval proportionate to impact and autonomy;
- explicit user communication and training;
- canary release, shadow mode, or staged activation where practical;
- comparison against the pre-AI baseline;
- monitoring of operational value, security, safety, privacy, cost, reliance, and user burden;
- authority to pause or disable the system.

**Stop condition:** Operational value is not demonstrated, institutional readiness deteriorates, or harms and residual risks exceed approved tolerance.

### Gate 7: Continuous operation and assurance

Required evidence:

- data, concept, model, and behavior-drift monitoring;
- recurring security, safety, and human–AI evaluation;
- incident, near-miss, override, abstention, and error-recovery analysis;
- benefit-realization and total-cost tracking;
- periodic access and permission review;
- third-party model and dependency reassessment;
- retraining, revalidation, rollback, and retirement criteria;
- independent assurance for high-impact systems.

**Stop condition:** The system no longer provides sufficient value, cannot be maintained, or has accumulated unacceptable risk.

### Gate 8: Retirement

Required evidence:

- safe shutdown and replacement plan;
- revocation of credentials, tools, and service access;
- archival or deletion of data and model artifacts according to policy;
- preservation of required audit and incident evidence;
- communication to users and affected stakeholders;
- lessons-learned review.

## Mapping findings to NIST AI RMF

| Failure cause | GOVERN | MAP | MEASURE | MANAGE |
| --- | --- | --- | --- | --- |
| Wrong or misunderstood problem | Establish accountability and decision authority | Define context, users, intended purpose, and assumptions | Measure operational outcomes, not only model performance | Re-scope or stop when evidence does not support value |
| Institutional unreadiness | Define deployment, funding, oversight, and legal ownership | Map receiving processes, approvals, people, and dependencies | Assess readiness, capacity, and continuity | Limit to pilot, remediate readiness gaps, delay, or stop |
| Unsuitable data | Define data ownership and governance | Map sources, provenance, affected groups, and limitations | Test quality, integrity, privacy, and representativeness | Improve, restrict, replace, or reject the dataset |
| Weak organizational learning | Assign ownership for training and process adaptation | Map affected roles, incentives, and workflows | Measure adoption, learning, workload, and behavior | Redesign work, training, policies, and support |
| Human–AI unreadiness | Define oversight, override, and accountability | Map decisions, users, harms, and reliance risks | Measure calibration, recovery, workload, and safety signals | Adjust autonomy, interfaces, training, and escalation |
| Infrastructure underinvestment | Assign lifecycle and operational ownership | Map integration, supply chain, and deployment dependencies | Test reliability, security, resilience, and observability | Build shared infrastructure and recovery capability |
| Immature technology | Define risk tolerance and approval authority | Map technical limits and high-impact failure scenarios | Evaluate uncertainty, robustness, and adversarial behavior | Limit scope or autonomy, delay, replace, or terminate |
| Missing stop discipline | Establish independent review and pause authority | Identify sunk-cost, mandate, and reputational pressures | Compare evidence against predefined continuation criteria | Abandon, pause, redesign, or retire responsibly |

## Balanced AI project scorecard

| Dimension | Example measures |
| --- | --- |
| Mission or business value | time saved, loss reduced, revenue improved, mission effect, decision quality, task completion |
| Model quality | accuracy, precision, recall, calibration, robustness, abstention quality, subgroup performance |
| Institutional readiness | approval completion, legal clarity, oversight capacity, fiscal continuity, operational compatibility |
| Human–AI performance | appropriate reliance, error recovery, override quality, review burden, learning over time |
| Workflow performance | end-to-end cycle time, handoffs, rework, coordination burden, downstream effects |
| Operational performance | availability, latency, throughput, integration success, fallback rate, output-quality incidents |
| Security | injection resistance, leakage rate, unauthorized actions, privilege violations, remediation time |
| Safety and responsibility | harmful-output rate, near misses, fairness indicators, complaints, escalation quality |
| Data health | freshness, completeness, lineage coverage, integrity failures, drift indicators |
| Governance and assurance | evidence completeness, approval status, audit findings, control effectiveness, residual risk |
| Economics | development, inference, validation, integration, maintenance, and retirement costs |
| Adoption and learning | active use, training completion, policy compliance, feedback closure, capability maturity |

## Executive decision checklist

Before funding or continuing an AI project, leaders should be able to answer:

1. What enduring problem are we solving, for whom, and in which workflow?
2. Why is AI superior to a rule, search system, conventional application, process change, or human decision?
3. Who owns value, risk, data, the model, security, operations, organizational learning, and retirement?
4. What baseline and measurable success criteria will be used?
5. Is the receiving institution authorized, funded, staffed, and operationally ready?
6. Do we possess lawful, representative, timely, and trustworthy data?
7. What are the system's known limitations and required abstention conditions?
8. Can users rely on it appropriately and recover when it is wrong?
9. Does it improve the complete workflow rather than only one task?
10. What permissions, tools, data, and networks can the system access?
11. How will output quality, security, privacy, safety, drift, cost, validation burden, and benefit be monitored?
12. Who has authority to pause, roll back, abandon, or retire the system?
13. Under what conditions will the project be stopped rather than repeatedly extended?

## Early warning indicators

The following conditions indicate elevated failure risk:

- the project name contains a technology but no user problem;
- the sponsor cannot define the decision or workflow to be improved;
- no non-AI baseline is permitted;
- model accuracy is the only success metric;
- the receiving institution has no deployment or operating authority;
- data ownership and provenance are unknown;
- tool access is funded but training, governance, and validation are not;
- the prototype depends on manually prepared data or hidden analyst work;
- no production owner exists;
- deployment requires broad administrator, network, database, or tool access;
- users are expected to detect errors without time, training, or evidence;
- local productivity gains are reported without end-to-end measurement;
- priorities change faster than the team can complete data exploration and validation;
- the project repeatedly changes models without improving operational value;
- there is no budget for monitoring, incident response, validation, retraining, and retirement;
- stopping or abandoning the project is treated as organizational failure rather than responsible governance.

## Recommended organizational model

High-impact AI initiatives should use a multidisciplinary product and assurance team rather than an isolated data-science team.

| Role | Primary responsibility |
| --- | --- |
| Executive or mission sponsor | enduring objective, funding, risk acceptance, strategic alignment |
| Product or service owner | user need, workflow integration, benefit realization, prioritization |
| Institutional deployment owner | approvals, operational compatibility, fiscal continuity, receiving-unit readiness |
| Domain expert | real-world context, data meaning, edge cases, professional judgment |
| Data owner and steward | provenance, quality, access, lawful use, retention, lineage |
| Data and ML engineers | pipelines, model development, deployment, reproducibility, monitoring |
| Security architect and engineer | threat model, identity, access, isolation, supply chain, monitoring, response |
| Human-factors or UX specialist | reliance, workload, interaction design, error recovery, accessibility |
| Privacy, legal, ethics, and compliance specialists | rights, obligations, impact assessment, acceptable use |
| Independent evaluator or assurance function | validation independent from the development team |
| Operations and incident-response teams | runtime ownership, escalation, recovery, evidence preservation |
| User and affected-stakeholder representatives | usability, burden, trust, adverse impacts, feedback |

## Key conclusion

AI projects succeed when organizations treat them as governed socio-technical and institutional systems, not isolated model-development exercises. The central management question is not, "Which AI technology should we deploy?" It is:

> **Which enduring problem should be solved, what evidence will demonstrate value and acceptable risk, is the institution ready to receive the system, and what secure operational capability is required to sustain the result?**

The discipline to reject unsuitable use cases, select simpler solutions, delay unsafe deployment, abandon projects without sufficient evidence, or retire systems whose value has declined is a sign of AI maturity rather than failure.

## APA 7 references

Chappidi, S., & Singh, J. (2026). *To build or not to build? Factors that lead to non-development or abandonment of AI systems* [Preprint]. arXiv. https://doi.org/10.48550/arXiv.2604.28053

Dillon, E. W., Jaffe, S., Immorlica, N., & Stanton, C. T. (2025). *Shifting work patterns with generative AI* [Preprint]. arXiv. https://doi.org/10.48550/arXiv.2504.11436

Giray, G., Demirörs, O., Kalinowski, M., & Mendez, D. (2025). *An empirical study of generative AI adoption in software engineering* [Preprint]. arXiv. https://doi.org/10.48550/arXiv.2512.23327

Gurgul, V., Gubela, R., & Lessmann, S. (2026). *The state of generative AI in software development: Insights from literature and a developer survey* [Preprint]. arXiv. https://doi.org/10.48550/arXiv.2603.16975

Lee, M. H. (2026). *From accuracy to readiness: Metrics and benchmarks for human-AI decision-making* [Preprint]. arXiv. https://doi.org/10.48550/arXiv.2603.18895

Legara, E. F., Jose, E. D., & Martinez, P. J. (2026). *Beyond model readiness: Institutional readiness for AI deployment in public systems* [Preprint]. arXiv. https://doi.org/10.48550/arXiv.2605.17203

McClure, J., & Gerdau, G. (2026). *Why AI readiness is an organizational learning problem, not a technology purchase* [Preprint]. arXiv. https://doi.org/10.48550/arXiv.2604.16369

National Institute of Standards and Technology. (2023). *Artificial intelligence risk management framework (AI RMF 1.0)* (NIST AI 100-1). https://doi.org/10.6028/NIST.AI.100-1

Raji, I. D., Kumar, I. E., Horowitz, A., & Selbst, A. D. (2022). The fallacy of AI functionality. In *Proceedings of the 2022 ACM Conference on Fairness, Accountability, and Transparency* (pp. 959–972). Association for Computing Machinery. https://doi.org/10.1145/3531146.3533158

Ryseff, J., De Bruhl, B. F., & Newberry, S. J. (2024). *The root causes of failure for artificial intelligence projects and how they can succeed: Avoiding the anti-patterns of AI* (RR-A2680-1). RAND Corporation. https://doi.org/10.7249/RRA2680-1

Übellacker, T. (2025). *Making sense of AI limitations: How individual perceptions shape organizational readiness for AI adoption* [Preprint]. arXiv. https://doi.org/10.48550/arXiv.2502.15870

U.S. Government Accountability Office. (2021). *Artificial intelligence: An accountability framework for federal agencies and other entities* (GAO-21-519SP). https://www.gao.gov/products/gao-21-519sp

Yan, H., Chen, Y., Ma, M., Wen, M., Lu, S., Zhang, S., Xu, T., Wang, R., Bansal, C., Rajmohan, S., Zhang, C., & Zhang, D. (2025). *An empirical study of production incidents in generative AI cloud services* [Preprint]. arXiv. https://doi.org/10.48550/arXiv.2504.08865