# Environment Map

This file defines expected environment-to-build behavior.

## Summary
- If environment mapping is unclear, treat as release blocker.
- If domain behavior differs for same flow, treat as parity blocker.

## Environment Table

| Environment / Domain | Expected Branch | Expected Build Source | API Base URL | Notes |
|---|---|---|---|---|
| `bss-dev.devascend.co.in` | `dev` | latest dev deployment | `https://bss-dev.devascend.co.in/api/v1` | Primary QA target |
| `v.devascend.co.in` (target domain) | **Must be explicitly confirmed** | **Must match target release branch/build** | `https://v.devascend.co.in/api/v1` (expected) | If unreachable or behavior drifts from bss-dev, mark BLOCKER |

## Parity Rule
Any mismatch in one of the below is a blocker until resolved/documented:
- Branch/build mismatch
- API base URL mismatch
- Critical flow behavior mismatch (login, dashboard metrics, careers apply, create login)

## Verification Checklist
- [ ] Confirm deployed branch per domain
- [ ] Confirm API base URL used by frontend per domain
- [ ] Confirm same behavior for P0 flows across domains
- [ ] Record mismatch evidence in `QA_LIVE_EXECUTION_BOARD.md`
