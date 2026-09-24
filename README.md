# FedRAMP Moderate Compliance Portfolio

## KTech HealthCloud — Simulated FedRAMP Moderate Authorization Program

> **Portfolio Disclaimer:** KTech HealthCloud is a **fictitious cloud service offering (CSO)** created to demonstrate FedRAMP and NIST SP 800-53 Rev. 5 governance, risk, compliance, and authorization skills. This is a **simulated authorization program**, not an actual FedRAMP authorization. No real federal agency, 3PAO, customer environment, vendor assessment, or government dataset is represented. All findings, risks, dates, scores, personnel, and assessment results are illustrative.

This portfolio demonstrates a simulated end-to-end **FedRAMP Moderate Rev. 5 authorization and continuous monitoring lifecycle** for a cloud-based healthcare SaaS environment.

The project connects system scoping and architecture, FIPS 199 categorization, authorization boundary definition, control responsibility and inheritance, NIST SP 800-53 Rev. 5 control implementation, System Security Plan (SSP) documentation, 3PAO assessment support, POA&M management, vulnerability management, cloud risk management, configuration management, incident response, and Continuous Monitoring (ConMon).

---

## Start Here

If you are reviewing this portfolio for a FedRAMP, security compliance, or cybersecurity GRC role, I recommend starting with these areas:

1. **[Control Implementation](./02-Control-Implementation/)** — control responsibility, inheritance, implementation status, ownership, evidence, and gap tracking.
2. **[SSP & Evidence](./03-SSP/)** — control implementation narratives and evidence traceability.
3. **[POA&M & Vulnerability Management](./05-POAM/)** — weakness management, remediation ownership, milestones, validation, and closure.
4. **[Continuous Monitoring](./07-Continuous-Monitoring/)** — ongoing control monitoring, vulnerability management, metrics, reporting, and authorization maintenance.

---

## Why This Exists

This repository is a working demonstration of the types of activities and artifacts used to support a FedRAMP authorization program.

Rather than reproducing FedRAMP guidance, the project demonstrates how security requirements can be translated into practical GRC activities, documentation, evidence, assessment readiness, remediation, risk management, and ongoing monitoring.

Each folder represents a component of the simulated authorization lifecycle and can be reviewed independently.

---

## Program Context — Rev. 5 & FedRAMP Modernization

This portfolio intentionally demonstrates a **FedRAMP Moderate Rev. 5 authorization lifecycle** to show practical experience with NIST SP 800-53 control implementation, authorization boundaries, control inheritance and customer responsibilities, SSP documentation, independent assessment, POA&M management, vulnerability management, and continuous monitoring.

FedRAMP is modernizing its authorization and ongoing monitoring model through the **Consolidated Rules for 2026 and FedRAMP 20x**. These changes place greater emphasis on measurable security outcomes, persistent validation, automation, machine-readable security information, current security data, and ongoing risk visibility.

The Rev. 5 methodology demonstrated in this portfolio provides the control, risk, evidence, assessment, and continuous-monitoring foundation needed to understand and support that transition.

Future portfolio enhancements may demonstrate selected modernization concepts such as machine-readable security information, Key Security Indicators (KSIs), automated evidence, and persistent security validation.

---

## The Scenario

**KTech HealthCloud** is a fictitious multi-tenant SaaS platform supporting patient-engagement and care-coordination workflows.

For this portfolio scenario, KTech HealthCloud is hosted within **AWS GovCloud (US)** and is preparing for an **agency-sponsored authorization using the FedRAMP Moderate Rev. 5 baseline** with a fictitious federal healthcare agency partner.

The architecture relies on underlying cloud services for certain security capabilities. Therefore, the program distinguishes between controls and control elements implemented by KTech, those inherited from underlying cloud services, and responsibilities that must be addressed by KTech customers.

Because the simulated environment processes PII and PHI, the scenario also considers applicable HIPAA/HITECH security requirements as an additional compliance overlay. HIPAA/HITECH requirements do not replace or modify the applicable FedRAMP baseline.

