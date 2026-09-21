# KTech HealthCloud — FedRAMP Incident Response Workflow

> Simulated program artifact. See repository root README for the portfolio disclaimer.

## Purpose

Defines how KTech HealthCloud detects, responds to, and reports security incidents in a manner consistent with NIST SP 800-61 Rev. 2 and FedRAMP incident reporting requirements (including US-CERT/CISA notification timelines), and how PHI-involving incidents are additionally handled per HIPAA breach notification obligations.

## Workflow

```
Detection (Sentinel alert, scan finding, user report, 3PAO finding)
        ↓
Triage & Validation (SOC)
        ↓
Categorization (NIST 800-61 incident category + severity)
        ↓
Containment
        ↓
Agency / US-CERT Notification (if threshold met)
        ↓
Eradication & Recovery
        ↓
Post-Incident Review ("lessons learned")
        ↓
POA&M / Control Update (if a control gap contributed)
        ↓
ConMon Reporting
```

## Severity and notification timelines

| Category | Example | Notification |
|---|---|---|
| Category 1 — Unauthorized Access | Confirmed account compromise with data access | Report to sponsoring agency and US-CERT within 1 hour of confirmation |
| Category 2 — Denial of Service | Availability-impacting attack | Report within 1 hour if sustained/confirmed |
| Category 4 — Improper Usage | Policy violation without data exposure | Report within agency-defined timeline, typically next business day |
| Category 6 — Investigating | Unconfirmed anomaly under active investigation | Internal tracking; escalate to a numbered category once confirmed |

Timelines above reflect standard federal incident reporting expectations; the actual sponsoring agency's incident communications plan governs the authoritative timeline for a real system.

## Roles

| Role | Responsibility |
|---|---|
| SOC (Tier 1/2) | Detection, triage, initial containment |
| ISSO | Categorization, agency/US-CERT notification, coordination with Authorizing Official |
| Incident Commander (rotating, senior SOC/Eng) | Leads active incident response, coordinates containment/eradication |
| Cloud Engineering | Technical containment and recovery actions |
| Privacy Officer | HIPAA breach notification assessment when PHI is involved |
| GRC | Post-incident POA&M entry, control-gap documentation, ConMon reporting |

## PHI-involving incidents (HIPAA overlay)

When an incident involves actual or suspected unauthorized access to PHI, the Privacy Officer performs a breach risk assessment per the HIPAA Breach Notification Rule (45 CFR §164.402) in parallel with the FedRAMP reporting track, covering:
- Nature and extent of PHI involved
- Identity of the unauthorized recipient, if known
- Whether the PHI was actually viewed/acquired
- Mitigation steps taken

This parallel track does not delay the FedRAMP/US-CERT notification timeline above.

## Post-incident

- A post-incident review ("lessons learned") is documented within 10 business days of closure
- If a control gap contributed to the incident, a POA&M item is opened referencing the affected control (see `../05-POAM/POAM.xlsx`)
- Incident summary (sanitized) is included in the next monthly ConMon package (see `../07-Continuous-Monitoring/ConMon-Plan.md`)

## Related artifacts

- [`../07-Continuous-Monitoring/ConMon-Plan.md`](../07-Continuous-Monitoring/ConMon-Plan.md) — monthly incident status reporting
- [`../05-POAM/POAM.xlsx`](../05-POAM/POAM.xlsx) — control gaps arising from incidents
- [`../03-SSP/SSP-Control-Narratives.md`](../03-SSP/SSP-Control-Narratives.md) — AU-6 (detection), IA-2 (access) controls referenced during investigation
