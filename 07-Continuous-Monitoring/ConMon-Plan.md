# KTech HealthCloud — Continuous Monitoring (ConMon) Plan

> Simulated program artifact. See repository root README for the portfolio disclaimer.

## Purpose

Describes how KTech HealthCloud sustains its FedRAMP Moderate authorization after the initial ATO, per FedRAMP ConMon requirements and NIST SP 800-137.

## Monitoring cadence

### Monthly
- Authenticated vulnerability scans (infrastructure + web application) — see `06-Vulnerability-Management/Remediation-Workflow.md`
- POA&M updates: status, evidence of progress, SLA aging
- Asset/software inventory reconciliation
- Configuration and change review (all changes from the prior month, see `10-Configuration-Management/`)
- Incident status reporting (open incidents, closed incidents, lessons learned)
- Metrics dashboard refresh and submission to the Authorizing Official's designated representative

### Quarterly
- Control review (sampling of a control subset, rotating through the full baseline over the authorization cycle)
- Access recertification (privileged and standard accounts)
- Contingency/incident response tabletop exercise (as scheduled)
- Risk register review and re-scoring

### Annual / Periodic
- Significant change review and re-authorization impact analysis
- Annual assessment (a defined control subset re-tested, per FedRAMP annual assessment guidance)
- Penetration test
- Policy and procedure review (IR Plan, Configuration Management Plan, Contingency Plan)
- Annual FIPS 199 categorization review

## Reporting

A monthly ConMon package is delivered to the Authorizing Official's designated representative containing:
1. Executive summary of the month's monitoring activity
2. Updated POA&M export
3. Vulnerability scan summary (counts by severity, SLA compliance)
4. Metrics dashboard (see `Metrics-Dashboard.xlsx`)
5. Significant change log (if any)
6. Incident summary (if any)

## Escalation triggers

The following trigger an out-of-cycle notification to the Authorizing Official rather than waiting for the monthly package:
- Any Critical-severity vulnerability confirmed exploitable in the environment
- Any security incident meeting the US-CERT reporting threshold (see `09-Incident-Response/`)
- Any significant change to the authorization boundary
- Any POA&M item breaching its SLA by more than 30 days without an approved risk acceptance

## Related artifacts

- [`ConMon-Calendar.xlsx`](ConMon-Calendar.xlsx) — the monthly/quarterly/annual activity calendar with owners
- [`Metrics-Dashboard.xlsx`](Metrics-Dashboard.xlsx) — POA&M aging, scan coverage, and evidence-completeness metrics
- [`../05-POAM/POAM.xlsx`](../05-POAM/POAM.xlsx) — source of POA&M metrics
- [`../08-Risk-Management/Cloud-Risk-Register.xlsx`](../08-Risk-Management/Cloud-Risk-Register.xlsx) — quarterly risk review source
