# BSS ATS — Design System & Phase-1 Release Review

## Purpose
Single-source review for design consistency and Phase-1 release readiness, aligned to current roadmap docs and live implementation.

---

## 1) Design System Audit (Current)

### 1.1 Foundations (Tokens / Theme)
**Status:** ✅ Available

- Global color and semantic tokens are defined in `frontend/src/app/globals.css`:
  - `--primary`, `--muted`, `--border`, `--ring`, `--success`, `--warning`, `--info`
  - sidebar tokens and base radius
- Dark mode token set exists.

**Gap:**
- No explicit token governance doc (what tokens to use in which scenarios).

---

### 1.2 Shared UI Primitives
**Status:** ✅ Present

Core primitives exist under `frontend/src/components/ui/`:
- input, textarea, select, button, card, table, badge/status-badge, tabs, dialog/sheet, sidebar, page-header, stats-card

**Gap:**
- Some pages still bypass primitives and use ad-hoc classes, causing style drift.

---

### 1.3 Form System
**Status:** ✅ In place (partially propagated)

Form utility classes and helpers available:
- `.form-label`, `.form-error`, `.form-section`, `.form-shell`
- Shared components: `FormLabel`, `FieldError`

Applied across major forms (jobs, companies, candidates, invoices, auth, careers apply, communication, shortlist, selected dialogs).

**Gap:**
- Residual forms/modals still need strict migration to remove remaining inconsistent label/error styles.

---

### 1.4 Responsive UX
**Status:** ⚠️ Improved, still verification-heavy

Improvements delivered:
- Sidebar behavior adjusted for mobile/tablet thresholds
- Better mobile form spacing and widths on key pages

**Gap:**
- Need a full mobile regression pass across all modules to ensure no compressed containers remain.

---

### 1.5 Minimal/Modern Aesthetic Goal
**Status:** ⚠️ In progress

Progress:
- Reduced heavy borders/shadows in core form shells and cards
- Standardized spacing and field sizes

Remaining:
- Remove lingering visual noise from older cards/lists and nested containers
- enforce one primary page container pattern where possible

---

## 2) Phase-1 (Sprint-1) Roadmap Readiness View

## 2.1 Roadmap Record
From `docs/ROADMAP_STATUS.md`:
- Sprint 1 = **completed**
- Active sprint = Sprint 4 (in progress)

So roadmap tracking marks Phase-1 complete.

## 2.2 Practical Release Readiness (Operational)
**Current judgment:** 🟡 *Conditionally ready* (not fully green)

### Must-pass before final signoff
1. Recruiter P0 E2E flow passes end-to-end
2. Careers public apply flow passes on target domain(s)
3. Dashboard critical metrics validated against DB semantics (in-pipeline definition agreed)
4. Mobile smoke checks pass for top workflows
5. No open P0/P1 blockers

---

## 3) Current Risk Register (Focused)

### R1: Metric semantics mismatch
- Symptom: confusion between candidate totals and pipeline totals.
- Current mitigation: in-pipeline moved toward dynamic/unique candidate counting logic.
- Remaining action: lock metric definition in product docs and UI tooltip.

### R2: Domain/environment drift
- Symptom: behavior differs between `bss-dev.devascend.co.in` and other domains/environments.
- Mitigation: explicitly verify deployed commit hash per domain.
- Remaining action: add environment-to-branch deployment map.

### R3: Partial design-system adoption
- Symptom: some views still look non-minimal/inconsistent.
- Mitigation: continue sequential migration to primitives + form helpers.

---

## 4) Go / No-Go Criteria for Phase-1 Release

## GO if all true:
- [ ] All P0 journeys in `docs/E2E_FUNCTIONAL_TEST_PLAN.md` pass
- [ ] Careers Apply works for all published jobs (no “Position Not Found”)
- [ ] Dashboard core metrics validated and agreed
- [ ] Mobile usability validated for top 8 pages
- [ ] No unresolved P0/P1 bugs

## NO-GO if any true:
- [ ] Public apply flow is inconsistent on target release domain
- [ ] Major metric discrepancy unresolved
- [ ] Key mobile workflows still constrained/broken

---

## 5) Recommended Next Actions (Sequential)

1. **Design-system closure pass (remaining outliers)**
   - migrate remaining non-standard labels/errors/containers
2. **Metric definition lock**
   - add explicit descriptions for dashboard cards
3. **Domain parity check**
   - verify same build/commit and API behavior on each active domain
4. **E2E execution + evidence**
   - run P0 matrix and attach screenshots/logs
5. **Release signoff note**
   - one-page green/yellow/red summary with blocker list

---

## 6) Source References
- `docs/ROADMAP_STATUS.md`
- `docs/UI_REDESIGN_TASKS.md`
- `docs/E2E_FUNCTIONAL_TEST_PLAN.md`
- `frontend/src/app/globals.css`
- `frontend/src/components/ui/*`
