# KTech HealthCloud — SSP Control Implementation Narratives

> Simulated program artifact. See repository root README for the portfolio disclaimer. These are excerpts from the System Security Plan (SSP), not the full plan.

Each narrative below follows the assessor-facing pattern used in a real SSP: control statement, how it is implemented (technical + procedural), responsible role, and the evidence a 3PAO would sample. Where relevant, the HIPAA Security Rule safeguard the control also satisfies is noted (see `01-FedRAMP-Roadmap/FedRAMP-Authorization-Roadmap.md` for the full crosswalk).

---

### AC-2 — Account Management

**Control statement:** The organization manages information system accounts, including establishment, activation, modification, review, and removal.

**Implementation:** KTech HealthCloud provisions and deprovisions user accounts through Microsoft Entra ID, integrated with the HR system of record via SCIM so that a termination in HR automatically disables the corresponding account within 4 business hours. Account requests for privileged roles require manager and Information System Security Officer (ISSO) approval, tracked in the ticketing system. Accounts are reviewed quarterly by resource owners; inactive accounts (no sign-in for 45 days) are automatically disabled. All account lifecycle events are logged to Microsoft Sentinel.

**Responsible role:** IAM Team (implementation), ISSO (quarterly review approval)

**Evidence:** Entra ID account list export, SCIM provisioning logs, quarterly access review sign-off, disablement/termination logs

---

### AC-6 — Least Privilege

**Control statement:** The organization employs the principle of least privilege, allowing only authorized accesses necessary to accomplish assigned tasks.

**Implementation:** Role-based access control (RBAC) is enforced across the application and infrastructure layers. Standing administrative access is disallowed; privileged roles (database admin, cloud infrastructure admin, security admin) are granted through Microsoft Entra Privileged Identity Management (PIM) as time-bound, eligible assignments requiring justification and approval, with a maximum activation window of 8 hours. PIM activation and de-activation events are logged and reviewed monthly by the ISSO.

**Responsible role:** IAM Team, Cloud Engineering (role definitions)

**Evidence:** PIM role assignment report, RBAC role definitions, monthly PIM activation log review

---

### IA-2 — Identification and Authentication (Organizational Users)

**Control statement:** The information system uniquely identifies and authenticates organizational users.

**Implementation:** KTech HealthCloud uses Microsoft Entra ID as the centralized identity provider for all workforce access. Multi-factor authentication (MFA) is enforced for all interactive sign-ins, and specifically for administrative access, through Conditional Access policies that require a phishing-resistant factor (FIDO2 security key or Microsoft Authenticator with number matching). Privileged roles are managed through PIM (see AC-6) rather than standing access. Authentication events, including MFA failures and Conditional Access policy denials, are forwarded to Microsoft Sentinel for centralized monitoring and investigation.

**Responsible role:** IAM Team

**Evidence:** Conditional Access policy export, PIM role assignment report, MFA enrollment/configuration report, Sentinel authentication log samples

---

### AU-2 — Event Logging

**Control statement:** The organization determines that the information system is capable of auditing defined events and coordinates the security audit function with other organizational entities.

**Implementation:** KTech HealthCloud logs authentication events, authorization changes, administrative actions, data access to PHI-containing tables, and application errors. Logging is enabled by default across the AWS GovCloud environment (CloudTrail, VPC Flow Logs, GuardDuty) and the application tier (structured JSON application logs). The auditable event list is reviewed annually, or after any significant change, by the ISSO and Cloud Engineering to confirm it still covers FedRAMP-required event types.

**Responsible role:** Cloud Engineering, SOC

**Evidence:** Logging configuration export (CloudTrail, VPC Flow Logs), auditable events list, annual review record

---

### AU-6 — Audit Record Review, Analysis, and Reporting

**Control statement:** The organization reviews and analyzes information system audit records for indications of inappropriate or unusual activity.

**Implementation:** All logs are centralized in Microsoft Sentinel, where correlation rules flag anomalous activity (impossible travel, privilege escalation, bulk PHI record access, repeated authentication failures). The SOC reviews high- and medium-severity Sentinel alerts daily and produces a weekly audit review summary for the ISSO. Findings that indicate a possible incident are escalated per the Incident Response Plan (see `09-Incident-Response/`).

**Responsible role:** SOC (daily triage), ISSO (weekly summary review)

**Evidence:** Sentinel analytics rule list, daily triage queue export, weekly audit review summary (sample)

---

### CM-2 — Baseline Configuration

**Control statement:** The organization develops, documents, and maintains a current baseline configuration of the information system.

**Implementation:** Infrastructure is provisioned via Terraform from version-controlled modules that encode the approved secure baseline (CIS-benchmark-aligned AMIs, hardened network ACLs, encrypted storage by default). The baseline is stored in the source repository, and any drift is detected by AWS Config rules that compare running configuration against the Terraform-defined baseline. Baseline changes follow the change management process (see `10-Configuration-Management/`).

**Responsible role:** Cloud Engineering

