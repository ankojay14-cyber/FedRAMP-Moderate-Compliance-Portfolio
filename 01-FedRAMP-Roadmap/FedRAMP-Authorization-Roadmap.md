# KTech HealthCloud — FedRAMP Moderate Authorization Roadmap

> **Simulated program artifact.** KTech HealthCloud is a fictitious cloud service offering (CSO) created for cybersecurity GRC portfolio purposes. See the repository root README for the complete portfolio disclaimer.

## Purpose

This roadmap defines the simulated path KTech HealthCloud follows to prepare for, obtain, and maintain an **agency-sponsored FedRAMP Moderate Rev. 5 authorization** while incorporating applicable FedRAMP Consolidated Rules for 2026.

Unlike the repository README, which explains my overall FedRAMP methodology, this document functions as the **KTech program roadmap** by identifying milestones, phase gates, deliverables, dependencies, and operational activities across the authorization lifecycle.

---

## Program Summary

| Item                             | Detail                                                                              |
| -------------------------------- | ----------------------------------------------------------------------------------- |
| **CSO**                          | KTech HealthCloud — multi-tenant SaaS                                               |
| **Impact Level**                 | Moderate                                                                            |
| **Security Categorization**      | FIPS 199: Confidentiality = Moderate, Integrity = Moderate, Availability = Moderate |
| **Security Baseline**            | FedRAMP Moderate — NIST SP 800-53 Rev. 5                                            |
| **Authorization Scenario**       | Agency-sponsored Rev. 5 authorization                                               |
| **Underlying Cloud**             | AWS GovCloud (US)                                                                   |
| **Control Responsibility Model** | KTech-implemented, inherited, shared, and customer responsibilities                 |
| **Federal Data**                 | Simulated PII and PHI                                                               |
| **Healthcare Overlay**           | HIPAA/HITECH                                                                        |
| **3PAO**                         | Meridian Assurance Partners — fictitious 3PAO                                       |
| **Modernization Context**        | FedRAMP Consolidated Rules for 2026 / 20x transition                                |

---

## Program Context — Rev. 5 & FedRAMP 2026

KTech intentionally demonstrates a **FedRAMP Moderate Rev. 5 authorization lifecycle** because Rev. 5 remains relevant to existing authorization environments and demonstrates practical knowledge of NIST SP 800-53, SSP documentation, control inheritance, evidence management, independent assessment, vulnerability management, and continuous monitoring.

The simulated program also incorporates applicable **FedRAMP Consolidated Rules for 2026** as they transition into Rev. 5 operations.

The modernization direction includes:

* Vulnerability Detection and Response (VDR)
* Vulnerability Evaluation and Reporting (VER)
* Secure Configuration Guide (SCG)
* Significant Change Notification (SCN)
* Collaborative Continuous Monitoring (CCM)
* Independent Verification and Validation (IVV)
* Machine-readable certification information
* Persistent security validation
* Security Decision Records and modernized certification-package concepts

KTech therefore demonstrates traditional Rev. 5 authorization knowledge while progressively incorporating the current FedRAMP operating model.

---

## Simulated Program Timeline

| Milestone                                | Target            | Phase Gate / Exit Criteria                                                          |
| ---------------------------------------- | ----------------- | ----------------------------------------------------------------------------------- |
| **Program Kickoff**                      | Oct 2026          | Sponsor, stakeholders, scope, and governance established                            |
| **FIPS 199 Categorization**              | Oct 2026          | C/I/A categorization documented and approved for the simulation                     |
| **Architecture & Boundary Definition**   | Oct 2026          | Boundary, architecture, components, data flows, and external connections documented |
| **Initial Gap Assessment**               | Nov 2026          | Applicable control gaps identified, risk-ranked, and assigned                       |
| **Control Implementation & Remediation** | Nov 2026–Jan 2027 | Priority implementation gaps addressed                                              |
| **SSP & Evidence Readiness**             | Feb 2027          | SSP narratives, evidence, responsibilities, and inheritance validated               |
| **Assessment Readiness Review**          | Feb 2027          | Material readiness gaps addressed before independent assessment                     |
| **SAP Finalization**                     | Mar 2027          | 3PAO assessment scope and testing approach established                              |
| **3PAO Assessment**                      | Mar–Apr 2027      | Independent testing and evidence review completed                                   |
| **SAR Delivery**                         | May 2027          | Assessment findings documented                                                      |
| **Pre-Authorization Remediation**        | May–Jun 2027      | Required corrective actions addressed and validated                                 |
| **Authorization Decision Support**       | Jun 2027          | Authorization package and residual-risk information prepared                        |
| **Continuous Monitoring**                | Ongoing           | Security posture continuously monitored and reported                                |

