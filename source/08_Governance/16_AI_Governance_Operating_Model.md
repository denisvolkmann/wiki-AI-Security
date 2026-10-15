---
title: "AI Governance Operating Model"
author: Denis Volkmann
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
| AI Platform Owner | Run the shared AI platform: the model gateway and allow-list, embedding services, vector stores, agent memory services and tracing tools. Keep their inventories current and apply approved changes. |
| Agent Sponsor | Answer for one agent: its purpose, the tools and systems it may use, its recertification and its retirement. Every agent has exactly one named sponsor. |

## Component Ownership

Each part of an AI application stack needs a person who answers for it. The table below names the accountable role for nine components that teams commonly build with, the decision that role owns, and the test cases that check the decision is recorded and enforced. It is one workable allocation, not a requirement of any standard: rename the roles to match your organization, but keep one accountable role per row.

| Component | Ownership question | Accountable | Consulted | Tested by |
|---|---|---|---|---|
| Models | Who decides which models are approved for use? | AI Governance Committee for models used in high-risk use cases; AI Platform Owner for all others, under the tier rules in the [AI Risk Methodology](../02_Risk_Management/02A_AI_Risk_Methodology.md) | Security Architecture, Procurement / Legal, Data Protection | [TC-L12-025](../10_Test_Case_Library/L12-model-layer.md#tc-l12-025), [TC-L12-032](../10_Test_Case_Library/L12-model-layer.md#tc-l12-032), [TC-L08-028](../10_Test_Case_Library/L08-ai-gateway-and-security-controls.md#tc-l08-028) |
| Agents | Who defines what an agent is allowed to do? | Agent Sponsor, within the purpose approved for the use case | AI Product Owner, Security Architecture (Gate 4) | [TC-D09-002](../10_Test_Case_Library/D09-agent-and-non-human-identity-governance.md#tc-d09-002), [TC-D09-003](../10_Test_Case_Library/D09-agent-and-non-human-identity-governance.md#tc-d09-003), [TC-L06-013](../10_Test_Case_Library/L06-agent-orchestration-layer.md#tc-l06-013), [TC-L06-034](../10_Test_Case_Library/L06-agent-orchestration-layer.md#tc-l06-034) |
| Embeddings | Who determines what data gets embedded? | Data Owner of each source decides what is embedded; AI Platform Owner approves the embedding model and provider | Data Protection, Procurement / Legal | [TC-L11-015](../10_Test_Case_Library/L11-knowledge-and-retrieval-layer.md#tc-l11-015), [TC-L11-026](../10_Test_Case_Library/L11-knowledge-and-retrieval-layer.md#tc-l11-026), [TC-L11-027](../10_Test_Case_Library/L11-knowledge-and-retrieval-layer.md#tc-l11-027) |
| Retrieval (RAG) | Who owns the documents behind it? | Data Owner of each knowledge source | AI Product Owner | [TC-L11-001](../10_Test_Case_Library/L11-knowledge-and-retrieval-layer.md#tc-l11-001), [TC-L11-010](../10_Test_Case_Library/L11-knowledge-and-retrieval-layer.md#tc-l11-010), [TC-L10-032](../10_Test_Case_Library/L10-data-layer.md#tc-l10-032) |
| Guardrails | Who defines and enforces the guardrails? | Security Architecture defines security and data rules, and the AI Product Owner defines topic and scope rules; the AI Platform Owner enforces them | GRC / Compliance, Data Protection | [TC-L08-043](../10_Test_Case_Library/L08-ai-gateway-and-security-controls.md#tc-l08-043), [TC-L08-036](../10_Test_Case_Library/L08-ai-gateway-and-security-controls.md#tc-l08-036), [TC-L08-039](../10_Test_Case_Library/L08-ai-gateway-and-security-controls.md#tc-l08-039) |
| Tools and MCP servers | Who grants access to which systems? | Owner of the target system, together with the Agent Sponsor | Identity and access management, Security Architecture | [TC-L06-047](../10_Test_Case_Library/L06-agent-orchestration-layer.md#tc-l06-047), [TC-L06-006](../10_Test_Case_Library/L06-agent-orchestration-layer.md#tc-l06-006), [TC-L09-005](../10_Test_Case_Library/L09-identity-and-access-mgmt.md#tc-l09-005), [TC-D09-005](../10_Test_Case_Library/D09-agent-and-non-human-identity-governance.md#tc-d09-005) |
| Observability | Who investigates failures and reviews what went wrong? | SOC for security incidents; AI Product Owner for quality failures (wrong answers, wrong tool choices, regressions); AI Platform Owner for the tracing tools themselves | Data Protection | [TC-L17-032](../10_Test_Case_Library/L17-monitoring-detection-and-response.md#tc-l17-032), [TC-L17-033](../10_Test_Case_Library/L17-monitoring-detection-and-response.md#tc-l17-033), [TC-D12-020](../10_Test_Case_Library/D12-ai-incident-response-and-forensics.md#tc-d12-020) |
| Vector databases | Who controls what data gets indexed? | Data Owner approves each index or collection and its scope; AI Platform Owner runs the store | Data Protection, Security Architecture | [TC-L11-028](../10_Test_Case_Library/L11-knowledge-and-retrieval-layer.md#tc-l11-028), [TC-L11-004](../10_Test_Case_Library/L11-knowledge-and-retrieval-layer.md#tc-l11-004), [TC-L11-007](../10_Test_Case_Library/L11-knowledge-and-retrieval-layer.md#tc-l11-007), [TC-L10-021](../10_Test_Case_Library/L10-data-layer.md#tc-l10-021) |
| Agent memory | Who is accountable for what it remembers? | AI Product Owner of the assistant or agent that writes the memory | Data Protection sets what may be remembered and handles access and erasure requests | [TC-L07-042](../10_Test_Case_Library/L07-prompt-and-context-layer.md#tc-l07-042), [TC-L07-043](../10_Test_Case_Library/L07-prompt-and-context-layer.md#tc-l07-043), [TC-L07-044](../10_Test_Case_Library/L07-prompt-and-context-layer.md#tc-l07-044), [TC-L07-045](../10_Test_Case_Library/L07-prompt-and-context-layer.md#tc-l07-045), [TC-L07-028](../10_Test_Case_Library/L07-prompt-and-context-layer.md#tc-l07-028) |

Record the accountable person for each live component in the use-case registry or the relevant inventory. A component without a named owner should not pass Gate 6.

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
- AI components without a named owner (models, agents, indexes, memory stores, tool grants).
- Open AI risks and exceptions.
- Vendor sovereignty validations completed.
- SOC alerts and incidents related to AI usage.

## Standards Basis

The governing body layer, the reserved decisions and the board-level reporting above follow the structure of ISO/IEC 38507:2022 (Governance implications of the use of artificial intelligence by organizations): clause 4.3 on maintaining accountability when introducing AI, and clause 6 on policies for governance oversight (6.2), decision-making (6.3), data use (6.4), culture and values (6.5), compliance (6.6) and risk appetite and management (6.7). The data owner row and the data quality metric follow ISO/IEC 5259-5:2025, clauses 7 and 8 (responsibilities of the governing body and of management for data quality). Clause numbers and headings were checked against the publishers' contents previews on 15 October 2026; the clause text was not read. See the [ISO/IEC AI Standards Crosswalk](../23_Framework_Crosswalks/15_ISO_IEC_AI_Standards_Crosswalk.md).

