---
title: "AI Risk Methodology"
author: Nachiket Sathaye
parent: "Risk Management"
nav_order: 1
document_type: AI Security Wiki Reference
version: 1.0
---

# AI Risk Methodology

> **Purpose:** Define the rating method for assessing AI risks consistently across AI platforms, custom AI applications and agentic AI workflows.

> **Audience:** Risk management, security architecture, GRC, audit, AI product owners.

## Risk Appetite and Criteria

The governing body approves an AI risk appetite statement (see the [AI Governance Operating Model](../08_Governance/16_AI_Governance_Operating_Model.md)). It sets, for each rating on the risk scale below, who may accept the residual risk and how long an acceptance lasts. Record the statement, its approval date and its review date with the risk register. The ratings on this page are the risk criteria; change them only through the same approval.

## Rating Factors

| Factor | Definition |
|---|---|
| Likelihood | Probability of the risk occurring based on exposure, adoption, control maturity and user behavior. |
| Impact | Consequence to confidentiality, integrity, availability, compliance, operational continuity, reputation or critical infrastructure. |
| Existing Control Coverage | Current ability of existing controls to prevent, detect, respond or provide evidence. |
| Residual Risk | Remaining risk after considering current control coverage. |
| Additional Control Requirement | Whether AI-specific controls, governance, monitoring or enforcement are required. |

## Risk Scale

| Rating | Definition |
|---|---|
| Low | Limited likelihood or business impact; existing controls generally sufficient. |
| Medium | Possible risk affecting sensitive information, compliance or business processes; monitoring or governance may be required. |
| High | Likely or significant impact; additional controls, monitoring or enforcement required. |
| Critical | May affect critical infrastructure, restricted data, regulatory obligations or operational continuity; strong preventive and detective controls required. |

## Required Fields for New AI Risk Entry

```markdown
Risk ID:
Risk Name:
AI Channel:
Risk Description:
Example Scenarios:
Potential Impact:
Existing Controls:
Likelihood:
Impact:
Existing Control Coverage:
Residual Risk:
Required AI Security Capabilities:
Evidence Required:
Risk Owner:
Treatment Decision:
Review Date:
```

## Communication and Consultation

At each stage, consult the people who can inform the assessment or are affected by the result: the business owner, data owner, security architecture, privacy, legal, the teams who operate the system and, for systems that affect people, representatives of the people affected. Record who was consulted and what changed as a result in the risk entry's notes. Report the outcome to the risk owner and, for High and Critical risks, to the AI Governance Committee.

## Review Triggers

- New AI vendor onboarding.
- New AI integration with enterprise data.
- AI coding assistant adoption.
- New RAG or custom AI application.
- Agentic AI workflow or tool-calling capability.
- Regulatory, audit or third-party risk review.
- A change to the system's purpose, users, deployment region or languages, or its data sources (these also trigger a review of its impact assessment, [AI-CTRL-042](../03_Control_Library/03_AI_Security_Control_Objectives_Library.md#ai-ctrl-042)).
- A material incident, or monitoring that shows the system operating outside its validated boundaries.

## Alignment with ISO/IEC 23894

ISO/IEC 23894:2023 gives guidance on AI risk management and follows the ISO 31000 process. The table shows where each step of its clause 6 process is carried out in this wiki. Clause numbers and headings were checked against the publisher's contents preview on 15 October 2026; the clause text was not read.

| ISO/IEC 23894 clause | Wiki page |
|---|---|
| 6.2 Communication and consultation | Communication and Consultation, above |
| 6.3 Scope, context and criteria | Risk Appetite and Criteria, and Risk Scale, above; [AI Use-Case Risk Triage](02F_AI_Use_Case_Risk_Triage.md) |
| 6.4.2 Risk identification | [AI Use-Case Risk Triage](02F_AI_Use_Case_Risk_Triage.md); [Enterprise AI Risk Register](02B_Enterprise_AI_Risk_Register.md) |
| 6.4.3 Risk analysis and 6.4.4 Risk evaluation | Rating Factors and Risk Scale, above |
| 6.5 Risk treatment | [AI Risk Treatment Plan](02C_AI_Risk_Treatment_Plan.md); [AI Risk to Control Mapping](02D_AI_Risk_to_Control_Mapping.md) |
| 6.6 Monitoring and review | Review Triggers, above; [AI Risk Review Template](02E_AI_Risk_Review_Template.md) |
| 6.7 Recording and reporting | Required Fields for New AI Risk Entry, above; [Risk, Control and Test Traceability](02G_Risk_Control_Test_Traceability.md) |

NIST publishes a crosswalk from ISO/IEC 23894 to the NIST AI RMF, so this table can be read together with the [NIST AI RMF Crosswalk](../23_Framework_Crosswalks/03_NIST_AI_RMF_Crosswalk.md). See also the [ISO/IEC AI Standards Crosswalk](../23_Framework_Crosswalks/15_ISO_IEC_AI_Standards_Crosswalk.md).
