# BSS ATS — Bug Tracker Ready Format (Jira/ClickUp)

Source normalized from shared issue list. Numbering, wording, priority, and acceptance criteria standardized.

> Shared realtime status board for tester/dev: `docs/QA_LIVE_EXECUTION_BOARD.md`

## Severity / Priority Legend
- **P0** = release blocker
- **P1** = high impact, fix in current cycle
- **P2** = medium/low impact, schedule after P0/P1

---

## Current Execution Status (Live Progress)

### P0 Bug Status Snapshot
- **BUG-003:** ✅ Fixed (retest pending)
  - Short fix: implemented working topbar global search with live suggestions (candidates/companies/jobs) and navigation.
  - Commit: `955606e`
- **BUG-012:** ✅ Fixed (retest pending)
  - Short fix: In Pipeline metric made dynamic and aligned to unique-candidate counting across active pipeline stages.
  - Commits: `ae22be4`, `1526be1`
- **BUG-015:** ✅ Fixed (retest pending)
  - Short fix: wired Create Login button to trigger login-setup/reset flow using company contact email with success/error toast.
  - Commit: `955606e`
- **BUG-021:** ✅ Fixed (retest pending)
  - Short fix: Cancel button in company edit is now non-submit (`type="button"`), so it no longer updates data.
  - Commit: `955606e`
- **BUG-022:** ✅ Fixed (retest pending)
  - Short fix: after create, app redirects to the newly created company detail and company list fetch limit increased to avoid visibility confusion.
  - Commit: `32f1681`

> Note: Marked as **Fixed** from development side; QA should mark **Retest Passed/Failed** after verification.

---

## BUG-001
- **Title:** Duplicate validation errors displayed for invalid email input
- **Module:** Company / Auth forms
- **Priority:** P1
- **Severity:** Medium
- **Steps:** Enter invalid email in form field and submit.
- **Actual:** Two error messages shown for same invalid email.
- **Expected:** Single clear validation error message.
- **Acceptance:** Only one email error shown per field.

## BUG-002
- **Title:** Forgot-password confirmation flow accessible for non-registered users without safe messaging standard
- **Module:** Auth
- **Priority:** P1
- **Severity:** High
- **Steps:** Trigger forgot/reset for unknown email.
- **Actual:** Flow behavior inconsistent; no secure generic UX standard enforced.
- **Expected:** Always show neutral message (e.g., “If account exists, reset link will be sent”) without revealing account existence.
- **Acceptance:** Uniform non-enumerating response for both existing and non-existing emails.

## BUG-003
- **Title:** Global search returns no results/suggestions
- **Module:** Global Search
- **Priority:** P0
- **Severity:** Critical
- **Steps:** Use global search with valid known entities.
- **Actual:** No results and no suggestions.
- **Expected:** Relevant results/suggestions with navigation.
- **Acceptance:** Search works for company/JD/candidate keywords.

## BUG-004
- **Title:** Sidebar icon spacing breaks when toggling collapsed/expanded view
- **Module:** Sidebar Navigation
- **Priority:** P2
- **Severity:** Low
- **Steps:** Toggle sidebar collapse state repeatedly.
- **Actual:** Icon spacing/alignment inconsistent.
- **Expected:** Stable spacing in both states.
- **Acceptance:** Pixel-consistent icon alignment in collapsed and expanded modes.

## BUG-005
- **Title:** Duplicate Microphone and Clipboard/Document icons shown
- **Module:** Navigation / Menu
- **Priority:** P2
- **Severity:** Low
- **Steps:** Open sidebar/menu and inspect icons.
- **Actual:** Duplicate/ambiguous icon usage.
- **Expected:** Unique, semantically correct icon mapping.
- **Acceptance:** No duplicate/confusing icons.

## BUG-006
- **Title:** Page alignment inconsistent (center-aligned while rest of app is left-aligned)
- **Module:** Layout
- **Priority:** P2
- **Severity:** Medium
- **Steps:** Compare affected page with standard dashboard pages.
- **Actual:** Inconsistent alignment and layout rhythm.
- **Expected:** Consistent layout grid/alignment.
- **Acceptance:** Page follows global layout alignment rules.

## BUG-007
- **Title:** Notifications show count only; users cannot identify notification content
- **Module:** Notifications
- **Priority:** P1
- **Severity:** High
- **Steps:** Trigger notification events.
- **Actual:** Only count is visible; no actionable preview/redirection context.
- **Expected:** Notification message preview + click redirection.
- **Acceptance:** Notification panel/list shows short text and route target.

## BUG-008
- **Title:** Profile click redirects to Candidates page instead of user profile
- **Module:** Profile Navigation
- **Priority:** P1
- **Severity:** High
- **Steps:** Click profile entry/avatar.
- **Actual:** Redirects to candidates.
- **Expected:** Redirects to profile/settings page.
- **Acceptance:** Profile entry opens profile route.

## BUG-009
- **Title:** Profile avatar shows only first letter, not proper initials logic
- **Module:** Profile UI
- **Priority:** P2
- **Severity:** Low
- **Steps:** Login with multi-word username.
- **Actual:** Single letter only.
- **Expected:** Initials logic (e.g., RS for Rahul Swami).
- **Acceptance:** Avatar uses consistent initials algorithm.

## BUG-010
- **Title:** Settings page title mismatch
- **Module:** Settings
- **Priority:** P2
- **Severity:** Low
- **Steps:** Open settings route/page.
- **Actual:** Title does not reflect page context.
- **Expected:** Correct title (e.g., “Settings”).
- **Acceptance:** Title and breadcrumb match route purpose.

