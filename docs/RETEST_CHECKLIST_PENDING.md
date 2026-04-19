# Retest Checklist (Pending/Blocked Only)

Use this file only for pending-fixed bugs and blocked P0 journeys.

## Table

| Test | URL | Steps | Expected | Capture if fail | Severity |
|---|---|---|---|---|---|
| BUG-012 Metric Validation | `https://bss-dev.devascend.co.in/` | Open dashboard, note In Pipeline, cross-check against active-stage candidate/application views | In Pipeline definition and count are consistent with source data | Dashboard + source data pages in one capture | Critical |
| BUG-015 Create Login Flow | `https://bss-dev.devascend.co.in/companies/<id>` | Click Create Login on a company with contact email; verify user-create or reset path outcome | Action results in real account/reset outcome, not toast-only | Button action + toast + mail evidence or backend response | Critical |
| BUG-023 Follow-up Datetime | `https://bss-dev.devascend.co.in/communication` | Create/reschedule follow-up with date+time and view timeline | Full timestamp (date + time) is saved and displayed | Form + timeline entry | High |
| BUG-024 Parse & Review Route | `https://bss-dev.devascend.co.in/jobs` | Open JD import and run Parse & Review | Route opens correctly without route-not-found error | Dialog action + resulting URL/error | High |
| BUG-025 JD Parse UI Clarity | `https://bss-dev.devascend.co.in/jobs` | Open import dialog and inspect actions/icons | No misleading upload action where upload is unsupported | Dialog screenshot | Medium |
| BUG-026 Candidate Duplicate Guard | `https://bss-dev.devascend.co.in/candidates/new` | Try creating candidate with existing email/phone | Duplicate is blocked with clear error | Form submission + error response | High |
| BUG-027 Careers Admin View | `https://bss-dev.devascend.co.in/careers-admin` | Click View on a row | Opens valid job details route | Click + resulting URL | High |
| BUG-028 Careers Filters & Grids | `https://bss-dev.devascend.co.in/careers-admin` | Use search/status/publish filters and verify count cards | Filters work and summary counts update correctly | Filter inputs + count cards + table result | Medium |
| BUG-029 Industry Dropdown | `https://bss-dev.devascend.co.in/companies/new` | Open industry input in create/edit form | Industry is controlled dropdown (not free text) | Field screenshot | Medium |
| Recruiter Login Journey (Blocked) | `https://bss-dev.devascend.co.in/login` | Login with valid recruiter credentials | Access to dashboard with stable session | Login attempt + error/loop | Critical |
| AI Evaluation Entry (Blocked) | `https://bss-dev.devascend.co.in/ai-analysis` | Open AI analysis entry flow and submit a valid input | Flow loads and accepts valid evaluation input | Page + failing step | High |
| Shortlist/Share Journey (Blocked) | `https://bss-dev.devascend.co.in/shortlists` | Create shortlist and open generated share URL | Share page opens and data is visible | Create flow + shared URL result | High |
| Domain Parity Check (Blocked) | `https://bss-dev.devascend.co.in` and target domain | Verify same flow behavior and expected build mapping | No domain-specific drift on critical flows | Side-by-side screenshots with URL/build evidence | Critical |

## Notes
- Update live status in `QA_LIVE_EXECUTION_BOARD.md` after each retest.
- Mark only PASS/FAIL/BLOCKED with evidence.
