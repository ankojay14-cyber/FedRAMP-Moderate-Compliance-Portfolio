# KTech HealthCloud — FIPS 199 Security Categorization

> **Simulated program artifact.** KTech HealthCloud is a fictitious cloud service offering (CSO) created for cybersecurity GRC portfolio purposes. This categorization does not represent an actual federal information system or agency security categorization. All organizations, personnel, volumes, dates, and approvals are illustrative.

| Document Attribute | Value |
| --- | --- |
| **System** | KTech HealthCloud |
| **Document** | FIPS 199 Security Categorization |
| **Version** | 1.0 (Simulated) |
| **Status** | Final — Agency AO Concurrence Recorded (Simulated) |
| **Related Controls** | RA-2, PL-10, PL-2, CP-2 |
| **Result** | SC KTech HealthCloud = {(confidentiality, MODERATE), (integrity, MODERATE), (availability, MODERATE)} |

---

## Executive Summary

**Result:** KTech HealthCloud is categorized **Moderate** for confidentiality, integrity, and availability, which supports the FedRAMP Moderate baseline (Rev5 Class C).

**The key judgment call:** NIST SP 800-60 assigns Health Care Delivery Services a provisional **High** integrity impact. Retaining it would have made KTech a FedRAMP High system. Rather than lowering it by assertion, KTech tested five integrity-failure scenarios against the FIPS 199 impact definitions and lowered the value to **Moderate**. That adjustment is **conditional**: it depends on six enforceable conditions, backed by Customer Responsibility Matrix entries and significant-change triggers, that keep KTech out of clinical decision-making.

**What the analysis shows:**

* **Seven information types** mapped to specific SP 800-60 references, with four candidate types considered and excluded
* **Adjustments in both directions:** five values raised, one lowered
* **High confidentiality from aggregation** (~1.8M patient records) explicitly evaluated and rejected: aggregation raises the scale of harm but not its severity
* **Availability earned, not assumed:** care-coordination availability stays Low; the system reaches Moderate through authentication services
* **Traceability** from each assumption to the CRM, Secure Configuration Guide, Contingency Plan, and Significant Change process

**Reviewer's guide:**