**Evidence:** Terraform baseline repository export, AWS Config rule compliance report, baseline configuration document

---

### CM-6 — Configuration Settings

**Control statement:** The organization establishes and documents configuration settings for components using security configuration checklists, and monitors and controls changes to those settings.

**Implementation:** Security configuration settings for OS, database, and container images follow CIS Benchmark Level 1 profiles, codified as policy-as-code (Open Policy Agent) checks in the CI/CD pipeline; a build fails if it violates a required setting. AWS Config continuously evaluates deployed resources against the same checklist and raises a finding within the Vulnerability/Configuration register for any non-compliant resource.

**Responsible role:** Cloud Engineering, DevSecOps

**Evidence:** CIS Benchmark checklist mapping, OPA policy repository, AWS Config compliance dashboard export

---

### RA-5 — Vulnerability Monitoring and Scanning

**Control statement:** The organization scans for vulnerabilities in the information system and hosted applications and remediates legitimate vulnerabilities in accordance with an organizational assessment of risk.

**Implementation:** Authenticated vulnerability scans run monthly against all in-scope infrastructure and continuously for container images via the CI/CD pipeline; web application scans run monthly against the production application. Results feed the Vulnerability Register (`06-Vulnerability-Management/Vulnerability-Register.xlsx`), where each finding is triaged by CVSS score, exploitability, and asset criticality, and assigned a remediation SLA (High = 30 days, Moderate = 90 days, Low = 180 days) consistent with FedRAMP timelines. Unremediated findings past SLA are escalated to the POA&M.

**Responsible role:** Vulnerability Management Team, Cloud Engineering (remediation)

**Evidence:** Scan reports (sanitized), Vulnerability Register, POA&M cross-reference for past-due items

---

### SC-7 — Boundary Protection

**Control statement:** The information system monitors and controls communications at the external boundary and key internal boundaries.

**Implementation:** The production environment sits in a dedicated VPC with public-facing components isolated in a DMZ subnet behind a Web Application Firewall (WAF) and an AWS Network Firewall enforcing default-deny egress. Application and database tiers sit in private subnets with no direct internet route. All boundary traffic is logged via VPC Flow Logs and reviewed for anomalies through Sentinel correlation rules (see AU-6).

**Responsible role:** Cloud Engineering, SOC

**Evidence:** Network architecture/boundary diagram, security group and NACL export, WAF rule set, Network Firewall policy

---

### SC-8 — Transmission Confidentiality and Integrity

**Control statement:** The information system protects the confidentiality and integrity of transmitted information.

**Implementation:** All data in transit, both external (client-to-application) and internal (service-to-service, application-to-database), is encrypted using TLS 1.2 or higher. TLS configuration is enforced through the load balancer and validated monthly by an automated TLS/cipher scan; any endpoint offering a deprecated protocol or weak cipher suite is flagged as a finding (see `06-Vulnerability-Management/`). *Also satisfies HIPAA §164.312(e) Transmission Security.*

**Responsible role:** Cloud Engineering

**Evidence:** TLS scan report, load balancer listener configuration, certificate inventory

---

### SC-28 — Protection of Information at Rest

**Control statement:** The information system protects the confidentiality and integrity of information at rest.

**Implementation:** All storage — database volumes, object storage, backups, and snapshots — is encrypted at rest using AES-256 via AWS KMS customer-managed keys. Key rotation is automated annually, and key usage is logged via CloudTrail. Database-level encryption (transparent data encryption) provides a second layer for PHI-containing tables. *Also satisfies HIPAA §164.312(a)(2)(iv) Encryption at Rest.*

**Responsible role:** Cloud Engineering

**Evidence:** KMS key policy export, encryption-at-rest configuration report, CloudTrail key usage log sample

---

### SI-2 — Flaw Remediation

**Control statement:** The organization identifies, reports, and corrects information system flaws.

**Implementation:** Patch management follows a risk-based cadence: critical/high-severity OS and application patches are applied within 15 days of vendor release (or per the SLA in RA-5 if identified via scanning), and routine patches are applied during the monthly maintenance window. Patch status is tracked centrally and reconciled against the Vulnerability Register monthly; emergency (zero-day) patches follow an expedited change process (see `10-Configuration-Management/`).

**Responsible role:** IT Operations, Cloud Engineering

**Evidence:** Patch compliance report, monthly patch reconciliation record, emergency change tickets (sample)

---

## Cross-reference

- Control ownership, implementation status, and inheritance are tracked in [`02-Control-Implementation/Control-Implementation-Matrix.xlsx`](../02-Control-Implementation/Control-Implementation-Matrix.xlsx)
- Evidence referenced above is indexed in [`Evidence-Matrix.xlsx`](Evidence-Matrix.xlsx) with owner and freshness/status
- 3PAO evidence requests drawn from this SSP are tracked in [`04-3PAO-Assessment/Evidence-Request-Tracker.xlsx`](../04-3PAO-Assessment/Evidence-Request-Tracker.xlsx)
