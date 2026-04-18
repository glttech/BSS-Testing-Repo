# Phase-1 Tester Checklist (BSS ATS)

Use this checklist for release verification. Mark each as Pass/Fail with evidence.

## A) Environment & Build
- [ ] Target URL confirmed (domain + environment)
- [ ] Frontend/Backend containers healthy
- [ ] Latest expected commit deployed
- [ ] Browser cache cleared / Incognito validation done

## B) Auth
- [ ] Login works with valid credentials
- [ ] Invalid login shows correct error
- [ ] Forgot password flow works
- [ ] Reset password flow works
- [ ] Logout works and protected routes lock

## C) Recruiter Core Flow (P0)
- [ ] Create company
- [ ] Create JD
- [ ] Add candidate (with required fields)
- [ ] Refer candidate to JD
- [ ] Update application stage (referred → screening → shortlisted etc.)
- [ ] Log communication
- [ ] Create shortlist
- [ ] Create invoice

## D) Careers Public Flow (P0)
- [ ] `/careers` loads published jobs
- [ ] Apply Now opens valid `/careers/<id>` detail page
- [ ] No “Position Not Found” for published jobs
- [ ] Resume upload works (pdf/docx)
- [ ] Submit application success shown
- [ ] Submission visible in careers admin/applications

## E) Dashboard Metrics
- [ ] Active JDs value reasonable vs jobs data
- [ ] In Pipeline value updates dynamically
- [ ] In Pipeline definition verified with product (unique candidates in active stages)
- [ ] Companies and MTD placements look consistent

## F) Candidates Module
- [ ] Candidate list count is not capped to 20 unexpectedly
- [ ] Filters work (search/source/notice)
- [ ] Candidate detail opens correctly

## G) UI/UX Standards (Mobile + Desktop)
- [ ] Mobile forms use full usable width (no squeezed desktop sidebar layout)
- [ ] Inputs/selects/buttons consistent styling
- [ ] Labels + inline errors are consistent
- [ ] Touch targets are usable (>=44px for primary actions)
- [ ] No major overflow/cutoff on small screens

## H) Regression Quick Pass
- [ ] Jobs list/detail/new
- [ ] Companies list/detail/new
- [ ] Candidates list/detail/new
- [ ] Communication page
- [ ] Shortlists
- [ ] Invoices
- [ ] Careers admin

## I) Evidence Required per failed case
- Screenshot/video (with URL visible)
- Repro steps (numbered)
- Expected vs actual
- Timestamp
- Console/network error (if available)

## J) Release Decision
- [ ] GO (all P0 pass, no P1 blockers)
- [ ] NO-GO (any P0 failure)

---

## Report Template
- Module:
- Test Case:
- Status: Pass / Fail
- Steps:
- Expected:
- Actual:
- Evidence:
- Severity: P0 / P1 / P2
