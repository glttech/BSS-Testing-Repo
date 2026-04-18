# NEXT_ITERATION_TEST_FORMAT.md

Use this format for every new testing cycle to keep QA output consistent, actionable, and developer-friendly.

---

## 1) Test Run Header

- **Run ID:** `ITER-YYYYMMDD-01`
- **Build/Commit:**
- **Environment URL:**
- **Tester Name:**
- **Date/Time:**
- **Browser/Device Matrix:**
  - Chrome Desktop
  - Android Chrome
  - iOS Safari (minimum smoke)

---

## 2) Scope Declaration (mark in-scope modules)

- [ ] Auth
- [ ] Dashboard
- [ ] Companies
- [ ] Jobs
- [ ] Candidates
- [ ] Applications / Pipeline
- [ ] Careers Public Flow
- [ ] Communication
- [ ] Shortlists
- [ ] Invoices
- [ ] Voice Screening

---

## 3) Test Case Format (repeat for each case)

- **Case ID:** `TC-001`
- **Feature/Module:**
- **Priority:** `P0 / P1 / P2`
- **Precondition:**
- **Steps to Reproduce:**
  1.
  2.
  3.
- **Expected Result:**
- **Actual Result:**
- **Status:** `PASS / FAIL / BLOCKED`
- **Evidence:** (screenshot/video + URL)
- **Linked Bug ID (if FAIL):** `BUG-xxx`

---

## 4) Bug Report Format (mandatory for every FAIL)

- **Bug ID:** `BUG-001`
- **Title:**
- **Module:**
- **Severity:** `Critical / High / Medium / Low`
- **Priority:** `P0 / P1 / P2`
- **Environment:**
- **Build/Commit:**
- **Steps to Reproduce:**
  1.
  2.
  3.
- **Actual Result:**
- **Expected Result:**
- **Frequency:** `Always / Intermittent / Rare`
- **Impact:** (1-line user/business impact)
- **Evidence:** screenshots/videos + console/network logs (if available)

---

## 5) Mandatory P0 Regression Set (every iteration)

1. Login / Logout / Forgot / Reset Password
2. Create Company (valid + invalid validation checks)
3. Create JD and publish to Careers
4. Add Candidate and refer to JD
5. Update Application Stage
6. Dashboard metric sanity check
   - In Pipeline count behavior vs candidate/application data
7. Careers public flow
   - `/careers` list
   - `Apply Now` opens `/careers/:id`
   - Application submission with resume upload
8. Communication log create + follow-up visibility
9. Shortlist flow create/send
10. Invoice creation flow

---

## 6) Iteration Exit Summary (required)

- **Total cases executed:**
- **PASS:**
- **FAIL:**
- **BLOCKED:**
- **Open P0 bugs:**
- **Open P1 bugs:**
- **Go/No-Go Recommendation:** `GO / NO-GO`
- **Top Risks/Notes:**

---

## 7) Quality Rules for Tester

- Do not log vague failures (e.g., "not working"); always include reproducible steps.
- Attach at least one evidence artifact for every FAIL.
- Include exact URL in screenshot for navigation/routing issues.
- For data/count mismatch bugs, include source numbers from both screens.
- Re-test fixed bugs and mark as `RETEST PASS` or `RETEST FAIL`.

---

## 8) Submission Format

Submit report as:
- `ITER-YYYYMMDD-01-QA-REPORT.md`
- Plus attachments folder with screenshots/videos.