| Attribute                         | Value                                                               |
| --------------------------------- | ------------------------------------------------------------------- |
| **Cloud Service Offering**        | KTech HealthCloud (SaaS)                                            |
| **FedRAMP Impact Level**          | Moderate                                                            |
| **Security Baseline**             | FedRAMP Moderate — NIST SP 800-53 Rev. 5                            |
| **Authorization Scenario**        | Agency-sponsored Rev. 5 authorization                               |
| **Underlying Cloud Platform**     | AWS GovCloud (US)                                                   |
| **Control Responsibility**        | KTech-implemented, inherited, shared, and customer responsibilities |
| **Data Types**                    | Simulated PII and PHI                                               |
| **Additional Compliance Overlay** | HIPAA/HITECH                                                        |
| **Independent Assessor**          | Meridian Assurance Partners — fictitious 3PAO                       |

---

## Project Objectives

This project demonstrates practical application of:

* FedRAMP Moderate Rev. 5 authorization readiness
* FIPS 199 security categorization
* Authorization boundary and architecture analysis
* Data-flow and system-component analysis
* NIST SP 800-53 Rev. 5 security controls
* Control responsibility and inheritance analysis
* Customer responsibility identification
* Security control implementation and evidence traceability
* System Security Plan (SSP) documentation
* 3PAO assessment readiness and coordination
* Security Assessment Plan (SAP) and Security Assessment Report (SAR) lifecycle awareness
* Plan of Action & Milestones (POA&M) management
* Vulnerability detection, evaluation, remediation, and validation
* Cloud security risk management
* Continuous Monitoring (ConMon)
* Significant change evaluation
* Incident response and reporting
* Configuration and change management
* Authorization decision support
* Ongoing security and risk reporting
* Awareness of FedRAMP 2026 modernization and 20x concepts

---

## FedRAMP Authorization Lifecycle

The following provides a simplified view of the Rev. 5 authorization lifecycle represented by this portfolio.

```text
┌───────────────────────────┐
│ 1. Scope & Readiness      │
└─────────────┬─────────────┘
              ↓
┌───────────────────────────┐
│ 2. Control Implementation │
│    + SSP Documentation    │
└─────────────┬─────────────┘
              ↓
┌───────────────────────────┐
│ 3. 3PAO Assessment        │
│    SAP → Test → SAR       │
└─────────────┬─────────────┘
              ↓
┌───────────────────────────┐
│ 4. Remediation & POA&M    │
└─────────────┬─────────────┘
              ↓
┌───────────────────────────┐
│ 5. Authorization Decision │
└─────────────┬─────────────┘
              ↓
┌───────────────────────────┐
│ 6. Continuous Monitoring  │
│    (Ongoing)              │
└───────────────────────────┘
```

---

## My FedRAMP Authorization Methodology

My methodology expands the simplified authorization lifecycle into eight practical stages, connecting system scoping and architecture, control responsibility and inheritance, control implementation, security documentation, independent assessment, remediation, authorization decision support, and continuous monitoring.

### 1. Scope, Categorize, Establish the Boundary & Understand the Architecture

I begin by understanding the cloud service offering, intended federal use, information types, system architecture, data flows, external services, integrations, dependencies, and authorization boundary.

I establish the security categorization and identify the applicable FedRAMP security requirements.

I review the system architecture to understand how security is implemented across the environment, including system components, network boundaries, identity and access management, data protection, encryption and key management, logging and monitoring, external connections, administrative access paths, trust relationships, and dependencies on underlying cloud services.

I also establish the **control responsibility and inheritance model**. For applicable controls, I determine what KTech implements directly, what capabilities or control elements are inherited from underlying cloud services, and where responsibilities are shared between KTech, underlying providers, and customers.

For inherited or shared responsibilities, I identify what KTech must still implement and what customers must configure or operate to satisfy their responsibilities.

**Key Activities:**
FIPS 199 Categorization → Authorization Boundary → Architecture Review → Data Flows → System Components → External Connections → Control Responsibility & Inheritance Analysis → Authorization Strategy

📁 **Portfolio Evidence:** [FedRAMP Roadmap](./01-FedRAMP-Roadmap/)

---

### 2. Assess Readiness & Perform Gap Analysis

