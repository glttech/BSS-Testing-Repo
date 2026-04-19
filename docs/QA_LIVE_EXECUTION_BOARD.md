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
| BUG-029 | Medium | Open | Industry dropdown should enforce controlled values instead of free text |  |  | Pending |  |  | Added from tester Google doc backlog sync |
| BUG-028 | Medium | Open | Careers page needs filtering and count grids for visibility |  |  | Pending |  |  | Added from tester Google doc backlog sync |
| BUG-027 | High | Fixed | Careers admin View action now routes to JD detail page | 5569370 | 2026-04-19 06:40 | Pending |  |  | Re-test view action from careers admin table |
| BUG-026 | High | Fixed | Duplicate candidate guard added on create/update using email/phone checks | dad4127 | 2026-04-19 09:33 | Pending |  |  | Re-test duplicate candidate creation/edit scenarios |
| BUG-025 | Medium | Open | Remove/disable unsupported upload icon in Job Descriptions |  |  | Pending |  |  | Added from tester Google doc backlog sync |
| BUG-024 | High | Fixed | Mounted JD parser routes under /api/v1/jds (parse-text and parse-and-validate) | 5569370 | 2026-04-19 06:40 | Pending |  |  | Re-test Parse & Review action from Jobs import dialog |
| BUG-023 | High | Fixed | Follow-up now supports full datetime input and timestamp display in communication + caller flows | 6a0af56 | 2026-04-18 16:26 | Pending |  |  |  |
| BUG-003 | Critical | Fixed | Global search suggestions + navigation for candidates/companies/jobs | 955606e | 2026-04-18 14:36 | Pass | Dimpi |  | A clear (cross) icon should be provided after displaying global search results to allow users to easily clear the search input.|
| BUG-012 | Critical | Fixed (Patch-2) | Excluded null candidateId from pipeline aggregation to prevent phantom count inflation | 9c061ed | 2026-04-19 00:06 | Pending | Dimpi |  | Re-test requested: verify pipeline total and list relevance after patch-2. |
| BUG-015 | Critical | Fixed (Patch-2) | Create Login now creates portal user first; if user exists, fallback to password-reset email flow | 9c061ed | 2026-04-19 00:06 | Pending | Dimpi |  | Re-test requested: verify portal user creation path and email/reset behavior. |
| BUG-021 | Critical | Fixed | Cancel in company edit is non-submit; no accidental update | 955606e | 2026-04-18 14:36 | Pass |Dimpi  |  | Working as expected. |
| BUG-022 | Critical | Fixed | After create redirect to new company detail + companies list limit expanded | 32f1681 | 2026-04-18 14:43 | Pass | Dimpi |  | The newly created company should be visible in the list without requiring a manual refresh. |
| BUG-007 | High | Fixed | Notification bell now opens actionable items list with short message and redirection | 3d5e31f | 2026-04-18 15:09 | Pass | Dimpi |  | After the notification bell fix, clicking on a notification from the communication log does not update the selected notification. Instead, it continues to display the previously selected notification. |
| BUG-008 | High | Fixed | Profile menu now routes to profile/settings area (admin) instead of candidates | 3d5e31f | 2026-04-18 15:09 | Pass | Dimpi |  | Redundant navigation issue: both ‘Profile’ and ‘Settings’ redirect to the same page. One of these options should be removed to avoid confusion, and the ‘Admin Panel’ should be renamed to ‘Settings’ or ‘Profile’ for better clarity and consistency. |

---

## Agent Comment Stream (append-only)
- 2026-04-18 09:18 UTC — Created shared live execution board for realtime developer/tester collaboration.
- 2026-04-18 09:18 UTC — Seeded P0 fix entries with commit references and deploy timestamps.
- 2026-04-18 09:39 UTC — Fixed BUG-007 and BUG-008 in topbar; deployed frontend and added for QA retest.
- 2026-04-18 09:47 UTC — Updated live board columns to include Severity and switched display timestamps to IST.
- 2026-04-18 10:57 UTC — Fixed BUG-023 (follow-up datetime support) and deployed; QA retest placeholder added.
- 2026-04-18 18:37 UTC — Applied Patch-2 for BUG-012 and BUG-015; deployed and moved both to Pending retest.
- 2026-04-18 19:39 UTC — Synced missing tester Google-doc issues into tracker as BUG-024 to BUG-029 and added Open rows in live board.
- 2026-04-19 01:11 UTC — Fixed BUG-024 and BUG-027 in code repo, deployed to bss-dev, and marked both Pending QA retest.
- 2026-04-19 04:03 UTC — Fixed BUG-026 duplicate validation in backend and deployed; pending QA retest.

---

## Next Updates Protocol
1. When dev pushes fix: update row + add one Agent Comment line.
2. When tester retests: set QA Retest to Pass/Fail and add proof note.
3. If Fail: create follow-up bug or reopen same bug row with new commit.