> These dates are simulated for portfolio purposes and are intended to demonstrate program sequencing, dependencies, phase gates, and lifecycle management.

---

## Phase 1 — Scope, Categorization, Architecture & Readiness

### Objective

Define what is being authorized, understand how the system operates, establish the authorization boundary, determine the applicable security requirements, and establish security responsibility before detailed implementation and assessment activities begin.

### Key Activities

* Define the KTech HealthCloud service offering and SaaS deployment model.
* Identify intended federal use cases and applicable federal information.
* Identify information types using FIPS 199 and NIST SP 800-60.
* Establish the simulated security categorization:

  * Confidentiality = Moderate
  * Integrity = Moderate
  * Availability = Moderate
* Establish the authorization boundary.
* Document system architecture.
* Identify system components and supporting services.
* Document PII/PHI data flows.
* Identify network boundaries and segmentation.
* Identify administrative access paths.
* Identify external connections and trust relationships.
* Identify dependencies on AWS GovCloud services.
* Identify security capabilities leveraged from the underlying AWS environment.
* Establish control responsibility and inheritance.
* Identify customer responsibilities.
* Perform the initial FedRAMP Moderate readiness assessment.

### Responsibility Model

For applicable requirements, KTech determines whether implementation is:

**KTech Implemented → Inherited → Shared → Customer Responsibility**

For Rev. 5 control documentation, these determinations are reflected through applicable **Control Implementation Summary (CIS)** and **Customer Responsibility Matrix (CRM)** information.

### Phase Gate

Phase 1 is complete when:

* Security categorization is documented.
* Authorization boundary is defined.
* Architecture and data flows are documented.
* System components and dependencies are identified.
* Responsibility and inheritance are understood.
* Initial control gaps have been identified.

### Outputs

* FIPS 199 Security Categorization
* Authorization Boundary Diagram
* System Architecture Diagram
* Network Diagram
* Data Flow Diagram
* System / Service Inventory
* CIS / CRM responsibility information
* Initial Gap Assessment
* Authorization Roadmap

📁 **Portfolio Area:** [`01-FedRAMP-Roadmap/`](./)

---

## Phase 2 — Control Implementation, CIS/CRM, SSP & Evidence

### Objective

Determine how applicable FedRAMP Moderate requirements are satisfied, establish implementation responsibility, remediate gaps, and develop assessor-ready security documentation and evidence.

### Key Activities

* Establish the applicable FedRAMP Moderate Rev. 5 baseline.
* Analyze applicable controls and control enhancements.
* Determine control implementation status.
* Identify inherited control capabilities.
* Identify shared responsibilities.
* Identify customer responsibilities.
* Maintain applicable CIS/CRM information.
* Assign control ownership across GRC, Cloud Engineering, IAM, SOC, application teams, and other responsible functions.
* Remediate implementation gaps.
* Develop assessor-readable control implementation narratives.
* Build and maintain the System Security Plan.
* Establish evidence traceability.
* Maintain supporting security plans, policies, standards, and procedures.

### Control Documentation

Each control narrative addresses:

* **Who** is responsible
* **What** implements the requirement
* **Where** the control operates
* **How** the control operates
* **What** is inherited
* **What** is shared
* **What** the customer must implement or configure
* **What evidence** demonstrates implementation

