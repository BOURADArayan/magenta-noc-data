# NOC RUNBOOK — Site DT-4501 Sector S3 Recovery
Version 2.1 | May 2025 | SANITIZED

## S.4.1 — BBU Firmware Version Check
1. Access BBU remote management console for DT-4501.
2. Navigate to: System > Software > Running Version.
3. Compare version against Golden Config Register (GCR).
4. Golden version May 2025: BBU-FW-9x-v4.7.2.
5. If version matches GCR: proceed to S.4.3.
6. If version does NOT match: proceed to S.4.2.

## S.4.2 — Sector Reset Procedure (Firmware Regression Confirmed)
1. Confirm S1 and S2 are nominal - KPIs within threshold.
2. Notify shift supervisor: Executing S3 reset on DT-4501, ETA 8 minutes.
3. BBU console: Sector Management > S3 > Maintenance Mode ON.
4. Wait 30 seconds for active sessions to migrate to S1/S2.
5. [WARN] Execute: Sector Reset > Soft Reset. Do NOT use Hard Reset without L3 approval.
6. Monitor reset - typical completion 4-6 minutes.
7. After reset: verify BBU firmware auto-reverted to v4.7.2.
8. Turn off Maintenance Mode: Sector Management > S3 > Maintenance Mode OFF.
9. Wait 5 minutes then check RACH, Throughput, RRC - all must reach threshold.
10. If KPIs recover: log in ticket, mark alarm resolved, proceed to S.7.
11. [WARN] If KPIs do NOT recover after 15 min: escalate to Level 3.

## S.7 — Shift Handoff and Ticket Closure
1. Complete shift note using 3-line template.
2. Update ticket with final status.
3. Confirm next operator acknowledged handoff before closing.
