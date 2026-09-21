# KTech HealthCloud — 3PAO Assessment Readiness

> Simulated program artifact. See repository root README for the portfolio disclaimer. "Meridian Assurance Partners" is a fictitious 3PAO used for this portfolio only.

## Purpose

Documents how KTech HealthCloud prepares for, supports, and responds to an independent Third Party Assessment Organization (3PAO) assessment — the process a Security Compliance Analyst coordinates directly.

## Assessment workflow

```
Pre-Assessment
      ↓
Control Evidence Review
      ↓
Evidence Request List
      ↓
SAP Review (Security Assessment Plan)
      ↓
3PAO Testing (control testing, vuln scanning, pen testing, interviews)
      ↓
Findings
      ↓
SAR (Security Assessment Report)
      ↓
POA&M
      ↓
Remediation
      ↓
Authorization / ConMon
```

## Stage detail

### 1. Pre-Assessment
- Confirm assessment scope and boundary against the current SSP
- Identify any system changes since the last assessment that affect scope
- Assign an internal point of contact (ISSO) for 3PAO coordination

### 2. Control Evidence Review
- GRC team performs an internal walkthrough of each in-scope control against its SSP narrative
- Identify evidence gaps before the 3PAO does (see Evidence Request Tracker below)

### 3. Evidence Request List
- 3PAO issues a formal evidence request list mapped to controls
- GRC logs each request in the Evidence Request Tracker, assigns an internal owner, and tracks status (Ready / Pending / Gap)
- Gaps are remediated or documented with a compensating explanation before testing begins

### 4. SAP Review
- 3PAO drafts the Security Assessment Plan: scope, methodology, rules of engagement, schedule
- KTech reviews and confirms testing windows, notification procedures for production-adjacent testing, and escalation contacts

### 5. 3PAO Testing
- Control testing: interviews, document review, technical verification (screen-shares/evidence walkthroughs)
- Vulnerability scanning: authenticated scans of the full asset inventory
- Penetration testing: external and internal, per SAP rules of engagement
- Findings are discussed informally as identified so there are no surprises in the SAR

### 6. Findings → SAR
- 3PAO documents all findings with control reference, severity (CVSS or risk-adjusted), and recommended remediation
- KTech reviews the draft SAR for factual accuracy before it is finalized

### 7. POA&M
- Every SAR finding becomes a POA&M item with an owner and a due date derived from severity (see `05-POAM/POAM.xlsx`)

### 8. Remediation → Authorization / ConMon
- Findings are remediated and validated (rescan/re-test)
- The authorization package (SSP + SAP + SAR + POA&M) moves to the Authorizing Official
- Post-authorization, the same evidence discipline continues through ConMon (`07-Continuous-Monitoring/`)

## Coordination practices

- Single point of contact (ISSO) for all 3PAO communication to avoid conflicting answers
- Weekly touchpoint during active testing windows
- All evidence provided to the 3PAO is logged (what, when, to whom) for audit trail purposes
- Draft findings are never disputed informally — disagreements are documented in writing and resolved before SAR finalization

## Related artifacts

- [`Evidence-Request-Tracker.xlsx`](Evidence-Request-Tracker.xlsx) — live tracker of evidence requests, owners, and status
- [`../03-SSP/SSP-Control-Narratives.md`](../03-SSP/SSP-Control-Narratives.md) — source narratives evidence is drawn from
- [`../05-POAM/POAM.xlsx`](../05-POAM/POAM.xlsx) — where SAR findings land
