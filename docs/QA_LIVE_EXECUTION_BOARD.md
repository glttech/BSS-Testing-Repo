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

## Current Iteration: P0 + P1 Stabilization

| Bug ID | Severity | Dev Status | Fix Summary (short) | Commit | Deployed At (IST) | QA Retest | Tester | Retest Time (IST) | Notes |
|---|---|---|---|---|---|---|---|---|---|
| BUG-023 | High | Fixed | Follow-up now supports full datetime input and timestamp display in communication + caller flows | 6a0af56 | 2026-04-18 16:26 | Pending |  |  |  |
| BUG-003 | Critical | Fixed | Global search suggestions + navigation for candidates/companies/jobs | 955606e | 2026-04-18 14:36 | Pending |  |  |  |
| BUG-012 | Critical | Fixed | In Pipeline dynamic metric + unique candidate counting in active stages | ae22be4, 1526be1 | 2026-04-18 11:48 | Pending |  |  |  |
| BUG-015 | Critical | Fixed | Create Login now triggers login setup/reset flow via contact email | 955606e | 2026-04-18 14:36 | Pending |  |  |  |
| BUG-021 | Critical | Fixed | Cancel in company edit is non-submit; no accidental update | 955606e | 2026-04-18 14:36 | Pending |  |  |  |
| BUG-022 | Critical | Fixed | After create redirect to new company detail + companies list limit expanded | 32f1681 | 2026-04-18 14:43 | Pending |  |  |  |
| BUG-007 | High | Fixed | Notification bell now opens actionable items list with short message and redirection | 3d5e31f | 2026-04-18 15:09 | Pending |  |  |  |
| BUG-008 | High | Fixed | Profile menu now routes to profile/settings area (admin) instead of candidates | 3d5e31f | 2026-04-18 15:09 | Pending |  |  |  |

---

## Agent Comment Stream (append-only)
- 2026-04-18 09:18 UTC — Created shared live execution board for realtime developer/tester collaboration.
- 2026-04-18 09:18 UTC — Seeded P0 fix entries with commit references and deploy timestamps.
- 2026-04-18 09:39 UTC — Fixed BUG-007 and BUG-008 in topbar; deployed frontend and added for QA retest.
- 2026-04-18 09:47 UTC — Updated live board columns to include Severity and switched display timestamps to IST.
- 2026-04-18 10:57 UTC — Fixed BUG-023 (follow-up datetime support) and deployed; QA retest placeholder added.

---

## Next Updates Protocol
1. When dev pushes fix: update row + add one Agent Comment line.
2. When tester retests: set QA Retest to Pass/Fail and add proof note.
3. If Fail: create follow-up bug or reopen same bug row with new commit.