## BUG-011
- **Title:** Dashboard top cards click behavior inconsistent (Candidate Trend not clickable)
- **Module:** Dashboard
- **Priority:** P2
- **Severity:** Medium
- **Steps:** Click all top cards.
- **Actual:** Last card non-clickable while others are clickable.
- **Expected:** Consistent card interaction model.
- **Acceptance:** Either all cards clickable with destination or non-clickable by design.

## BUG-012
- **Title:** In Pipeline count misleading vs visible candidate data
- **Module:** Dashboard / Candidates
- **Priority:** P0
- **Severity:** Critical
- **Steps:** Compare dashboard in-pipeline metric with candidates/applications datasets.
- **Actual:** Count appears misleading/inconsistent.
- **Expected:** Metric definition explicit and values consistent with data source.
- **Acceptance:** Tooltip/label defines metric (unique candidates vs applications), and value matches backend logic.

## BUG-013
- **Title:** Dashboard sections have excessive spacing and oversized containers
- **Module:** Dashboard UI
- **Priority:** P2
- **Severity:** Medium
- **Steps:** Review dashboard on laptop/mobile.
- **Actual:** Too much whitespace; low information density.
- **Expected:** Balanced spacing and visible summary density.
- **Acceptance:** Dashboard shows meaningful rows without excessive empty regions.

## BUG-014
- **Title:** Long company names break action-button alignment
- **Module:** Company list/cards
- **Priority:** P1
- **Severity:** Medium
- **Steps:** Create/view company with long name.
- **Actual:** Action buttons shift/misalign.
- **Expected:** Buttons remain right-aligned; text truncates/wraps safely.
- **Acceptance:** Stable button alignment for long names.

## BUG-015
- **Title:** “Create Login” action button does not trigger any action
- **Module:** Company/User provisioning
- **Priority:** P0
- **Severity:** Critical
- **Steps:** Click Create Login button.
- **Actual:** No action/feedback.
- **Expected:** User creation flow starts with success/error feedback.
- **Acceptance:** Button invokes backend action and shows result.

## BUG-016
- **Title:** Missing character limits for key company fields
- **Module:** Company form
- **Priority:** P1
- **Severity:** Medium
- **Fields:** company name, industry, contact person, phone, website, address, notes.
- **Expected:** Reasonable max lengths + UI helper/validation.
- **Acceptance:** Limits enforced in frontend + backend.

## BUG-017
- **Title:** Generic “Validation failed” message lacks field-level clarity
- **Module:** Validation UX
- **Priority:** P1
- **Severity:** High
- **Steps:** Submit invalid company form data.
- **Actual:** Non-descriptive error.
- **Expected:** Specific field-level errors.
- **Acceptance:** Error clearly indicates field and reason.

## BUG-018
- **Title:** Contact phone field allows alphabetic input
- **Module:** Company form
- **Priority:** P1
- **Severity:** High
- **Steps:** Enter letters in contact number.
- **Actual:** Accepted.
- **Expected:** Numeric + allowed phone symbols only.
- **Acceptance:** Invalid chars blocked or rejected with message.

## BUG-019
- **Title:** Industry field allows numeric-only values
- **Module:** Company form
- **Priority:** P1
- **Severity:** Medium
- **Steps:** Enter numeric industry value.
- **Actual:** Accepted.
- **Expected:** Alphabetic/business taxonomy input constraints.
- **Acceptance:** Validation prevents invalid numeric-only entries.

## BUG-020
- **Title:** Cancel button shows “Company updated successfully” even when canceling
- **Module:** Company edit
- **Priority:** P1
- **Severity:** High
- **Steps:** Open edit form, click Cancel.
- **Actual:** Success toast for update appears.
- **Expected:** Cancel should discard without update toast.
- **Acceptance:** No update action or success toast on cancel.

## BUG-021
- **Title:** Cancel action updates and persists company data instead of discarding
- **Module:** Company edit
- **Priority:** P0
- **Severity:** Critical
- **Steps:** Modify values and click Cancel.
- **Actual:** Changes are saved.
- **Expected:** Changes discarded.
- **Acceptance:** Cancel never mutates persisted data.

## BUG-022
- **Title:** Company creation inconsistent when only required fields are filled
- **Module:** Company create
- **Priority:** P0
- **Severity:** Critical
- **Steps:** Create company with required fields only vs required+optional.
- **Actual:** Inconsistent visibility/creation behavior.
- **Expected:** Required-only valid payload always creates visible record.
- **Acceptance:** Consistent create behavior independent of optional fields.

---

## QA Retest Tracker (to close fixes formally)

| Bug ID | Dev Status | QA Retest | Tester | Date | Notes |
|---|---|---|---|---|---|
| BUG-003 | Fixed | Pending |  |  |  |
| BUG-012 | Fixed | Pending |  |  |  |
| BUG-015 | Fixed | Pending |  |  |  |
| BUG-021 | Fixed | Pending |  |  |  |
| BUG-022 | Fixed | Pending |  |  |  |

**QA Retest values:** Pending / Pass / Fail

---

## Suggested Sprint Triage

### Sprint Immediate (P0)
- BUG-003, BUG-012, BUG-015, BUG-021, BUG-022

### Sprint Current (P1)
- BUG-001, BUG-002, BUG-007, BUG-008, BUG-014, BUG-016, BUG-017, BUG-018, BUG-019, BUG-020

### Sprint Next (P2)
- BUG-004, BUG-005, BUG-006, BUG-009, BUG-010, BUG-011, BUG-013