I evaluate the system against the applicable **FedRAMP Moderate Rev. 5 baseline** and NIST SP 800-53 Rev. 5 requirements to establish the current security and compliance posture.

For each applicable control and control enhancement, I identify the implementation status, responsible control owner, applicable inheritance or customer responsibility, available supporting evidence, identified deficiencies, and required corrective actions.

For controls that rely on an underlying cloud provider, I validate the applicable inheritance and identify any KTech or customer responsibilities that must still be implemented.

**Methodology:**
Control Requirement → Responsibility & Inheritance → Implementation Status → Control Owner → Evidence → Gap → Remediation

📁 **Portfolio Evidence:** [Control Implementation](./02-Control-Implementation/)

---

### 3. Build the SSP & Evidence Package

I develop and maintain the **System Security Plan (SSP)** so that control implementation statements accurately reflect how security controls are implemented within the KTech environment.

Control documentation explains who is responsible for the control, what security mechanism or process implements it, where and how the control operates, what portions are inherited or shared, what customer responsibilities remain, and what evidence demonstrates implementation and operation.

Where controls or control elements are inherited, I identify the underlying service dependency and document KTech's remaining responsibilities rather than treating inherited implementation as KTech's own implementation.

I maintain traceability between security requirements, implementation statements, control ownership, inheritance, customer responsibilities, and supporting evidence.

**Methodology:**
Control → Responsibility & Inheritance → Implementation Narrative → Responsible Owner → Evidence → Validation

📁 **Portfolio Evidence:**

* [SSP Control Narratives](./03-SSP/SSP-Control-Narratives.md)
* [SSP Evidence Matrix](./03-SSP/Evidence-Matrix.xlsx)

---

### 4. Prepare for Independent Assessment

Before formal assessment activities begin, I perform an internal readiness review to determine whether the system, documentation, control implementations, control owners, and supporting evidence are prepared for independent assessment.

I validate that SSP implementation statements align with the actual environment, inherited and customer responsibilities are accurately represented, supporting evidence is current and retrievable, known deficiencies are documented, and SMEs understand their responsibilities during the assessment.

I also review documentation for consistency so that the authorization boundary, architecture, data flows, SSP, control responsibility information, inventories, policies, procedures, and supporting evidence tell the same security story.

**Methodology:**
Readiness Review → Documentation Consistency → Evidence Validation → SME Coordination → Gap Resolution → Assessment Preparation

📁 **Portfolio Evidence:**

* [Assessment Readiness](./04-3PAO-Assessment/Assessment-Readiness.md)
* [Evidence Request Tracker](./04-3PAO-Assessment/Evidence-Request-Tracker.xlsx)

---

### 5. Support the 3PAO Assessment

I coordinate with the **Third Party Assessment Organization (3PAO)**, system owners, engineers, security teams, and control owners throughout the independent security assessment.

The 3PAO develops the Security Assessment Plan (SAP) and independently assesses the applicable security controls and technical implementation.

From the CSP perspective, I support assessment planning, review the SAP, coordinate evidence requests, facilitate SME interviews and technical testing, respond to assessor questions, and help ensure requested evidence is complete and traceable.

Assessment results and identified risks are documented by the 3PAO in the **Security Assessment Report (SAR)**.

**Assessment Flow:**
SAP → Evidence Collection → Control Assessment & Technical Testing → Findings → SAR

📁 **Portfolio Evidence:**

* [3PAO Assessment Readiness](./04-3PAO-Assessment/)
* [SAR Findings Summary](./04-3PAO-Assessment/SAR-Findings-Summary.xlsx)

---

### 6. Manage Findings, Remediation & POA&M

I coordinate the management of security weaknesses identified through assessment activities, vulnerability detection, control testing, operational monitoring, and other security processes.

Findings are validated, evaluated for risk, assigned to responsible owners, and tracked through corrective action.

Where applicable, unresolved weaknesses are documented and managed through the **Plan of Action & Milestones (POA&M)** process.

I maintain traceability between findings, risks, corrective actions, responsible owners, milestones, remediation evidence, validation, and closure.

