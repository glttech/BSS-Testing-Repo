# Phase-1 Tester Checklist (BSS ATS)

Use this file for execution-level testing. Keep outcomes in `QA_LIVE_EXECUTION_BOARD.md`.

## Summary
- Target environment: `https://bss-dev.devascend.co.in`
- Rule: mark only PASS / FAIL based on observed behavior.
- Rule: for every FAIL, capture screenshot with URL and short repro video if possible.

---

## Checklist Table (Execution)

| Test | URL | Test Data Example | Expected Result (PASS condition) | What to capture if FAIL |
|---|---|---|---|---|
| Login (valid user) | `https://bss-dev.devascend.co.in/login` | valid recruiter email/password | Redirects to dashboard and session remains active | Login screen + error text + network response |
| Create Company | `https://bss-dev.devascend.co.in/companies/new` | Name: `QA Realty`, Industry: `Real Estate`, Contact Email: `qa.company@example.com`, Phone: `9876543210` | Company created and visible / opens detail page | Filled form + toast + resulting page |
| Create JD | `https://bss-dev.devascend.co.in/jobs/new` | Title: `QA Test JD`, Company: existing company, Status: open | JD created successfully and visible in jobs list | Form + toast + jobs list |
| Candidate Create | `https://bss-dev.devascend.co.in/candidates/new` | Name: `Rahul Candidate`, Email: `qa.candidate@example.com`, Phone: `9000000001` | Candidate created and visible in list/detail | Form + toast + list/result |
| Candidate Duplicate Guard | `https://bss-dev.devascend.co.in/candidates/new` | Reuse same email/phone as existing candidate | Duplicate prevented with clear validation/conflict message | Attempt form + returned error |
| Parse & Review (JD) | `https://bss-dev.devascend.co.in/jobs` | Paste JD text in import dialog | Parse & Review opens and route works (no route-not-found) | Dialog + error page/URL |
| Careers Admin View Action | `https://bss-dev.devascend.co.in/careers-admin` | Click View in any row | Opens correct JD detail page | Click action + resulting URL |
| Careers Public Apply | `https://bss-dev.devascend.co.in/careers` | Use any published job | Apply Now opens `/careers/<id>` and application submit works | Listing page + detail page + submit response |
| Communication Follow-up Datetime | `https://bss-dev.devascend.co.in/communication` | Set follow-up with date+time | Stored item shows full timestamp (date+time) | Form input + timeline entry |
| Dashboard Metric Clarity | `https://bss-dev.devascend.co.in/` | N/A | Metric helper text visible and understandable | Dashboard card area screenshot |
| In Pipeline Metric Validation (BUG-012) | `https://bss-dev.devascend.co.in/` + candidates/applications views | Compare pipeline with actual active-stage candidates | Count is semantically consistent (no phantom inflation) | Dashboard + source page counts |
| Create Login Flow (BUG-015) | `https://bss-dev.devascend.co.in/companies/<id>` | Company with valid contact email | Create Login either creates portal user or triggers reset path with real outcome | Button click + toast + email/portal evidence |
| Shortlist & Share | `https://bss-dev.devascend.co.in/shortlists` | Create shortlist and open share URL | Share link opens and renders shortlist content | Shortlist create + shared page |

---

## Notes
- If route/action fails once, retry once in incognito before marking FAIL.
- Use IST in notes when possible.
- All FAIL evidence should include URL bar in screenshot.