| If you have… | Read |
| --- | --- |
| 1 minute | This summary and the [high-water-mark table](#10-adjusted-impact-summary--high-water-mark) |
| 5 minutes | [8.1 Integrity scenario analysis](#81-health-care-delivery-services--high--moderate) and [7.2 Aggregation analysis](#72-aggregation-analysis) |
| 15 minutes | [4.9 Enforceable conditions](#49-enforcement-of-categorization-assumptions) and [13 Categorization review meeting](#13-fips-199-categorization-review-meeting) |

---

## 1. Purpose

This document establishes the security categorization for KTech HealthCloud using:

* FIPS 199, *Standards for Security Categorization of Federal Information and Information Systems*
* NIST SP 800-60 Vol. 1 Rev. 1, *Guide for Mapping Types of Information and Information Systems to Security Categories*
* NIST SP 800-60 Vol. 2 Rev. 1, *Appendices to Guide for Mapping Types of Information and Information Systems to Security Categories*
* NIST SP 800-122, *Guide to Protecting the Confidentiality of Personally Identifiable Information (PII)*

The objective is to determine the potential impact of a loss of:

* Confidentiality
* Integrity
* Availability

for each applicable federal information type processed by KTech HealthCloud.

The resulting information-type impact levels are then evaluated using the FIPS 199 high-water-mark methodology to determine the overall security categorization of the system.

The categorization is based on the actual mission use and architectural assumptions established for this simulated environment rather than selecting an impact level in advance.

> **Reference version note:** SP 800-60 Vol. 2 Rev. 1 (2008) remains the current final guidance. NIST released an initial working draft of SP 800-60 Rev. 2 in January 2024, which proposes an updated information-type taxonomy and incorporates SP 800-122 guidance. Finalization of Rev. 2 is a recategorization trigger (Section 4.7).

---

## 2. System Description

### System Name

KTech HealthCloud

### System Type

Multi-tenant Software-as-a-Service (SaaS) platform.

### Hosting Environment

KTech HealthCloud is hosted within AWS GovCloud (US), a leveraged FedRAMP-authorized infrastructure environment.

### Intended Federal Use

For this simulated scenario, a fictitious federal healthcare agency uses KTech HealthCloud to support:

* Patient engagement
* Patient communications
* Appointment and service coordination
* Care-coordination workflows
* Outreach activities
* Patient demographic management
* Healthcare-related notifications
* User identity and access management
* Security logging and monitoring

The platform processes simulated federal information that includes personally identifiable information (PII) and protected health information (PHI).

### Simulated Operating Profile

| Attribute | Value |
| --- | --- |
| **Agency Tenants** | 3 |
| **Patient Records** | ~1.8 million |
| **Agency Users** | ~6,000 (care coordinators, case managers, administrative staff) |
| **Patient Users** | Enrolled patients via patient portal |
| **Agency Role** | HIPAA covered entity |
| **KTech Role** | Business associate under a simulated Business Associate Agreement (BAA) |

### System Role

KTech HealthCloud supports patient-engagement and care-coordination activities but is **not the authoritative clinical system of record**.

The agency's Electronic Health Record (EHR) or other authorized clinical system remains the authoritative source for clinical information used for diagnosis and treatment. KTech receives a read-only reference subset of clinical data (such as problem lists, allergies, and medication lists) to support coordination.

KTech HealthCloud does not independently:

* Diagnose patients
* Recommend clinical treatment
* Prescribe or administer medication
* Control medical devices
* Direct emergency medical treatment
* Make autonomous clinical decisions
* Replace the authoritative Electronic Health Record
* Serve as the sole source of information for life-safety decisions

Clinical personnel are expected to validate material clinical information against the authoritative clinical record before making clinical decisions.

These assumptions are material to the integrity categorization and are reflected in applicable customer responsibilities (Section 4).

---

## 3. Categorization Methodology

KTech uses the following process to determine the system security categorization.

### Step 1 — Identify Information Types

Identify the federal information types processed, stored, transmitted, generated, or otherwise supported by KTech HealthCloud.

### Step 2 — Determine Provisional Impact Levels

Identify the provisional confidentiality, integrity, and availability impact levels recommended by NIST SP 800-60 for each applicable information type.

### Step 3 — Evaluate Special Factors

Evaluate whether the provisional impact levels should be adjusted based on KTech's actual:

* Mission use
* Information sensitivity
* Privacy considerations
* Volume and aggregation of information
* Operational dependency
* User population
* System functionality
* Healthcare context
* Potential harm to individuals
* Potential harm to agency operations
* System dependencies
* Availability requirements

### Step 4 — Document Adjustments

Any adjustment from the NIST SP 800-60 provisional impact level must be supported by documented rationale.

Impact levels are not reduced solely to achieve a desired FedRAMP baseline.

**Impact is assessed before controls.** Categorization reflects the potential harm if confidentiality, integrity, or availability is lost. Encryption, tenant isolation, and other safeguards do not lower impact levels; they respond to them.

### Step 5 — Apply the High-Water Mark

For each security objective, KTech selects the highest applicable impact level across all information types.

The resulting system categorization follows the FIPS 199 structure:

```text
SC KTech HealthCloud = {(confidentiality, impact), (integrity, impact), (availability, impact)}
```

### Step 6 — Review and Approval

KTech, as the simulated CSP, proposes and documents the categorization based on its understanding of the CSO, information types, architecture, and intended use.

For an agency-sponsored authorization, the sponsoring agency reviews the categorization and the Authorizing Official (AO) ultimately confirms or accepts the security categorization as part of the agency's risk-management and authorization process.

### FIPS 199 Impact Definitions

| Level | Potential Adverse Effect |
| --- | --- |
| **Low** | Limited adverse effect on organizational operations, organizational assets, or individuals |
| **Moderate** | Serious adverse effect, including significant harm to individuals that does not involve loss of life or serious life-threatening injuries |
| **High** | Severe or catastrophic adverse effect, including catastrophic harm to individuals involving loss of life or serious life-threatening injuries |

---

## 4. Categorization Assumptions & Constraints

The KTech categorization depends on several system-use assumptions.

These assumptions are explicitly documented because changes to them could affect the confidentiality, integrity, or availability impact levels.

### 4.1 KTech Is Not the Authoritative Clinical Record

The authoritative Electronic Health Record or other approved agency clinical system remains the authoritative source for clinical decision-making.

KTech HealthCloud is used primarily for patient engagement, communication, outreach, scheduling, and care coordination.

### 4.2 No Autonomous Clinical Decision-Making

KTech does not autonomously determine:

* Diagnosis
* Medication
* Treatment
* Clinical priority
* Emergency response
* Life-safety decisions

### 4.3 Clinical Information Requires Verification

Information presented through KTech that could materially influence clinical treatment must be validated against the authoritative clinical system before a clinical decision is made.

To support verification, KTech displays the source system and last-synchronized timestamp for all reference clinical data.

### 4.4 Alternative Procedures Exist

Temporary KTech unavailability does not eliminate the agency's ability to deliver emergency or life-safety healthcare services.

Authorized personnel can use the agency's authoritative clinical systems and established alternative procedures during a KTech service disruption.

### 4.5 PHI Is a Regulatory/Privacy Characteristic

Protected Health Information (PHI) is not treated as a separate NIST SP 800-60 information type.

Instead, HIPAA/HITECH requirements are considered as an additional legal and regulatory overlay on applicable healthcare information processed by KTech.

PII confidentiality is additionally evaluated using NIST SP 800-122 (Section 7.3).

### 4.6 Multi-Tenant Data Aggregation

KTech is a multi-tenant SaaS environment capable of storing significant quantities of PII and PHI.

The categorization therefore considers whether aggregation of sensitive information increases the consequences of unauthorized disclosure beyond the provisional impact assigned to an individual information type.

The aggregation analysis in Section 7.2 explicitly evaluates whether aggregation warrants a Moderate or High confidentiality impact rather than assuming that PHI automatically results in Moderate confidentiality.

### 4.7 Recategorization Trigger

The security categorization must be reviewed when changes materially affect the assumptions used in this analysis.

Potential recategorization triggers include KTech:

* Becoming an authoritative clinical system of record
* Introducing clinical decision-support functionality
* Providing automated diagnosis or treatment recommendations, including AI-generated clinical recommendations
* Supporting medication administration or prescribing
* Supporting emergency or life-safety workflows
* Becoming a critical dependency for delivery of healthcare services
* Processing materially different federal information types
* Ingesting any excluded record category (Section 4.8)
* Significantly expanding the volume or sensitivity of federal information
* Introducing new agency missions or user populations
* Undergoing architectural changes that materially affect potential impact

Additional review triggers:

* Finalization of NIST SP 800-60 Rev. 2
* Annual review, at minimum

Such changes must be evaluated through the KTech significant-change process, aligned with FedRAMP Significant Change Notification (SCN) requirements, to determine whether the existing FIPS 199 categorization remains appropriate.

### 4.8 Excluded Record Categories

The following heightened-sensitivity record categories are excluded from ingestion. Their inclusion would materially change the confidentiality and aggregation analysis.

* Psychotherapy notes
* Substance use disorder records subject to 42 CFR Part 2
* Records of specially protected populations designated by the agency

### 4.9 Enforcement of Categorization Assumptions

Each assumption is enforced through a specific mechanism so that it functions as a verifiable condition rather than an unenforced expectation.

| Condition | Assumption | Enforced Through | Owner |
| --- | --- | --- | --- |
| C-1 | KTech is not the clinical system of record | BAA and terms of use; CRM-KTECH-CLIN-001 | Agency / KTech |
| C-2 | No autonomous clinical decision-making | Product scope in SSP / Security Decision Record; SA-8 design review; change control | KTech |
| C-3 | Clinical information is verified against the EHR | CRM-KTECH-CLIN-001; source and timestamp display (SI-10) | Agency / KTech |
| C-4 | Alternative procedures exist for outages | CRM-KTECH-CONT-001; agency contingency plan | Agency |
| C-5 | Excluded record categories are not ingested | Ingestion filters; Data Flow Diagram; Secure Configuration Guide; CRM-KTECH-DATA-001 | KTech / Agency |
| C-6 | Record modifications are logged and recoverable | AU-2, AU-12, CP-9, CP-10 | KTech |

### 4.10 Customer Responsibility Matrix Entries

| CRM ID | Customer Responsibility | Rationale |
| --- | --- | --- |
| **CRM-KTECH-CLIN-001** | The customer must not use KTech HealthCloud as the authoritative clinical system of record. Clinical information that could materially affect diagnosis, medication, treatment, emergency response, or other clinical decisions must be verified against the customer's authorized clinical system of record. | Supports the defined use of KTech as a patient-engagement and care-coordination platform and is a material assumption supporting the system's integrity categorization. |
| **CRM-KTECH-CONT-001** | The customer must maintain documented alternative procedures (such as EHR-native referral tracking and telephone outreach) for care-coordination activities during a KTech service disruption. | Supports the availability analysis and ensures a KTech outage does not prevent delivery of healthcare services. |
| **CRM-KTECH-DATA-001** | The customer must not transmit or configure integrations that send excluded record categories (Section 4.8) to KTech HealthCloud. | Supports the confidentiality and aggregation analysis. |
| **CRM-KTECH-SUP-001** | Customer users must not include PHI in support tickets. | Reduces unnecessary PHI exposure. This responsibility does **not** lower the Help Desk Services confidentiality impact (Section 7.1), because impact is assessed before controls. |

---

## 5. Information Type Identification

The information-type analysis begins with the business and mission functions actually supported by KTech rather than treating all healthcare-related information as a single information type. Each data element in the KTech Data Flow Diagram was traced to its business function and mapped to a specific SP 800-60 Vol. 2 information type.

| # | KTech Information / Function | SP 800-60 Information Type | SP 800-60 Reference |
| --- | --- | --- | --- |
| IT-1 | Care plans, referrals, care-team tasks, transition-of-care notes, reference clinical data | Health Care Delivery Services | D.14.4 |
| IT-2 | Appointment requests, scheduling, reminders, outreach campaigns, patient messages | Access to Care | D.14.1 |
| IT-3 | Patient demographics and identifiers; user accounts, credentials, and MFA enrollment | Personal Identity and Authentication | C.2.8.9 |
| IT-4 | Application, infrastructure, and security audit logs | System and Network Monitoring | C.3.5.8 |
| IT-5 | Security configurations, vulnerability data, incident records, key-management metadata | Information Security | C.3.5.5 |
| IT-6 | Tenant configuration, role definitions, access settings | IT Infrastructure Maintenance | C.3.5.4 |
| IT-7 | Customer support tickets | Help Desk Services | C.3.1.2 |

### 5.1 Resolution of Initial Candidate Types

The initial draft identified six candidate functions, three of which required validation against the SP 800-60 taxonomy. They were resolved as follows:

| Initial Candidate | Resolution |
| --- | --- |
| Patient scheduling, outreach, and access-to-service information | Mapped to **Access to Care (D.14.1)** rather than Health Care Delivery Services, because it supports patients' access to services rather than delivery of care |
| Patient identity and user account information (two candidates) | Combined under **Personal Identity and Authentication (C.2.8.9)**, which covers both identity and authentication information |
| Audit, security, and monitoring information | Split into **System and Network Monitoring (C.3.5.8)** for log data and **Information Security (C.3.5.5)** for security operations data |
| SaaS/system administrative information | Split into **IT Infrastructure Maintenance (C.3.5.4)** for tenant configuration and access settings, and **Help Desk Services (C.3.1.2)** for support tickets |

### 5.2 Information Types Considered and Excluded

| Information Type | Reason for Exclusion |
| --- | --- |
| Health Care Administration (D.14.3) | KTech performs no billing, claims, or payment processing |
| Health Care Research and Practitioner Education (D.14.5) | No research or training datasets are processed |
| Population Health Management and Consumer Safety (D.14.2) | KTech does not perform population health surveillance or consumer safety monitoring |
| Customer Services (C.2.6.1) | This type covers agency public-affairs customer service; KTech support tickets map more precisely to Help Desk Services |

### 5.3 Where PHI Appears

PHI is present in IT-1, IT-2, and IT-3, and may appear in IT-4 (log content) and IT-7 (support tickets). This distribution drives the confidentiality adjustments in Section 7.

---

## 6. Provisional Impact Levels

| # | Information Type | Ref. | C | I | A |
| --- | --- | --- | --- | --- | --- |
| IT-1 | Health Care Delivery Services | D.14.4 | Low | **High** | Low |
| IT-2 | Access to Care | D.14.1 | Low | Moderate | Low |
| IT-3 | Personal Identity and Authentication | C.2.8.9 | Moderate | Moderate | Moderate |
| IT-4 | System and Network Monitoring | C.3.5.8 | Moderate | Moderate | Low |
| IT-5 | Information Security | C.3.5.5 | Low | Moderate | Low |
| IT-6 | IT Infrastructure Maintenance | C.3.5.4 | Low | Low | Low |
| IT-7 | Help Desk Services | C.3.1.2 | Low | Low | Low |

**Relevant SP 800-60 special factors:**

* **Health Care Delivery Services:** confidentiality may warrant Moderate where privacy-protected medical information is involved; integrity is provisionally High because inaccurate clinical information could contribute to loss of life.
* **IT Infrastructure Maintenance:** SP 800-60 notes that the confidentiality impact of this type may necessitate the highest confidentiality impact of the information types processed by the system, because access settings protect all other information.

---

## 7. Confidentiality Analysis

### 7.1 Adjustments

**IT-1 Health Care Delivery Services — Low → Moderate.**
KTech care-coordination data is individually identifiable health information. Unauthorized disclosure could cause significant harm to individuals, including discrimination, embarrassment, and financial or reputational harm, and would trigger HIPAA breach-notification obligations for the agency. This matches the SP 800-60 special factor for privacy-protected medical information.

**IT-2 Access to Care — Low → Moderate.**
Appointment and messaging data links identified patients to specific services, providers, and conditions. Disclosure reveals health information by inference even without full clinical records.

**IT-6 IT Infrastructure Maintenance — Low → Moderate.**
Tenant access settings and role definitions control access to all PHI in the tenant. Consistent with the SP 800-60 special factor for this type, its confidentiality is raised to match the highest confidentiality of the information it protects.

**IT-7 Help Desk Services — Low → Moderate.**
Agency users may include patient details in support tickets despite CRM-KTECH-SUP-001. Because PHI can reasonably enter this channel, the potential impact of disclosure is Moderate. The customer responsibility reduces the likelihood of PHI entering tickets but does not lower the impact level.

**No adjustment:** IT-3 (Moderate), IT-4 (Moderate; log content may include PII fragments, consistent with the provisional value), and IT-5 (Low; security operations data contains no PII/PHI by design).

### 7.2 Aggregation Analysis

KTech concentrates approximately 1.8 million patient records from three agency tenants in one multi-tenant service. SP 800-60 identifies aggregation as a factor that may raise impact levels, so **High confidentiality was explicitly evaluated and rejected.**

| Consideration | Assessment |
| --- | --- |
| Harm to individuals from a full-dataset breach | Serious and widespread (identity theft, privacy harm, discrimination), but not expected to cause loss of life or serious life-threatening injury |
| Harm to agency operations | Serious (breach response, notification costs, loss of public trust), but not catastrophic to the agency's ability to perform its primary mission |
| Data categories that would elevate harm | Excluded by Section 4.8 and CRM-KTECH-DATA-001 |
| National security or law-enforcement sensitivity | None |

**Conclusion:** Aggregation increases the *scale* of potential harm but does not change its *severity* from serious to severe or catastrophic. Confidentiality remains **Moderate**. If the excluded record categories in Section 4.8 are ever ingested, aggregation must be re-evaluated.

### 7.3 SP 800-122 PII Confidentiality Cross-Check

| SP 800-122 Factor | KTech Assessment |
| --- | --- |
| Identifiability | Directly identifiable (name, date of birth, contact data, agency patient ID) |
| Quantity of PII | Large (~1.8M individuals) |
| Data field sensitivity | Elevated — health information linked to identity |
| Context of use | Healthcare services; disclosure reveals health status |
| Obligations to protect | HIPAA/HITECH, Privacy Act, agency requirements |
| Access and location | Remote access by agency users and patients; hosted in AWS GovCloud (US) |

**PII confidentiality impact level: Moderate**, consistent with the Section 7.2 conclusion.

### 7.4 System Confidentiality

Highest adjusted confidentiality value across all information types: **MODERATE**.

---

## 8. Integrity Analysis

Integrity is the decisive objective for this system. The provisional High value for Health Care Delivery Services would make the system High impact if retained.

KTech did not automatically reduce this value. The assumptions in Section 4 provide part of the basis for the analysis but do not, by themselves, establish a Moderate rating. The downward adjustment below is justified by demonstrating, scenario by scenario, that a credible loss of integrity would not reasonably be expected to cause the severe or catastrophic effects associated with High impact.

### 8.1 Health Care Delivery Services — High → Moderate

| Integrity Failure Scenario | Worst Credible Consequence | Why Not Severe/Catastrophic |
| --- | --- | --- |
| Reference medication or allergy list altered in KTech | Care coordinator sees incorrect information | KTech is not used for prescribing or administration; clinicians verify against the EHR (C-1, C-2, C-3) |
| Referral incorrectly marked complete | Delayed follow-up; missed or late specialist visit | Serious harm is possible, which is why integrity is Moderate rather than Low. Delay in non-emergency coordination is not expected to cause loss of life, and the EHR referral record remains authoritative (C-1, C-4) |
| Incorrect scheduling or reminder data | Missed appointment | Limited to serious operational harm; patient can confirm with the clinic |
| Care-team task reassigned or deleted | Task not performed on time | Detected through task aging and audit logs; recoverable (C-6) |
| Malicious bulk modification of records | Widespread incorrect coordination data | Serious operational harm and loss of trust; clinical decisions remain anchored in the EHR (C-1, C-3) |

**Conclusion:** Integrity failures in KTech could cause **serious** adverse effects, including significant harm to individuals through delayed care. Under the scoped use, a credible integrity failure is not expected to cause loss of life or serious life-threatening injury. The adjusted value is **Moderate**, not Low.

> **This adjustment is conditional.** It holds only while conditions C-1 through C-6 (Section 4.9) remain true. If KTech becomes a clinical system of record, adds clinical decision support, or supports emergency workflows, integrity reverts to High and the system must be recategorized.

### 8.2 IT Infrastructure Maintenance — Low → Moderate

Unauthorized modification of tenant access settings or role definitions could grant unauthorized access to PHI or disable security-relevant configurations across a tenant. The potential effect is serious, so integrity is raised to Moderate.

### 8.3 No Adjustment

IT-2, IT-3, IT-4, and IT-5 retain their provisional Moderate integrity. IT-7 retains Low integrity; modification of support tickets would have only a limited adverse effect.

### 8.4 System Integrity

Highest adjusted integrity value across all information types: **MODERATE**.

---

## 9. Availability Analysis

### 9.1 Health Care Delivery Services — Retained at Low

KTech did not raise Health Care Delivery Services availability to Moderate simply because the target environment is FedRAMP Moderate.

An outage of care-coordination functions causes limited operational disruption: agency staff revert to EHR-native referral tracking and telephone outreach under CRM-KTECH-CONT-001 (C-4). The provisional Low value is retained.

### 9.2 Personal Identity and Authentication — Retained at Moderate

Loss of authentication services prevents all agency users and patients from accessing any KTech function, including secure messaging. The simulated Business Impact Analysis (BIA) shows that extended outages cause serious degradation of agency operations:

| Outage Duration (Simulated BIA) | Effect | Impact |
| --- | --- | --- |
| Up to 4 hours | Workflow delays; manual workarounds in use | Limited |
| 4–24 hours | Backlogged referrals and messages; missed outreach windows; increased agency staff burden | Serious |
| More than 72 hours | Sustained degradation of care-coordination operations across tenants | Serious; not catastrophic, because clinical care continues through the EHR |

The provisional Moderate value is retained.

### 9.3 No Adjustment

All other information types retain their provisional Low availability.

### 9.4 System Availability

Highest adjusted availability value across all information types: **MODERATE**, driven by Personal Identity and Authentication.

The simulated BIA results feed the Contingency Plan (CP-2): **RTO 4 hours, RPO 1 hour** for core services.

---

## 10. Adjusted Impact Summary & High-Water Mark

| # | Information Type | Provisional (C/I/A) | Adjusted C | Adjusted I | Adjusted A |
| --- | --- | --- | --- | --- | --- |
| IT-1 | Health Care Delivery Services | L / H / L | M ↑ | M ↓ | L |
| IT-2 | Access to Care | L / M / L | M ↑ | M | L |
| IT-3 | Personal Identity and Authentication | M / M / M | M | M | **M** |
| IT-4 | System and Network Monitoring | M / M / L | M | M | L |
| IT-5 | Information Security | L / M / L | L | M | L |
| IT-6 | IT Infrastructure Maintenance | L / L / L | M ↑ | M ↑ | L |
| IT-7 | Help Desk Services | L / L / L | M ↑ | L | L |
| | **System High-Water Mark** | | **M** | **M** | **M** |

↑ = raised from provisional; ↓ = lowered from provisional

**Adjustment balance:** Five values were raised and one was lowered. The single downward adjustment (IT-1 integrity) is conditional and bounded by Section 4.9.

---

## 11. Final FIPS 199 Security Categorization

```text
SC KTech HealthCloud = {(confidentiality, MODERATE),
                        (integrity, MODERATE),
                        (availability, MODERATE)}
```

| Outcome | Value |
| --- | --- |
| **FIPS 199 System Impact Level** | Moderate |
| **FIPS 200 / SP 800-53B Baseline** | Moderate |
| **FedRAMP Baseline** | FedRAMP Moderate — NIST SP 800-53 Rev. 5 |
| **FedRAMP CR26 Certification Class** | Rev5 Class C |

### Summary Rationale

KTech HealthCloud processes identifiable health information at scale, which makes confidentiality **Moderate**; aggregation raises the scale but not the severity of potential harm. It supports care coordination but is not a clinical system of record, which makes integrity **Moderate** rather than High, subject to enforceable conditions. Authentication availability affects every user, which makes availability **Moderate**.

### Completion of Categorization Criteria

| Criterion (from Draft v0.1) | Status | Section |
| --- | --- | --- |
| All applicable information types identified | Complete | 5 |
| Provisional values documented | Complete | 6 |
| Adjustment factors evaluated | Complete | 7–9 |
| Health Care Delivery Services integrity determination justified | Complete | 8.1 |
| PII confidentiality and aggregation evaluated | Complete | 7.2–7.3 |
| FIPS 199 high-water mark applied | Complete | 10 |

---

## 12. Traceability

| This Categorization Feeds | Artifact |
| --- | --- |
| Baseline selection (PL-10) | Control Implementation Matrix |
| RA-2 implementation statement | SSP / Security Decision Record |
| CRM-KTECH-CLIN-001, CONT-001, DATA-001, SUP-001 | Customer Responsibility Matrix |
| Customer configuration requirements (C-5) | Secure Configuration Guide |
| BIA results (RTO/RPO) | Contingency Plan (CP-2) |
| Recategorization triggers (Section 4.7) | Configuration / Significant Change Tracker |
| Information types and data elements | Data Flow Diagram; Privacy Impact Assessment |

---

## 13. FIPS 199 Categorization Review Meeting

Before formal approval, KTech held a joint categorization review with the sponsoring agency. Including agency stakeholders at this stage surfaced agency concerns before the package entered formal review, rather than after.

| Meeting Attribute | Value |
| --- | --- |
| **Date** | 2026-10-16 (Simulated) |
| **Format** | 90-minute working session |
| **Input** | Categorization Draft v0.9 |
| **Facilitator** | KTech GRC Lead |

### Participants

| Organization | Role |
| --- | --- |
| KTech | System Owner |
| KTech | GRC Lead (facilitator) |
| KTech | Security Architect |
| KTech | Privacy Officer |
| KTech | Clinical Workflow SME |
| Sponsoring Agency | System Owner |
| Sponsoring Agency | Information System Security Officer (ISSO) |
| Sponsoring Agency | Privacy Officer |

The KTech CISO and the agency Authorizing Official did not attend. Both received the meeting record before their approval decisions, so their review stays independent of the working session.

### Agenda

1. Information types and SP 800-60 mappings
2. Provisional values and adjustments
3. Health Care Delivery Services integrity adjustment
4. PII/PHI aggregation analysis
5. Categorization conditions and customer responsibilities
6. Recategorization triggers and high-water-mark result

### Issues Raised and Resolutions

| # | Raised By | Issue | Discussion | Resolution |
| --- | --- | --- | --- | --- |
| R-1 | Agency Privacy Officer | Should ~1.8M patient records across three tenants warrant **High** confidentiality? | The Privacy Officer noted that harm severity depends on record content, not only volume. The team agreed that behavioral health and substance use records would materially change the analysis. | **Retained Moderate, with a new condition.** Added Section 4.8 (excluded record categories), condition C-5, and CRM-KTECH-DATA-001. Aggregation analysis (7.2) updated to cite the exclusion. |
| R-2 | Agency ISSO | Is "clinicians verify against the EHR" enforceable, or only an expectation? | The Security Architect confirmed the application can display source system and last-synchronized timestamps. The Clinical Workflow SME confirmed care coordinators already reconcile against the EHR during referral review. | **Strengthened C-3.** Added source and timestamp display as a KTech-enforced mechanism (SI-10) alongside CRM-KTECH-CLIN-001. |
| R-3 | Agency System Owner | Does the agency have documented outage procedures for care coordination? | The agency confirmed informal procedures exist but are not written down. | **New customer responsibility.** Added CRM-KTECH-CONT-001. Agency to document procedures in its contingency plan (A-3). |
| R-4 | KTech Security Architect | Should tenant access settings be categorized separately from general admin data? | Access settings protect all PHI in a tenant; general support tickets do not. | **Split IT-6 and IT-7.** Tenant configuration mapped to IT Infrastructure Maintenance (raised to M/M/L); support tickets mapped to Help Desk Services. |

### Decision

The review team agreed that, with resolutions R-1 through R-4 incorporated, the analysis supports the proposed categorization:

* **Confidentiality:** Moderate
* **Integrity:** Moderate, conditional on C-1 through C-6
* **Availability:** Moderate

No participant recorded a dissent. The agency Privacy Officer's concurrence on R-1 was conditional on C-5 being validated during the 3PAO assessment.

### Action Items

| # | Action | Owner | Due (Simulated) | Status |
| --- | --- | --- | --- | --- |
| A-1 | Incorporate R-1 through R-4 and issue Draft v0.95 | KTech GRC Lead | 2026-10-19 | Closed |
| A-2 | Add CRM-KTECH-DATA-001 and CRM-KTECH-CONT-001 to the Customer Responsibility Matrix | KTech GRC Lead | 2026-10-19 | Closed |
| A-3 | Document care-coordination outage procedures in the agency contingency plan | Agency System Owner | 2026-11-30 | Open — tracked in agency POA&M |
| A-4 | Confirm Access to Care provisional values against SP 800-60 Vol. 2, D.14.1 | KTech GRC Lead | 2026-10-19 | Closed |
| A-5 | Add validation of ingestion filters (C-5) to the 3PAO test scope | KTech GRC Lead | Before SAP finalization | Open |

---

## 14. Review & Approval

| Role | Organization | Responsibility | Status | Date (Simulated) |
| --- | --- | --- | --- | --- |
| System Owner | KTech | Propose and document categorization | Complete | 2026-10-09 |
| GRC Lead | KTech | Validate methodology, information types, assumptions, and rationale; facilitate review meeting | Complete | 2026-10-16 |
| Security Architect | KTech | Validate architecture-dependent conditions (C-2, C-3, C-5, C-6) | Reviewed | 2026-10-16 |
| Privacy Officer | KTech | Review PII/PHI analysis and CRM privacy entries | Reviewed | 2026-10-16 |
| CISO | KTech | Approve CSP-proposed categorization | Approved | 2026-10-20 |
| System Owner | Sponsoring Agency | Confirm intended federal use and customer responsibilities | Reviewed | 2026-10-23 |
| ISSO | Sponsoring Agency | Review categorization against intended federal use | Reviewed | 2026-10-23 |
| Privacy Officer | Sponsoring Agency | Review PII/PHI and aggregation analysis | Reviewed (conditional on C-5 validation) | 2026-10-23 |
| Authorizing Official | Sponsoring Agency | Confirm/accept categorization within the authorization and risk-decision process | Concurred | 2026-10-28 |

### Version History

| Version | Date (Simulated) | Description |
| --- | --- | --- |
| 0.1 | 2026-10-02 | Draft — assumptions established; information-type analysis in progress |
| 0.9 | 2026-10-14 | Review draft — all information types mapped, adjustments proposed, high-water mark applied |
| 0.95 | 2026-10-19 | Incorporated review meeting resolutions R-1 through R-4 |
| 1.0 | 2026-10-28 | Final — CISO approval and agency AO concurrence recorded |

---

## References

* FIPS 199 — Standards for Security Categorization of Federal Information and Information Systems
* FIPS 200 — Minimum Security Requirements for Federal Information and Information Systems
* NIST SP 800-60 Vol. 1 Rev. 1 & Vol. 2 Rev. 1 — Guide for Mapping Types of Information and Information Systems to Security Categories
* NIST SP 800-60 Rev. 2 (Initial Working Draft, January 2024) — monitored, not applied
* NIST SP 800-122 — Guide to Protecting the Confidentiality of PII
* NIST SP 800-37 Rev. 2 — Risk Management Framework
* NIST SP 800-53B — Control Baselines
* FedRAMP Consolidated Rules for 2026
