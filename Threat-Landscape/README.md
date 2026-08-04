# AI Threat Landscape

This section tracks security threats created or materially changed by artificial intelligence, including adversarial model use, AI-assisted cyber operations, agentic workflows, runtime AI integration, identity deception, supply-chain exposure, and abuse of trusted AI infrastructure.

## Current Research

- [Covert Use of AI in Offensive Cyber Operations](Covert-Use-of-AI-in-Offensive-Cyber-Operations.md)

## Related Repositories

### Detection Engineering

The technical framework, case studies, correlation logic, and Sigma rules are maintained in:

`https://github.com/yuval14/Cybersecurity-Detection-Engineering/tree/main/AIDAF-Adversarial-AI-Detection-and-Assessment-Framework`

### Operational Workbook

The detection and threat-hunting workbook is maintained in:

`https://github.com/yuval14/AI-Security-Tooling/tree/main/AI_Enabled_Threat_Detection_and_Hunting_Workbook`

## Scope

This section distinguishes between:

1. Attacks against AI systems.
2. Use of AI to conduct attacks against conventional systems.
3. Compromise of AI tools, agents, integrations, and supply chains as an initial-access or post-compromise path.
4. AI-supported identity deception, fraud, and persistent legitimate access.
5. Defensive implications for CISO, SOC, CTI, DFIR, detection engineering, and national cyber resilience.

## Analytic Principle

AI involvement should be reported with evidence and confidence. Speed, sophistication, code quality, variation, and multilingual content are not proof of AI use. Direct runtime artifacts, provider records, recovered prompts, agent traces, model credentials, tool calls, and correlated system effects provide stronger evidence.