Remediation is not considered complete solely because an action is reported as finished. Supporting evidence and, where appropriate, retesting or validation are used to confirm that the weakness has been effectively addressed.

**Remediation Flow:**
Finding → Validate → Evaluate Risk → Assign Owner → POA&M / Corrective Action → Mitigate or Remediate → Validate or Retest → Close

📁 **Portfolio Evidence:**

* [POA&M](./05-POAM/)
* [KTech POA&M](./05-POAM/KTECH_POAM.xlsx)
* [Vulnerability Management](./06-Vulnerability-Management/)
* [Vulnerability Register](./06-Vulnerability-Management/Vulnerability-Register.xlsx)
* [Remediation Workflow](./06-Vulnerability-Management/Remediation-Workflow.md)

---

### 7. Support the Authorization Decision

I support the authorization process by ensuring the security authorization package accurately communicates the system's architecture and authorization boundary, control implementations, control responsibilities and inheritance, assessment results, identified weaknesses, remediation status, and residual risk.

I help ensure consistency and traceability across the SSP, supporting evidence, assessment results, SAR, POA&M, risk information, and related authorization artifacts.

The objective is to provide the **Authorizing Official (AO)** and relevant stakeholders with sufficient security and risk information to make an informed, risk-based authorization decision.

**Methodology:**
SSP + Control Evidence + Assessment Results + SAR + POA&M + Residual Risk → AO Risk Decision

📁 **Supporting Portfolio Areas:**

* [SSP](./03-SSP/)
* [3PAO Assessment](./04-3PAO-Assessment/)
* [POA&M](./05-POAM/)
* [Risk Management](./08-Risk-Management/)

---

### 8. Transition to Continuous Monitoring

Authorization is not the end of the security lifecycle.

I transition the system into **Continuous Monitoring (ConMon)** to maintain ongoing visibility into control effectiveness, vulnerabilities and exposures, configuration and system changes, incidents, outstanding weaknesses, and changes to the system's risk posture.

My continuous monitoring approach includes:

* Ongoing control monitoring and assessment
* Persistent vulnerability detection, evaluation, prioritization, mitigation, and remediation
* Verification and validation of remediation status
* POA&M and corrective-action management
* Configuration and change monitoring
* Evaluation and notification of significant changes
* Incident detection, evaluation, response, and reporting
* Risk analysis and risk-register updates
* Security metrics and trend analysis
* Security-status and ongoing authorization reporting
* Coordination with system owners, engineers, security teams, assessors, and agency stakeholders

Vulnerability management is treated as an ongoing risk process rather than a periodic compliance exercise. Findings are evaluated using applicable FedRAMP vulnerability requirements and tracked through mitigation, remediation, validation, and closure.

Significant system changes are evaluated to determine their potential impact on the authorization boundary, architecture, data flows, control implementation, inherited responsibilities, supporting evidence, and overall risk posture. Changes requiring additional assessment or notification are escalated through the appropriate process.

Incident-response activities are integrated with continuous monitoring so that security events and incidents can affect risk assessments, control documentation, POA&M items, corrective actions, and ongoing authorization decisions.

Continuous monitoring results feed back into remediation, risk management, SSP and control documentation, configuration management, and ongoing security decision-making.

**Continuous Monitoring Cycle:**
Control Monitoring & Assessment → Vulnerability Detection & Response → Verification & Validation → POA&M / Corrective Actions → Risk Management → Configuration & Significant Change Management → Incident Response → Security Metrics & Reporting → Ongoing Authorization → Repeat

📁 **Portfolio Evidence:**

* [Continuous Monitoring](./07-Continuous-Monitoring/)
* [ConMon Plan](./07-Continuous-Monitoring/ConMon-Plan.md)
* [ConMon Calendar](./07-Continuous-Monitoring/ConMon-Calendar.xlsx)
* [Metrics Dashboard](./07-Continuous-Monitoring/Metrics-Dashboard.xlsx)
* [Vulnerability Management](./06-Vulnerability-Management/)
* [Vulnerability Register](./06-Vulnerability-Management/Vulnerability-Register.xlsx)
* [Cloud Risk Register](./08-Risk-Management/Cloud-Risk-Register.xlsx)
* [Incident Response](./09-Incident-Response/)
* [Configuration Management](./10-Configuration-Management/)

