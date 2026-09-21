# KTech HealthCloud — FedRAMP Moderate Authorization Roadmap

> Simulated program artifact. See repository root README for the portfolio disclaimer.

## Purpose

This roadmap defines the end-to-end path KTech HealthCloud follows to reach and maintain a FedRAMP Moderate Agency Authority to Operate (ATO), and shows how each phase's outputs feed the next.

## Program summary

| Item | Detail |
|---|---|
| CSO | KTech HealthCloud (multi-tenant SaaS) |
| Impact Level | Moderate (FIPS 199: Confidentiality=Moderate, Integrity=Moderate, Availability=Moderate) |
| Baseline | FedRAMP Tailored LI-SaaS, NIST SP 800-53 Rev. 5 |
| Authorization Path | Agency ATO (single sponsoring federal healthcare agency) |
| Underlying Cloud | AWS GovCloud (US) — FedRAMP High authorized IaaS, controls inherited where applicable |
| 3PAO | Meridian Assurance Partners (fictitious, A2LA-accredited for portfolio purposes) |

---

## Phase 1 — Scope & Readiness

**Objective:** Define the authorization boundary and confirm the system is ready to move into control implementation.

- Define the cloud service offering, deployment model (SaaS), and service model boundary diagram
- Identify federal data flows: PII/PHI ingestion, storage, transmission, and destruction
- Categorize the system per FIPS 199 / NIST SP 800-60 → Moderate
- Identify inherited controls from the underlying IaaS (AWS GovCloud)
- Identify stakeholders: Information System Owner (ISO), ISSO, Authorizing Official (AO), sponsoring agency, 3PAO
- Perform an initial gap/readiness assessment against the Tailored LI-SaaS baseline
- **Output:** System boundary diagram, initial control applicability list, gap assessment summary

## Phase 2 — Control Implementation & Documentation

**Objective:** Implement the required controls and document them in an assessor-ready SSP.

- Establish the applicable control baseline (FedRAMP Tailored LI-SaaS, ~130+ controls)
- Assign control ownership across Cloud Engineering, IAM, SOC, and GRC
- Implement technical controls (identity, logging, encryption, boundary protection) and administrative controls (policy, procedure)
- Develop control implementation narratives (assessor-readable "how," not just "what")
- Build the SSP and supporting policies (Incident Response Plan, Configuration Management Plan, Contingency Plan, Rules of Behavior)
- **Output:** [`02-Control-Implementation/Control-Implementation-Matrix.xlsx`](../02-Control-Implementation/Control-Implementation-Matrix.xlsx), [`03-SSP/SSP-Control-Narratives.md`](../03-SSP/SSP-Control-Narratives.md)

## Phase 3 — Assessment Readiness & 3PAO Assessment

**Objective:** Prove the controls work, then have that proof independently validated.

- Internal readiness review: control self-testing, evidence completeness check
- Vulnerability scanning and penetration-test preparation (authenticated OS/DB scans, web app scans)
- 3PAO develops the Security Assessment Plan (SAP); KTech reviews scope and rules of engagement
- 3PAO executes testing: control testing, vulnerability scanning, penetration testing, interviews
- 3PAO documents findings and delivers the Security Assessment Report (SAR)
- **Output:** [`04-3PAO-Assessment/Assessment-Readiness.md`](../04-3PAO-Assessment/Assessment-Readiness.md), [`04-3PAO-Assessment/Evidence-Request-Tracker.xlsx`](../04-3PAO-Assessment/Evidence-Request-Tracker.xlsx)

## Phase 4 — Remediation & POA&M

**Objective:** Convert findings into tracked, owned, closed corrective actions.

- Analyze SAR findings: severity, exploitability, affected assets
- Establish remediation owners and risk-based due dates (30/90/180-day SLAs by severity)
- Document weaknesses in the Plan of Action & Milestones (POA&M)
- Validate corrective actions (rescan, re-test) before closure
- Prepare the final authorization package (SSP + SAP + SAR + POA&M + policies)
- **Output:** [`05-POAM/POAM.xlsx`](../05-POAM/POAM.xlsx)

## Phase 5 — Authorization

**Objective:** Obtain the Agency ATO.

- Authorizing Official reviews the full package: SSP, SAR, POA&M, and supporting evidence
- Risk-based authorization decision, with any residual risk formally accepted or conditioned
- ATO letter issued with authorization boundary, conditions, and expiration/reauthorization terms
- **Output:** Authorization decision record (summarized in this roadmap; full ATO letter is out of scope for this portfolio)

## Phase 6 — Continuous Monitoring (Ongoing)

**Objective:** Maintain the authorization through the system's operational life.

- Monthly: authenticated vulnerability scans, POA&M updates, asset/inventory reconciliation, configuration/change review, incident status reporting
- Quarterly: control reviews (sampling), access recertification, risk register review, contingency/IR exercises as applicable
- Annual: significant change review, annual assessment (subset of controls), penetration test, policy review
- **Output:** [`07-Continuous-Monitoring/ConMon-Plan.md`](../07-Continuous-Monitoring/ConMon-Plan.md), [`07-Continuous-Monitoring/ConMon-Calendar.xlsx`](../07-Continuous-Monitoring/ConMon-Calendar.xlsx), [`07-Continuous-Monitoring/Metrics-Dashboard.xlsx`](../07-Continuous-Monitoring/Metrics-Dashboard.xlsx)

Findings identified during ConMon (new vulnerabilities, control drift, incidents) flow back into the POA&M (Phase 4) and Risk Register, closing the lifecycle loop.

---

## Healthcare overlay: FedRAMP × HIPAA/HITECH

Because KTech HealthCloud processes PHI on behalf of covered-entity federal healthcare customers, the program layers HIPAA Security Rule safeguards onto the FedRAMP Moderate baseline rather than treating them as separate programs:

| HIPAA Security Rule Safeguard | Mapped FedRAMP/NIST 800-53 Controls |
|---|---|
| Access Control (§164.312(a)) | AC-2, AC-3, AC-6, IA-2 |
| Audit Controls (§164.312(b)) | AU-2, AU-6, AU-12 |
| Integrity (§164.312(c)) | SI-7, SC-8 |
| Transmission Security (§164.312(e)) | SC-8, SC-13 |
| Encryption at Rest (§164.312(a)(2)(iv)) | SC-28 |
| Contingency Plan (§164.308(a)(7)) | CP-2, CP-9, CP-10 |
| Security Incident Procedures (§164.308(a)(6)) | IR-4, IR-6, IR-8 |
| Workforce Security / Sanctions (§164.308(a)(3)) | PS-3, PS-8 |

This mapping is referenced in the SSP control narratives (`03-SSP/`) wherever a control also satisfies a HIPAA safeguard, so a single control implementation and a single piece of evidence serve both compliance obligations.