### Control Analysis Flow

**Control Requirement → Responsibility / Inheritance → Implementation → Owner → Evidence → Gap → Remediation → Validation**

### 2026 Transition

KTech also maintains a **Secure Configuration Guide** describing security-relevant customer configuration responsibilities.

This demonstrates the transition from the traditional CIS/CRM model toward FedRAMP's modernized approach to communicating secure customer configuration requirements.

### Phase Gate

Phase 2 is complete when:

* Material control gaps have remediation plans.
* Control ownership is established.
* SSP narratives reflect the actual environment.
* Inheritance and customer responsibilities are documented.
* Evidence is mapped and retrievable.
* Security documentation is ready for internal assessment-readiness review.

### Outputs

* Control Implementation Matrix
* CIS / CRM
* Secure Configuration Guide
* SSP Control Narratives
* Evidence Matrix
* Supporting Security Documentation

📁 **Portfolio Evidence:**

* [`02-Control-Implementation/Control-Implementation-Matrix.xlsx`](../02-Control-Implementation/Control-Implementation-Matrix.xlsx)
* [`03-SSP/SSP-Control-Narratives.md`](../03-SSP/SSP-Control-Narratives.md)
* [`03-SSP/Evidence-Matrix.xlsx`](../03-SSP/Evidence-Matrix.xlsx)

---

## Phase 3 — Assessment Readiness & Independent 3PAO Assessment

### Objective

Demonstrate that the documented controls operate as represented and support independent assessment by the 3PAO.

### Internal Readiness

KTech performs an internal readiness review covering:

* SSP consistency
* Control implementation
* Evidence completeness and currency
* Control ownership
* Inheritance
* Customer responsibilities
* Vulnerability status
* Configuration status
* SME readiness
* Known security deficiencies
* Documentation consistency

The authorization boundary, architecture, data flows, inventory, SSP, responsibility information, policies, procedures, and supporting evidence should tell the same security story.

### Independent Assessment

The **3PAO performs the independent assessment**.

The 3PAO:

* Develops the Security Assessment Plan (SAP)
* Defines assessment scope and methodology
* Performs applicable control assessment
* Conducts interviews
* Reviews evidence
* Performs applicable technical testing
* Conducts applicable vulnerability and penetration testing
* Documents assessment findings
* Develops the Security Assessment Report (SAR)

KTech supports the assessment by coordinating SMEs, evidence requests, technical-testing activities, clarification requests, and responses.

### Assessment Flow

**Readiness Review → SAP → Evidence Collection → Independent Testing → Findings → SAR**

### Phase Gate

Phase 3 is complete when:

* Independent testing is completed.
* Assessment findings are documented.
* The SAR is delivered.
* Findings requiring remediation or risk treatment are identified.

### Outputs

* Assessment Readiness Review
* Evidence Request Tracker
* SAP — 3PAO artifact
* Assessment Findings
* SAR — 3PAO artifact

📁 **Portfolio Evidence:**

* [`04-3PAO-Assessment/Assessment-Readiness.md`](../04-3PAO-Assessment/Assessment-Readiness.md)
* [`04-3PAO-Assessment/Evidence-Request-Tracker.xlsx`](../04-3PAO-Assessment/Evidence-Request-Tracker.xlsx)
* [`04-3PAO-Assessment/SAR-Findings-Summary.xlsx`](../04-3PAO-Assessment/SAR-Findings-Summary.xlsx)

---

## Phase 4 — Findings, Vulnerability Response & Corrective Action

### Objective

Convert security findings and vulnerabilities into risk-informed, owned, measurable corrective actions and validate remediation before closure.

### Assessment Findings

KTech:

* Validates assessment findings.
* Identifies affected resources.
* Determines security and business impact.
* Assigns corrective-action owners.
* Establishes remediation activities.
* Maintains remediation evidence.
* Performs rescanning, retesting, or validation.
* Closes findings only after sufficient evidence demonstrates effective remediation.