---

### Lifecycle Principle

> **FedRAMP authorization is not a one-time compliance exercise.** Architecture changes, control performance, vulnerabilities and exposures, security findings, incidents, inherited-service changes, and emerging risks continuously feed back into control implementation, remediation, risk management, security documentation, and ongoing monitoring.

---

## Control-to-Closure Traceability

The KTech portfolio is designed so that a reviewer can follow a security requirement through the authorization lifecycle rather than viewing each artifact as an independent template.

A representative control can be traced through:

```text
NIST / FedRAMP Control Requirement
              ↓
Control Responsibility & Inheritance
              ↓
Implementation / Gap Analysis
              ↓
SSP Control Implementation Statement
              ↓
Supporting Evidence
              ↓
3PAO Assessment & Testing
              ↓
Assessment Finding (if applicable)
              ↓
POA&M / Corrective Action
              ↓
Remediation
              ↓
Validation / Retesting
              ↓
Closure
              ↓
Continuous Monitoring
```

A future portfolio enhancement will provide a worked control example linking the Control Implementation Matrix, SSP narrative, evidence, assessment result, POA&M entry, remediation evidence, and closure validation.

---

## Repository Structure

| Folder                                                           | Contents                                                                                                    | Demonstrates                                                      |
| ---------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------- |
| [`01-FedRAMP-Roadmap/`](./01-FedRAMP-Roadmap/)                   | Authorization roadmap, architecture/scoping artifacts, and healthcare compliance overlay                    | Authorization lifecycle, system scoping & architecture            |
| [`02-Control-Implementation/`](./02-Control-Implementation/)     | Control Implementation Matrix — responsibility, inheritance, implementation status, ownership, and evidence | NIST SP 800-53 control analysis                                   |
| [`03-SSP/`](./03-SSP/)                                           | SSP control implementation narratives and Evidence Matrix                                                   | SSP development, control documentation & evidence traceability    |
| [`04-3PAO-Assessment/`](./04-3PAO-Assessment/)                   | Assessment readiness workflow and Evidence Request Tracker                                                  | 3PAO assessment coordination                                      |
| [`05-POAM/`](./05-POAM/)                                         | Simulated POA&M register                                                                                    | Weakness tracking & remediation management                        |
| [`06-Vulnerability-Management/`](./06-Vulnerability-Management/) | Vulnerability register and remediation workflow                                                             | Vulnerability detection, evaluation, prioritization & remediation |
| [`07-Continuous-Monitoring/`](./07-Continuous-Monitoring/)       | ConMon plan, monitoring calendar and metrics dashboard                                                      | Continuous monitoring, security reporting & ongoing authorization |
| [`08-Risk-Management/`](./08-Risk-Management/)                   | Cloud risk register                                                                                         | Cloud security risk analysis & treatment                          |
| [`09-Incident-Response/`](./09-Incident-Response/)               | FedRAMP-aligned incident response and reporting workflow                                                    | Incident evaluation, response & coordination                      |
| [`10-Configuration-Management/`](./10-Configuration-Management/) | Configuration/change tracker                                                                                | Configuration, change & significant-change governance             |

---

## Planned Portfolio Enhancements

To continue expanding this simulated program, planned enhancements include:

* Authorization boundary and system architecture diagram
* Data-flow diagram
* FIPS 199 security categorization artifact
* CIS/CRM-style control responsibility artifact
* Worked control-to-closure traceability example
* Markdown or image previews of key Excel workbooks
* FedRAMP 20x / machine-readable security demonstration
* Automated or machine-readable security evidence example

---

## Frameworks & Standards

* FedRAMP Rev. 5
* NIST SP 800-53 Rev. 5
* NIST Risk Management Framework (SP 800-37)
* FIPS 199
* FIPS 200
* HIPAA/HITECH — scenario-specific compliance overlay

---

## Disclaimer

All artifacts in this repository are fictitious or simulated and are provided for educational and professional portfolio purposes.
