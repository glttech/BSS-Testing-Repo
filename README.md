# BSS Testing Repo

This repository is **QA/Tester-facing only**.

It contains:
- live bug tracker and execution board
- tester checklists and iteration formats
- release readiness/testing documents

It does **not** contain application source code.

## QA Rules (mandatory)
- Tester must mark only **PASS / FAIL / BLOCKED** (no guessing).
- Every **FAIL** must include screenshot evidence (URL visible).
- No retest should be marked complete until dev marks the fix complete in live board.
- Overall **GREEN** is allowed only if all P0 tests are PASS.

## Primary docs
- `docs/QA_LIVE_EXECUTION_BOARD.md` (single source of live status)
- `docs/BUG_TRACKER_READY_JIRA_CLICKUP.md` (bug definitions/catalog)
- `docs/NEXT_ITERATION_TEST_FORMAT.md` (standard test run format)
- `docs/PHASE1_TESTER_CHECKLIST.md` (phase-1 checklist)
- `docs/RETEST_CHECKLIST_PENDING.md` (pending-fixed and blocked retests only)
- `docs/ENVIRONMENT_MAP.md` (domain/branch/API parity map)