### Vulnerability Detection & Response

For the late-2026 simulated environment, KTech transitions vulnerability operations to the applicable **Vulnerability Detection and Response (VDR)** and **Vulnerability Evaluation and Reporting (VER)** model.

The vulnerability lifecycle is:

**Detect → Evaluate → Determine PAIN → Determine Exploitability → Determine Reachability → Prioritize → Mitigate / Remediate → Verify → Report → Monitor**

KTech evaluates vulnerabilities using factors including:

* **Potential Agency Impact N-rating (PAIN)**
* Likely Exploitable Vulnerability (LEV) status
* Internet-Reachable Vulnerability (IRV) status
* Not Internet-Reachable Vulnerability (NIRV) status
* Known exploitation
* Affected information resources
* Existing mitigations
* Federal/customer impact

### PAIN-Based Response

Applicable remediation and mitigation timelines are determined by the FedRAMP VDR model rather than relying exclusively on the legacy severity-based 30/90/180-day approach.

The portfolio therefore treats **30/90/180 days as legacy Rev. 5 context**, while the simulated late-2026 vulnerability-management process transitions to VDR/VER.

### Accepted Vulnerabilities

A vulnerability that is not or will not be fully mitigated or remediated within the applicable FedRAMP period is evaluated and tracked according to the **Accepted Vulnerability** requirements.

Vulnerabilities that remain unresolved for **192 days following evaluation** are categorized as Accepted Vulnerabilities in accordance with applicable VER requirements.

Acceptance does not mean that the vulnerability disappears from security oversight. Accepted vulnerabilities remain visible to appropriate stakeholders and continue to inform risk decisions.

### POA&M Position

The portfolio retains a POA&M artifact to demonstrate knowledge of:

* Traditional Rev. 5 authorization practices
* NIST RMF corrective-action management
* Agency-owned remediation actions
* Internal risk and corrective-action tracking

However, KTech does **not** treat the traditional CSP POA&M as a substitute for the current VDR/VER vulnerability reporting process.

Provider vulnerability information is maintained through the applicable vulnerability-management and reporting process.

Agency POA&Ms are maintained where the agency has a risk, weakness, decision, or corrective action that the agency itself is responsible for managing or accepting.

### Remediation Flow

**Finding / Vulnerability → Validate → Evaluate → Prioritize → Assign Owner → Mitigate / Remediate → Verify → Report → Close or Accept**

### Phase Gate

Phase 4 is complete for authorization purposes when:

* Material assessment findings have appropriate corrective actions.
* Required pre-authorization remediation is complete or appropriately dispositioned.
* Supporting evidence is available.
* Remediation has been independently validated where required.
* Residual risks are clearly documented.

### Outputs

* Vulnerability Register
* Corrective Action Tracker
* Legacy / Agency POA&M Example
* Remediation Evidence
* Validation / Retest Results
* Vulnerability Activity Reporting
* Updated Risk Register

📁 **Portfolio Evidence:**

* [`05-POAM/KTECH_POAM.xlsx`](../05-POAM/KTECH_POAM.xlsx)
* [`06-Vulnerability-Management/Vulnerability-Register.xlsx`](../06-Vulnerability-Management/Vulnerability-Register.xlsx)
* [`06-Vulnerability-Management/Remediation-Workflow.md`](../06-Vulnerability-Management/Remediation-Workflow.md)
* [`08-Risk-Management/Cloud-Risk-Register.xlsx`](../08-Risk-Management/Cloud-Risk-Register.xlsx)

---

## Phase 5 — Authorization & Certification Decision Support

### Objective

Provide the Authorizing Official, agency stakeholders, and applicable FedRAMP stakeholders with sufficient security and risk information to support authorization and certification decisions.

### Key Activities

