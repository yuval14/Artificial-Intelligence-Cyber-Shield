# AI Red Team Frameworks

This page lists selected AI red teaming frameworks, benchmarks, guides, and tooling that can support adversarial testing of AI systems, large language models, AI agents, and machine-learning pipelines.

> Note: "Open source" means that a usable framework, benchmark, guide, or tool is publicly available under an open or source-available license. Some frontier-model safety frameworks are public documents but not open-source software.

| # | Vendor / Organization | Framework / Tool Name | Goal / Function | Initial Release Date | Open Source / Public | Primary Use Case | Link |
|---:|---|---|---|---|---|---|---|
| 1 | OWASP | OWASP AI Red Teaming Guide | Practical methodology for planning and executing AI red team engagements across model, application, and operational layers. | 2025 | Yes | AI application red teaming methodology | [OWASP AI Red Teaming Guide](https://owasp.org/www-project-ai-red-teaming-guide/) |
| 2 | OWASP | OWASP Top 10 for LLM Applications | Common LLM application risks used as a threat checklist for red team scenarios and control validation. | 2023; updated 2025 | Yes | LLM threat modeling and testing | [OWASP Top 10 for LLM Applications](https://genai.owasp.org/) |
| 3 | MITRE | MITRE ATLAS | Adversarial threat landscape and technique catalog for AI-enabled systems, modeled in a way similar to ATT&CK. | 2020 | Yes | AI attack technique mapping | [MITRE ATLAS](https://atlas.mitre.org/) |
| 4 | NIST | AI Risk Management Framework and AI RMF Playbook | Risk management structure for mapping, measuring, managing, and governing AI risks, including evaluation and red teaming activities. | January 2023 | Yes | Governance and risk-based AI assessment | [NIST AI RMF](https://www.nist.gov/itl/ai-risk-management-framework) |
| 5 | Microsoft | PyRIT | Automation framework for red teaming generative AI systems, including prompt attacks, scoring, orchestration, and repeatable testing. | February 2024 | Yes | Automated LLM red teaming | [PyRIT](https://github.com/Azure/PyRIT) |
| 6 | Microsoft | AI Red Teaming Guidance | Enterprise guidance for scoping, running, and reporting AI red team operations. | 2024 | Public guidance | Enterprise AI security testing | [Microsoft AI Red Teaming](https://learn.microsoft.com/en-us/azure/ai-foundry/concepts/ai-red-teaming) |
| 7 | Microsoft | Counterfit | Command-line automation framework for assessing machine-learning models using adversarial attacks. | 2021 | Yes | Adversarial ML testing | [Counterfit](https://github.com/Azure/counterfit) |
| 8 | NVIDIA | garak | LLM vulnerability scanner for probing prompt injection, jailbreaks, hallucination, data leakage, and other generative AI risks. | June 2023 | Yes | LLM vulnerability scanning | [garak](https://github.com/NVIDIA/garak) |
| 9 | UK AI Security Institute | Inspect | Open-source framework for large language model evaluations, including capabilities, safety, and autonomy-oriented tasks. | May 2024 | Yes | Model evaluation and safety testing | [Inspect](https://inspect.aisi.org.uk/) |
| 10 | Meta | Purple Llama | Trust and safety umbrella project for open tools and evaluations supporting responsible generative AI deployment. | December 2023 | Yes / source available | Generative AI security and safety evaluation | [Purple Llama](https://github.com/meta-llama/PurpleLlama) |
| 11 | Meta | CyberSecEval | Benchmark suite for evaluating cybersecurity capabilities and risks in LLMs. | December 2023 | Yes | Cyber capability and misuse evaluation | [CyberSecEval](https://github.com/meta-llama/PurpleLlama/tree/main/CybersecurityBenchmarks) |
| 12 | MLCommons | AILuminate | AI risk and reliability benchmark for evaluating model behavior across hazardous content categories. | v0.5 April 2024; v1.0 2025 | Yes | AI safety benchmarking | [AILuminate](https://mlcommons.org/ailuminate/) |
| 13 | IBM | Adversarial Robustness Toolbox | Python library for adversarial machine learning attacks, defenses, robustness testing, and model hardening. | July 2018 | Yes | Classical adversarial ML robustness testing | [IBM ART](https://github.com/Trusted-AI/adversarial-robustness-toolbox) |
| 14 | Google | Secure AI Framework | Security framework for protecting AI systems using secure-by-design, detection, response, and supply-chain security principles. | June 2023 | Public guidance | Secure AI engineering and governance | [Google SAIF](https://saif.google/) |
| 15 | Google DeepMind | Frontier Safety Framework | Framework for identifying, evaluating, and managing severe risks from frontier AI models. | 2024; updated 2025 | Public document | Frontier model risk evaluation | [Frontier Safety Framework](https://deepmind.google/discover/blog/introducing-the-frontier-safety-framework/) |
| 16 | OpenAI | Preparedness Framework | Framework for tracking, evaluating, and governing frontier model risks such as cybersecurity, biological, persuasion, and autonomy risks. | December 2023; updated 2025 | Public document | Frontier model risk evaluation | [OpenAI Preparedness Framework](https://openai.com/safety/preparedness/) |
| 17 | Anthropic | Responsible Scaling Policy | Frontier AI risk management policy using capability thresholds, safeguards, and safety levels. | September 2023; updated 2026 | Public document | Frontier model scaling governance | [Anthropic Responsible Scaling Policy](https://www.anthropic.com/responsible-scaling-policy) |
| 18 | Stanford CRFM | HELM | Holistic Evaluation of Language Models, including accuracy, robustness, fairness, bias, toxicity, efficiency, and transparency dimensions. | 2022 | Yes | Broad model evaluation benchmark | [HELM](https://crfm.stanford.edu/helm/) |
| 19 | Giskard | Giskard LLM Scan | Open-source LLM vulnerability scanner for prompt injection, harmful content, sensitive data disclosure, and model behavior issues. | 2023 | Yes | LLM application testing | [Giskard](https://github.com/Giskard-AI/giskard) |
| 20 | Lakera | Gandalf | Interactive prompt-injection and jailbreak challenge used for awareness, training, and informal red team practice. | 2023 | Public challenge | Prompt injection training | [Gandalf](https://gandalf.lakera.ai/) |
| 21 | Cloud Security Alliance | Agentic AI Red Teaming Guide | Guidance for red teaming agentic AI systems, including autonomy, tool use, identity, and multi-step risk scenarios. | 2025 | Public guidance | Agentic AI red teaming | [CSA AI Safety Initiative](https://cloudsecurityalliance.org/research/working-groups/ai-safety-initiative) |
| 22 | Beijing AI Safety Institute | ForesightSafety Bench | Frontier risk evaluation benchmark covering broad safety pillars, agentic autonomy, AI4Science, embodied AI, and catastrophic risk dimensions. | 2026 | Yes | Frontier AI safety evaluation | [ForesightSafety Bench](https://github.com/Beijing-AISI/ForesightSafety-Bench) |
| 23 | AI-Infra-Guard authors | AI-Infra-Guard | Multi-layer agent red teaming framework covering infrastructure, MCP/tool layers, agent behavior, and model-layer jailbreak testing. | 2026 | Yes | AI agent and MCP security red teaming | [AI-Infra-Guard paper](https://arxiv.org/abs/2606.31227) |

## Suggested Use

For a practical AI red team program, combine several layers rather than relying on one framework:

1. **Governance baseline:** NIST AI RMF, Google SAIF, OpenAI Preparedness Framework, Anthropic Responsible Scaling Policy.
2. **Threat taxonomy:** MITRE ATLAS, OWASP Top 10 for LLM Applications, OWASP AI Red Teaming Guide.
3. **Automated testing:** PyRIT, garak, Giskard, Inspect, CyberSecEval.
4. **Adversarial ML robustness:** IBM ART and Microsoft Counterfit.
5. **Agentic AI security:** CSA Agentic AI Red Teaming Guide, AI-Infra-Guard, and agent-specific test harnesses.

## APA 7 References

Alaga, J., Schuett, J., & Anderljung, M. (2024). *A grading rubric for AI safety frameworks*. arXiv. https://arxiv.org/abs/2409.08751

Derczynski, L., Galinkin, E., Martin, J., Majumdar, S., & Inie, N. (2024). *garak: A framework for security probing large language models*. arXiv. https://arxiv.org/abs/2406.11036

MLCommons AI Safety Working Group. (2025). *AILuminate: Introducing v1.0 of the AI risk and reliability benchmark from MLCommons*. arXiv. https://arxiv.org/abs/2503.05731

MITRE. (n.d.). *MITRE ATLAS: Adversarial threat landscape for artificial-intelligence systems*. https://atlas.mitre.org/

National Institute of Standards and Technology. (2023). *Artificial intelligence risk management framework (AI RMF 1.0)*. U.S. Department of Commerce. https://doi.org/10.6028/NIST.AI.100-1

Nicolae, M.-I., Sinn, M., Tran, M. N., Buesser, B., Rawat, A., Wistuba, M., Zantedeschi, V., Baracaldo, N., Chen, B., Ludwig, H., Molloy, I. M., & Edwards, B. (2018). *Adversarial robustness toolbox v1.0.0*. arXiv. https://arxiv.org/abs/1807.01069

Open Worldwide Application Security Project. (2025). *OWASP Top 10 for large language model applications*. https://genai.owasp.org/

OpenAI. (2023). *Preparedness framework*. https://openai.com/safety/preparedness/

Yang, Y., Zheng, X., Wu, H., Cheng, H., Shi, X., Guo, J., Yang, B., Zhou, Y., Wu, X., & Ying, Z. (2026). *Securing the AI agent: A unified framework for multi-layer agent red teaming*. arXiv. https://arxiv.org/abs/2606.31227
