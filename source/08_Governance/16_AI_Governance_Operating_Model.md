---
title: "AI Governance Operating Model"
author: Nachiket Sathaye
parent: "Governance"
nav_order: 1
document_type: AI Security Wiki Reference
version: 1.0
---

# AI Governance Operating Model

> **Purpose:** Define ownership, gates, workflow, reporting and continuous governance for AI adoption.

> **Audience:** Governance, compliance, security leadership, architecture review boards, AI steering committee.

| Gate | Applies To | Required Review |
|---|---|---|
| Gate 1 | Any AI tool | AI usage and data handling review |
| Gate 2 | AI with sensitive data | DLP, classification and data protection review |
| Gate 3 | Custom AI application | AppSec, prompt injection and runtime review |
| Gate 4 | Agentic AI | Tool, API, approval workflow and privilege review |
| Gate 5 | Vendor AI platform | Sovereignty, third-party processing and procurement review |
| Gate 6 | Production AI | Audit logging, SOC integration and evidence readiness review |

## Governance Bodies

| Function | Responsibility |
|---|---|
| Governing body (board, or its risk or audit committee) | Set the organization's AI risk appetite, approve the categories of AI use that are prohibited or high-risk, and oversee AI risk, compliance and data quality through regular reporting. Accountability stays with the governing body when decisions are automated. |
| Accountable executive | Own AI governance on behalf of the governing body, chair or sponsor the AI governance committee, and report AI risk, incidents and exceptions upward. |
| AI Governance Committee | Approve high-risk use cases, risk acceptances and exceptions; review impact assessments; track maturity against this operating model. |
| Data Owner (AI datasets) | Own the quality, provenance and permitted use of each dataset used to train, fine-tune or ground an AI system, and approve its data quality thresholds. |
| AI Product Owner | Define use case, data scope and business justification. |
| Security Architecture | Review AI design, controls, integrations and residual risk. |
| GRC / Compliance | Validate policy, regulatory, audit and sovereignty requirements. |
| Data Protection / DLP | Validate data classification and leakage controls. |
| AppSec / DevSecOps | Validate custom AI application and AI-assisted development controls. |
| SOC | Validate alerting, logging, investigation and monitoring. |
| Procurement / Legal | Validate vendor terms, data processing, residency and contractual controls. |

## Decisions Reserved for the Governing Body

The governing body should not delegate these decisions, even where it delegates the work behind them:

- The AI risk appetite statement and the risk criteria used in the [AI Risk Methodology](../02_Risk_Management/02A_AI_Risk_Methodology.md).
- The categories of AI use that are prohibited, and the categories that always count as high-risk.
- Acceptance of residual risk rated Critical for an AI use case.
- The AI policy and its scope ([AI Policy, Standards and Acceptable Use](17_AI_Policy_Standards_and_Acceptable_Use.md)).
- The level of human oversight required where AI makes or supports decisions about people.

## Board-Level Reporting

Report these to the governing body at least each quarter:

- Number of AI use cases by risk tier, and how many are high-risk or use sensitive data.
- Critical and high AI risks open past their treatment date.
- Exceptions past their expiry date.
- Material AI incidents and near misses, with root causes.
- Impact assessments overdue for review.
- Datasets in use below their approved data quality thresholds.
- Status of AI regulatory obligations and authority engagement.

## Continuous Governance Metrics

- Number of approved AI tools.
- Number of unapproved AI tools detected.
- AI prompt/file policy violations.
- AI coding assistant usage and detections.
- Custom AI apps reviewed.
- Agentic AI workflows approved.
- Open AI risks and exceptions.
- Vendor sovereignty validations completed.
- SOC alerts and incidents related to AI usage.

## Standards Basis

The governing body layer, the reserved decisions and the board-level reporting above follow the structure of ISO/IEC 38507:2022 (Governance implications of the use of artificial intelligence by organizations): clause 4.3 on maintaining accountability when introducing AI, and clause 6 on policies for governance oversight (6.2), decision-making (6.3), data use (6.4), culture and values (6.5), compliance (6.6) and risk appetite and management (6.7). The data owner row and the data quality metric follow ISO/IEC 5259-5:2025, clauses 7 and 8 (responsibilities of the governing body and of management for data quality). Clause numbers and headings were checked against the publishers' contents previews on 15 October 2026; the clause text was not read. See the [ISO/IEC AI Standards Crosswalk](../23_Framework_Crosswalks/15_ISO_IEC_AI_Standards_Crosswalk.md).