* Review the authorization package for completeness.
* Validate consistency across architecture, boundary, SSP, evidence, assessment results, and risk information.
* Review control responsibilities and inheritance.
* Review SAR findings.
* Review corrective actions and vulnerability status.
* Evaluate residual risk.
* Resolve material documentation inconsistencies.
* Support agency clarification requests.
* Support the Authorizing Official's risk decision.
* Maintain applicable FedRAMP certification and Marketplace information.

### Authorization Decision

The **Authorizing Official (AO)** makes the agency's risk-based authorization decision.

KTech supports the decision by ensuring that security and risk information is:

**Accurate → Current → Traceable → Evidence-Based**

The agency authorization identifies the approved use, information, boundary, configurations, restrictions, and conditions for continued use.

### Phase Gate

Phase 5 is complete when:

* The authorization package is complete.
* Material residual risks are understood.
* Required risk decisions have been documented.
* The agency's authorization decision has been made.
* Applicable FedRAMP authorization/certification information has been provided.

### Outputs

* Authorization Package
* Residual Risk Summary
* Authorization Decision Support
* Agency ATO
* Applicable FedRAMP Certification / Marketplace Records

📁 **Supporting Portfolio Areas:**

* [`03-SSP/`](../03-SSP/)
* [`04-3PAO-Assessment/`](../04-3PAO-Assessment/)
* [`05-POAM/`](../05-POAM/)
* [`08-Risk-Management/`](../08-Risk-Management/)

---

## Phase 6 — Continuous Monitoring & Ongoing Authorization

### Objective

Maintain continuous visibility into KTech HealthCloud's security posture and provide current security information supporting ongoing FedRAMP certification and agency authorization decisions.

Authorization is **not** the end of the security lifecycle.

KTech operates a Continuous Monitoring program integrating:

* Control monitoring
* Vulnerability detection and response
* Vulnerability evaluation and reporting
* Corrective-action management
* Independent validation
* Configuration management
* Significant-change management
* Incident response
* Risk management
* Security metrics
* Ongoing security reporting

### Continuous Security Monitoring

KTech continuously monitors:

* Security-relevant system behavior
* Vulnerabilities and exposures
* Configuration drift
* Security events
* Incidents
* Changes to architecture
* Changes to external connections
* Changes to underlying dependencies
* Inherited-service changes
* Security-control effectiveness
* Changes in risk posture

### Vulnerability Detection & Response

Vulnerability management operates as a continuous risk process.

**Detect → Evaluate → PAIN → Exploitability → Reachability → Prioritize → Mitigate / Remediate → Verify → Report**

KTech maintains vulnerability information sufficient to determine:

* Affected information resources
* Potential agency impact
* Likely exploitability
* Internet reachability
* Mitigation status
* Remediation status
* Accepted-vulnerability status
* Overdue status
* Corrective-action ownership

### Monthly Vulnerability Reporting

KTech reports vulnerability detection and response activity to the necessary parties in a consistent **human-readable format at least monthly**.

The monthly reporting process provides visibility into:

* New vulnerabilities
* Open vulnerabilities
* PAIN ratings
* Exploitability
* Internet reachability
* Mitigation status
* Remediation status
* Accepted vulnerabilities
* Overdue vulnerabilities
* Vulnerability trends

### Accepted Vulnerability Review

Vulnerabilities that are not or will not be fully mitigated or remediated within **192 days of evaluation** are categorized as Accepted Vulnerabilities.

Accepted vulnerabilities remain visible in security reporting and are considered in ongoing risk and authorization decisions.

### Corrective Actions & Agency POA&M

Provider vulnerability information is maintained through VDR/VER-aligned vulnerability management and reporting.

Agency POA&Ms are created and maintained when the agency has a risk, decision, weakness, mitigation, or corrective action that it is responsible for managing or accepting.

This prevents provider vulnerability lists from being automatically duplicated into agency POA&Ms.

### Configuration & Significant Change Management

KTech continuously evaluates system changes for potential impact on:

* Authorization boundary
* Architecture
* Data flows
* System components
* External connections
* Security controls
* Control inheritance
* Customer responsibilities
* Secure configurations
* Supporting evidence
* Vulnerability exposure
* Overall risk posture

Changes meeting applicable FedRAMP significant-change criteria are managed through the applicable **Significant Change Notification** process.

### Secure Configuration Management

KTech maintains a **Secure Configuration Guide** describing how customers securely configure and operate relevant security settings.

The guide supports:

* Administrative-account security
* Privileged-account configuration
* Security-sensitive customer settings
* Recommended secure configurations
* Customer security responsibilities

### Incident Evaluation & Response

Security events and incidents identified through continuous monitoring feed into the incident-response process.

Incident activity can trigger:

* Investigation
* Containment
* Mitigation
* Remediation
* Control reassessment
* Risk-register updates
* Corrective actions
* Evidence updates
* Agency/FedRAMP communications
* Authorization-impact evaluation

Incident reporting and communications follow the applicable FedRAMP incident requirements in effect for the CSO.

### Independent Verification & Validation

Applicable independent assessment and validation activities provide assurance that security information remains accurate and that corrective actions operate as intended.

Validation activities can include:

* Control validation
* Technical testing
* Remediation retesting
* Vulnerability validation
* Penetration testing
* Significant-change assessment
* Verification of certification information

### Security Metrics & Reporting

KTech maintains security metrics covering:

* Vulnerability exposure
* PAIN distribution
* Vulnerability aging
* Accepted vulnerabilities
* Overdue vulnerabilities
* Remediation performance
* Corrective-action status
* Control effectiveness
* Configuration drift
* Significant changes
* Security incidents
* Risk trends
* Assessment findings
* Validation status

### Continuous Monitoring Cycle

**Monitor → Detect → Evaluate → Prioritize → Mitigate / Remediate → Verify → Report → Assess Change → Update Risk → Support Ongoing Authorization → Repeat**

### Outputs

* Continuous Monitoring Plan
* ConMon Calendar
* Vulnerability Register
* Monthly Vulnerability Activity Report
* Corrective Action Tracker
* Updated Risk Register
* Metrics Dashboard
* Configuration / Change Records
* Significant Change Assessments
* Incident Records
* Secure Configuration Guide
* Independent Validation Evidence
* Ongoing Authorization Evidence

📁 **Portfolio Evidence:**

* [`07-Continuous-Monitoring/ConMon-Plan.md`](../07-Continuous-Monitoring/ConMon-Plan.md)
* [`07-Continuous-Monitoring/ConMon-Calendar.xlsx`](../07-Continuous-Monitoring/ConMon-Calendar.xlsx)
* [`07-Continuous-Monitoring/Metrics-Dashboard.xlsx`](../07-Continuous-Monitoring/Metrics-Dashboard.xlsx)
* [`06-Vulnerability-Management/Vulnerability-Register.xlsx`](../06-Vulnerability-Management/Vulnerability-Register.xlsx)
* [`08-Risk-Management/Cloud-Risk-Register.xlsx`](../08-Risk-Management/Cloud-Risk-Register.xlsx)
* [`09-Incident-Response/`](../09-Incident-Response/)
* [`10-Configuration-Management/`](../10-Configuration-Management/)

Findings identified during Continuous Monitoring—including vulnerabilities, control deficiencies, incidents, configuration drift, inherited-service changes, and material system changes—feed back into corrective actions, risk management, control documentation, and ongoing authorization activities.

---

## Healthcare Overlay — FedRAMP × HIPAA/HITECH

Because KTech HealthCloud processes simulated PHI on behalf of a fictitious covered-entity federal healthcare customer, applicable HIPAA/HITECH security requirements are considered as an additional compliance overlay to the FedRAMP Moderate baseline.

HIPAA/HITECH does **not replace, reduce, or modify the FedRAMP Moderate baseline**.

