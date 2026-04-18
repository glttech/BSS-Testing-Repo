# QA Live Execution Board

Purpose: shared real-time board for developer + tester. Update this file continuously during each fix/retest cycle so no separate status messages are required.

## How to use
- Developer updates `Dev Status`, `Fix Summary`, `Commit`, `Deployed At`.
- Tester updates `QA Retest`, `Tester`, `Retest Time`, `Notes`.
- Keep newest updates at top.

## Status values
- **Dev Status:** Open / In Progress / Fixed / Won't Fix
- **QA Retest:** Pending / Pass / Fail / Blocked

---

## Current Iteration: P0 Stabilization

| Bug ID | Dev Status | Fix Summary (short) | Commit | Deployed At (UTC) | QA Retest | Tester | Retest Time (UTC) | Notes |
|---|---|---|---|---|---|---|---|---|
| BUG-003 | Fixed | Global search suggestions + navigation for candidates/companies/jobs | 955606e | 2026-04-18 09:06 | Pending |  |  |  |
| BUG-012 | Fixed | In Pipeline dynamic metric + unique candidate counting in active stages | ae22be4, 1526be1 | 2026-04-18 06:18 | Pending |  |  |  |
| BUG-015 | Fixed | Create Login now triggers login setup/reset flow via contact email | 955606e | 2026-04-18 09:06 | Pending |  |  |  |
| BUG-021 | Fixed | Cancel in company edit is non-submit; no accidental update | 955606e | 2026-04-18 09:06 | Pending |  |  |  |
| BUG-022 | Fixed | After create redirect to new company detail + companies list limit expanded | 32f1681 | 2026-04-18 09:13 | Pending |  |  |  |

---

## Agent Comment Stream (append-only)
- 2026-04-18 09:18 UTC — Created shared live execution board for realtime developer/tester collaboration.
- 2026-04-18 09:18 UTC — Seeded P0 fix entries with commit references and deploy timestamps.

---

## Next Updates Protocol
1. When dev pushes fix: update row + add one Agent Comment line.
2. When tester retests: set QA Retest to Pass/Fail and add proof note.
3. If Fail: create follow-up bug or reopen same bug row with new commit.
