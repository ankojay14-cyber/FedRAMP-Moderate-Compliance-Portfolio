> **Portfolio disclaimer:** KTech HealthCloud is a **fictitious** cloud service offering built to demonstrate FedRAMP/NIST SP 800-53 Rev. 5 GRC skills. This is a **simulated authorization program**, not an actual FedRAMP authorization. No real agency, 3PAO, CSP, vendor tool, or dataset is represented. All findings, scores, dates, and personnel are illustrative.

A simulated FedRAMP Moderate program demonstrating the end-to-end security compliance lifecycle for a cloud-based healthcare SaaS environment — authorization readiness, NIST SP 800-53 control implementation, System Security Plan (SSP) documentation, 3PAO assessment support, POA&M management, vulnerability management, cloud risk assessment, configuration management, incident response, and continuous monitoring (ConMon).

## Why this exists

This repository is a working demonstration of the artifacts a FedRAMP/GRC analyst actually produces day to day — not a copy of FedRAMP guidance. Each folder below is something a hiring manager can open and read on its own.

## The scenario

**KTech HealthCloud** is a multi-tenant SaaS platform (patient engagement + care-coordination workflows) hosted on a major commercial cloud (AWS), pursuing a **FedRAMP Moderate** Authority to Operate (ATO) via the **Tailored LI-SaaS** baseline, sponsored by a federal healthcare agency. Because the tenant data includes PHI, the program also maps FedRAMP controls to HIPAA/HITECH Security Rule safeguards.

| Attribute | Value |
|---|---|
| Cloud Service Offering | KTech HealthCloud (SaaS) |
| FedRAMP Impact Level | Moderate |
| Baseline | FedRAMP Tailored LI-SaaS (NIST SP 800-53 Rev. 5) |
| Authorization Path | Agency ATO |
| Underlying IaaS/PaaS | AWS GovCloud (US) — inherited controls |
| Data Types | PII, PHI (HIPAA/HITECH applicable) |
| 3PAO | Simulated independent assessor ("Meridian Assurance Partners" — fictitious) |

---

## Project Objectives

This project demonstrates practical experience with:

- FedRAMP Moderate authorization readiness
- NIST SP 800-53 security controls
- System Security Plan (SSP) documentation
- Security control implementation and evidence
- 3PAO assessment readiness
- Plan of Action & Milestones (POA&M) management
- Vulnerability management
- Continuous Monitoring (ConMon)
- Cloud security risk management
- Incident response
- Configuration and change management
- Security assessment and remediation tracking

---

## FedRAMP Authorization Lifecycle

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
│ 5. Authorization          │
└─────────────┬─────────────┘
              ↓
┌───────────────────────────┐
│ 6. Continuous Monitoring  │
│    (Ongoing)              │
└───────────────────────────┘
```
---

## Repository structure

| Folder | Contents | Demonstrates |
|---|---|---|
| [`01-FedRAMP-Roadmap/`](01-FedRAMP-Roadmap) | Six-phase authorization roadmap, healthcare (HIPAA/HITECH) overlay | Authorization lifecycle knowledge |
| [`02-Control-Implementation/`](02-Control-Implementation) | Control Implementation Matrix (`.xlsx`) — full Tailored LI-SaaS control list, ownership, status | NIST 800-53 control mapping |
| [`03-SSP/`](03-SSP) | 12 SSP control implementation narratives, Evidence Matrix (`.xlsx`) | SSP development & maintenance |
| [`04-3PAO-Assessment/`](04-3PAO-Assessment) | Assessment readiness workflow (SAP→Test→SAR), Evidence Request Tracker (`.xlsx`) | 3PAO coordination |
| [`05-POAM/`](05-POAM) | POA&M register (`.xlsx`) | Weakness tracking & remediation management |
| [`06-Vulnerability-Management/`](06-Vulnerability-Management) | Vulnerability register (`.xlsx`), remediation workflow | Scan coordination, CVSS triage |
| [`07-Continuous-Monitoring/`](07-Continuous-Monitoring) | ConMon plan, monthly/quarterly/annual calendar (`.xlsx`), metrics dashboard (`.xlsx`) | Ongoing authorization maintenance |
| [`08-Risk-Management/`](08-Risk-Management) | Cloud risk register (`.xlsx`) | Vendor/cloud risk assessment |
| [`09-Incident-Response/`](09-Incident-Response) | FedRAMP incident response & US-CERT reporting workflow | IR coordination with government stakeholders |
| [`10-Configuration-Management/`](10-Configuration-Management) | Configuration/change tracker (`.xlsx`) | Change management documentation |

---
## How the artifacts connect

The environment is scoped (Phase 1) → controls are implemented and written into the SSP (Phase 2) → evidence is staged and the 3PAO tests it (Phase 3) → findings become POA&M items and are remediated (Phase 4) → the package is authorized (Phase 5) → and the program sustains authorization through vulnerability management, configuration management, incident response, and recurring ConMon reporting (Phase 6) — which feeds new findings back into the POA&M, closing the loop.

---

## Frameworks

- FedRAMP
- NIST SP 800-53
- NIST Risk Management Framework (RMF)
- FIPS 199
- FIPS 200

---

## Disclaimer

This repository is a professional cybersecurity portfolio project and does not represent an actual FedRAMP authorization or authorization package.