For this simulated scenario, KTech operates as a **business associate** when processing PHI on behalf of the covered-entity customer, with applicable responsibilities documented through a simulated **Business Associate Agreement (BAA)**.

Where requirements overlap, KTech maps security implementations and supporting evidence to multiple applicable obligations while maintaining traceability.

| HIPAA Security Rule Requirement                   | Example Related NIST SP 800-53 Controls |
| ------------------------------------------------- | --------------------------------------- |
| **Risk Analysis — §164.308(a)(1)(ii)(A)**         | RA-3                                    |
| **Risk Management — §164.308(a)(1)(ii)(B)**       | RA-7, PM-9                              |
| **Sanction Policy — §164.308(a)(1)(ii)(C)**       | PS-8                                    |
| **Workforce Security — §164.308(a)(3)**           | AC-2, PS-2, PS-3                        |
| **Contingency Plan — §164.308(a)(7)**             | CP-2, CP-9, CP-10                       |
| **Access Control — §164.312(a)**                  | AC-2, AC-3, AC-6, IA-2                  |
| **Encryption & Decryption — §164.312(a)(2)(iv)**  | SC-28                                   |
| **Audit Controls — §164.312(b)**                  | AU-2, AU-6, AU-12                       |
| **Integrity — §164.312(c)**                       | SI-7                                    |
| **Person or Entity Authentication — §164.312(d)** | IA-2                                    |
| **Transmission Security — §164.312(e)**           | SC-8, SC-13                             |
| **Security Incident Procedures — §164.308(a)(6)** | IR-4, IR-6, IR-8                        |

> These mappings are **illustrative portfolio crosswalks**. Mapping a HIPAA requirement to a NIST SP 800-53 control does not by itself establish compliance. Applicability, implementation, evidence, and the specific HIPAA requirement must still be evaluated.

---

## Program Deliverables

The completed KTech roadmap is designed to produce the following connected portfolio artifacts:

| Program Area                 | Primary Artifact                                |
| ---------------------------- | ----------------------------------------------- |
| **Categorization**           | FIPS 199 Security Categorization                |
| **Architecture**             | System Architecture Diagram                     |
| **Boundary**                 | Authorization Boundary Diagram                  |
| **Data Flows**               | Data Flow Diagram                               |
| **Inventory**                | System / Service Inventory                      |
| **Responsibility**           | CIS / CRM + Secure Configuration Guide          |
| **Controls**                 | Control Implementation Matrix                   |
| **Security Documentation**   | SSP Control Narratives                          |
| **Evidence**                 | Evidence Matrix                                 |
| **Assessment**               | Assessment Readiness + Evidence Request Tracker |
| **Assessment Results**       | SAR Findings Summary                            |
| **Vulnerability Management** | VDR/VER-aligned Vulnerability Register          |
| **Corrective Actions**       | Corrective Action Tracker / POA&M Example       |
| **Risk Management**          | Cloud Risk Register                             |
| **Continuous Monitoring**    | ConMon Plan + Calendar                          |
| **Metrics**                  | Security Metrics Dashboard                      |
| **Incident Response**        | Incident Response Workflow                      |
| **Change Management**        | Configuration / Significant Change Tracker      |

---

## Lifecycle

```text
Scope & Categorize
        ↓
Architecture & Boundary
        ↓
Responsibility & Inheritance
        ↓
Implement Controls
        ↓
SSP & Evidence
        ↓
Assessment Readiness
        ↓
Independent 3PAO Assessment
        ↓
Findings & Vulnerability Response
        ↓
Corrective Action & Validation
        ↓
Authorization Decision
        ↓
Continuous Monitoring
        ↓
Ongoing Authorization
        ↺
```

> **Lifecycle Principle:** FedRAMP authorization is not a one-time compliance exercise. Architecture changes, vulnerabilities, assessment findings, incidents, inherited-service changes, configuration drift, accepted vulnerabilities, and emerging risks continuously feed back into security implementation, validation, corrective action, risk management, documentation, and ongoing authorization.
