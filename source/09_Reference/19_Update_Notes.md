---
title: "Update Notes"
author: Nachiket Sathaye
parent: "Reference"
nav_order: 2
description: "What changed in the wiki and when, starting with the 15 October 2026 updates on AI governance frameworks and component ownership, with what was verified and what is still work in progress."
document_type: AI Security Wiki Reference
version: 1.0
last_reviewed: 2026-10-15
---

# Update Notes

This page records each substantial update to the wiki, newest first, with what was checked and what is still work in progress. The full version history is in [section 20 of the home page](../index.md#20-version-history).

## 15 October 2026: component ownership

This update compared the wiki's 17 layers with a nine-part list of AI application stack components: LLMs, agents, embeddings, RAG, AI security, MCP and tools, observability, vector databases and memory. Each part came with an ownership question, such as "who decides which models are approved for use?". The original source of that list was not verified. Every part already had a home in the 17 layers, but the wiki answered only two of the nine ownership questions in full. Agent memory had no owner at all, and observability covered security incidents but not quality failures.

### What is new

- **Component ownership:** the [AI Governance Operating Model](../08_Governance/16_AI_Governance_Operating_Model.md#component-ownership) now has a table that names the accountable role for each of the nine components, the roles to consult, and the test cases that check each decision. Two roles were added: AI Platform Owner and Agent Sponsor. The table is one workable allocation, not a requirement of any standard.
- **Agent memory:** four new cases, [TC-L07-042](../10_Test_Case_Library/L07-prompt-and-context-layer.md#tc-l07-042) to [TC-L07-045](../10_Test_Case_Library/L07-prompt-and-context-layer.md#tc-l07-045), cover a memory store inventory with owners, a policy on what may be remembered, user visibility and control, and memory in data subject access and erasure requests. [AI-CTRL-026](../03_Control_Library/03_AI_Security_Control_Objectives_Library.md#ai-ctrl-026) now asks for all four.
- **Embeddings and vector databases:** [TC-L11-026](../10_Test_Case_Library/L11-knowledge-and-retrieval-layer.md#tc-l11-026) to [TC-L11-028](../10_Test_Case_Library/L11-knowledge-and-retrieval-layer.md#tc-l11-028) cover approval of embedding models, content sent to external embedding providers, and approval and ownership of new indexes and collections.
- **Approval records:** [TC-L12-032](../10_Test_Case_Library/L12-model-layer.md#tc-l12-032) checks that each approved model has a decision record with a named approver, [TC-L08-043](../10_Test_Case_Library/L08-ai-gateway-and-security-controls.md#tc-l08-043) that each guardrail policy has an owner and approved changes, and [TC-L06-047](../10_Test_Case_Library/L06-agent-orchestration-layer.md#tc-l06-047) that each tool or system grant to an agent is approved by the system owner and the agent's sponsor.
- **Observability:** [TC-L17-032](../10_Test_Case_Library/L17-monitoring-detection-and-response.md#tc-l17-032) covers access, masking, retention and residency of AI tracing and evaluation tools, and [TC-L17-033](../10_Test_Case_Library/L17-monitoring-detection-and-response.md#tc-l17-033) covers ownership and review of AI failures that are not security incidents.
- The library now holds 668 cases: 535 in the 17 layers and 133 in the six emerging domains.

### What is still work in progress

- The OWASP and NIST AI RMF mappings on the new cases reuse identifiers already used elsewhere in the library. Like all mappings in the library, check them against the current published versions before relying on them.
- The thresholds in the new cases are starting values to tune, as for every case in the library.
- The layer-to-domain coverage matrix in the [Reference Index](../10_Test_Case_Library/00-reference-index.md) was not changed.

## 15 October 2026: AI governance frameworks

This update compared the wiki against a widely shared list of 30 AI governance frameworks and standards, and filled the gaps it found. Before it, the wiki mapped 10 of the 30 in depth, cited 2 without mapping them, and did not name the other 18.

### What is new

- **Four new crosswalk pages**, bringing the Framework Crosswalks section to 17 pages:
  - [NIST AI 100-2 Crosswalk](../23_Framework_Crosswalks/14_NIST_AI_100_2_Crosswalk.md): every NISTAML attack class identifier mapped to controls and test case layers.
  - [ISO/IEC AI Standards Crosswalk](../23_Framework_Crosswalks/15_ISO_IEC_AI_Standards_Crosswalk.md): ISO/IEC 38507, 42005, 42006, 23894, TR 24028, 5338, 23053, 22989 and the 5259 data quality series, clause by clause.
  - [Trustworthy AI and Ethics Standards Crosswalk](../23_Framework_Crosswalks/16_Trustworthy_AI_Ethics_Crosswalk.md): the EU Ethics Guidelines for Trustworthy AI, the UNESCO Recommendation on the Ethics of AI, and IEEE 7000, 7001, 7002, 7003 and 7010.
  - [International AI Instruments Crosswalk](../23_Framework_Crosswalks/17_International_AI_Instruments_Crosswalk.md): the Council of Europe Framework Convention on AI and the G7 Hiroshima Process Code of Conduct.
- **Board-level governance** (ISO/IEC 38507): the [AI Governance Operating Model](../08_Governance/16_AI_Governance_Operating_Model.md) now has a governing body, an accountable executive and a data owner for AI datasets, decisions reserved for the board, and board-level reporting.
- **Risk management** (ISO/IEC 23894): the [AI Risk Methodology](../02_Risk_Management/02A_AI_Risk_Methodology.md) now has a risk appetite statement, a communication and consultation step, more review triggers, and a table aligning each step of the ISO/IEC 23894 process with a wiki page.
- **Impact assessment** (ISO/IEC 42005): [AI-CTRL-042](../03_Control_Library/03_AI_Security_Control_Objectives_Library.md#ai-ctrl-042) now asks for unintended uses and misuse, deployment regions and languages, data quality, and benefits as well as harms. The [AI Use-Case Risk Triage](../02_Risk_Management/02F_AI_Use_Case_Risk_Triage.md) now says which answers trigger a full impact assessment.
- **Certification readiness** (ISO/IEC 42006): the [AI Security Audit and Evidence Checklist](../06_Testing_and_Assurance/14_AI_Security_Audit_and_Evidence_Checklist.md) explains what an ISO/IEC 42001 certification audit will look for. The [Vendor Evaluation Master Framework](../05_Vendor_Evaluation/11_AI_Security_Vendor_Evaluation_Master_Framework.md) asks for the scope of a supplier's certificate.
- **Data quality** (ISO/IEC 5259): [AI-CTRL-029](../03_Control_Library/03_AI_Security_Control_Objectives_Library.md#ai-ctrl-029) now requires a data quality profile with measured thresholds for each dataset, and [AI-CTRL-019](../03_Control_Library/03_AI_Security_Control_Objectives_Library.md#ai-ctrl-019) adds quality measures for retrieval corpora. Three new test cases, [TC-L10-031](../10_Test_Case_Library/L10-data-layer.md#tc-l10-031) to [TC-L10-033](../10_Test_Case_Library/L10-data-layer.md#tc-l10-033), test them. The library now holds 656 cases.
- **Bias** (IEEE 7003): [AI-CTRL-041](../03_Control_Library/03_AI_Security_Control_Objectives_Library.md#ai-ctrl-041) and the [GCC T10 Bias Testing Record](../11_GCC_AI_Compliance/T10_Bias_Testing_Record.md) now keep a versioned bias profile with the system's validated application boundaries.
- **Terminology** (ISO/IEC 22989): the [glossary](../09_Reference/18_AI_Security_Glossary_and_Taxonomy.md#standard-vocabulary) maps the standard's six AI stakeholder roles to the roles used in the wiki and the EU AI Act.
- **Advanced AI suppliers** (G7 Hiroshima Code): the [EU T12 GPAI Model Checklist](../12_EU_AI_Compliance/T12_GPAI_Model_Checklist.md) asks for a supplier's Hiroshima reporting framework report.

### Correction: NIST AI 100-2 in Foundations section 3.1

[Foundations section 3.1](../00_Foundations/03-Threat-Taxonomy.md#31-how-nist-classifies-attacks) misdescribed NIST AI 100-2e2025. It said that the report organises generative AI attacks into "evasion, poisoning, privacy and misuse" classes. In the published report, evasion, poisoning and privacy are the section headings of the **predictive** AI taxonomy. Both the predictive and the generative AI taxonomies classify attacks by the attacker's objective: availability (NISTAML.01), integrity (NISTAML.02), privacy (NISTAML.03), misuse (NISTAML.04, generative AI only) and supply chain (NISTAML.05). The section has been rewritten and was checked against the published PDF on 15 October 2026.

### UK AI Management Essentials (AIME) is withdrawn

Some lists of AI governance frameworks, including the one this update was checked against, present the UK's AI Management Essentials (AIME) as a current UK management standard. It is not. The UK Department for Science, Innovation and Technology (DSIT) published AIME as a draft self-assessment tool for consultation on 6 November 2024. Its government response, dated December 2025 and published on 6 February 2026, says that DSIT "will not be publishing AIME and therefore will not be making it a requirement of the government procurement process".

The response gives these reasons:

- Respondents found the tool's scope too broad to work as a single instrument.
- DSIT will instead write narrower guidance on foundational governance measures, aimed at small and medium-sized enterprises.
- DSIT will point organizations to other support, such as AI adoption hubs, rather than one tool.
- DSIT does not think it appropriate to link the guidance to specific legislation or standards.

The [UK AI Regulatory Hub](../21_UK_AI_Compliance/01_UK_AI_Regulatory_Hub.md) lists AIME as row UK13, a withdrawn draft, tagged [Verified] against the [government response](https://assets.publishing.service.gov.uk/media/6981d0758c1e89ed1e91bb55/AI_Management_Essentials_tool_government_response.pdf). The ten sections of the 2024 draft are still a reasonable lightweight self-check, but do not describe AIME as a UK requirement or standard.

### IEEE standards: based on available public data

IEEE standards are sold by IEEE, and their contents pages are not freely published. For IEEE 7000, 7001, 7002, 7003 and 7010, the wiki gives the title, year, status and scope as published on IEEE's own pages. Clause structures come from secondary public sources and, for IEEE 7001 and 7010, from papers by working group members that describe the draft standards. Each source is named on the [Trustworthy AI and Ethics Standards Crosswalk](../23_Framework_Crosswalks/16_Trustworthy_AI_Ethics_Crosswalk.md#ieee-7000-series-standards). Clause numbers have not been checked against the published standards.

### Verified in this update

These were checked on 15 October 2026 against the issuing body's own page or document, with a retrieval tool rather than line by line:

- ISO/IEC 38507, 42005, 42006, 23894, TR 24028, 5338, 23053, 22989 and 5259-1 to 5259-5: edition, title, clause numbers and clause headings, from publishers' pages and the free contents previews of standards stores.
- NIST AI 100-2e2025: section headings, attack classes and NISTAML identifiers, from the published PDF.
- EU Ethics Guidelines for Trustworthy AI: date and the seven requirements.
- UNESCO Recommendation: adoption date, values and principles from UNESCO's page; the eleven policy areas and their paragraph numbers from a copy of the full text.
- Council of Europe Framework Convention: article numbers and titles, Article 30(3) on entry into force, and the European Union's ratification on 15 May 2026.
- G7 Hiroshima Process Code of Conduct: the eleven actions, from the Code's text.
- UK AI Management Essentials: draft structure, consultation dates and the government response.

### Work in progress

These have not been fully verified. Treat them as provisional until a later update confirms them:

- **IEEE 7000, 7001, 7002, 7003 and 7010:** clause structures are from secondary public sources or describe drafts. IEEE 7002 has no public structure, so only its scope is given. The IEEE 7010 status page was found by search and not opened.
- **ISO/IEC standards:** only clause headings were read, not clause text, so every clause-to-control mapping is a judgment from the heading. The ISO page for ISO/IEC 23894 was not opened; its contents were checked in a store preview.
- **ISO/IEC 42006 audit time:** the factors that drive audit time (number of AI systems, high-risk uses, third-party AI) come from a secondary source.
- **Council of Europe Framework Convention:** the count of consents to be bound (only the EU as of 8 September 2026) comes from a secondary tracker, because the Treaty Office status page could not be read automatically. Whether each signatory has ratified has not been checked.
- **ALTAI:** the self-assessment web tool's address was found by search and not opened.
- **All mappings to wiki controls** on the four new crosswalk pages are this wiki's own judgment and have not been reviewed by the issuing bodies.
- **Not yet done:** recording NISTAML identifiers in each control and test case, so that the NIST AI 100-2 crosswalk can be generated at build time like the MITRE ATLAS one; adding the Council of Europe Convention to the regional hubs of its signatories; and a dedicated control for retiring AI systems (ISO/IEC 5338 clause 6.4.17).
