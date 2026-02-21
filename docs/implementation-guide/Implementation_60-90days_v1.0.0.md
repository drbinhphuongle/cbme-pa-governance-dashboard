# Implementation Guide — Pilot-first (60–90 days) for Programmatic Assessment Governance + Dashboard Kit (v1.0.0)

## 0. Purpose
This guide provides a practical, **pilot-first** implementation pathway for running programmatic assessment (PA) in CBME using:
- a minimal governance model,
- decision rules and evidence standards,
- and a minimal-data dashboard that supports CCC decisions with auditability.

**Goal:** achieve **decision-capable** CCC operations in one pilot site/rotation within 60–90 days, then scale.

---

## 1. Preconditions (what you need before day 1)
### 1.1 People (minimum viable team)
- **Program Director** (Accountable)
- **CCC Chair** + **2–4 CCC members** (small, cross-role)
- **1–2 Coaches/Mentors**
- **Data Steward** (can be one of the team members if small program)
- **Assessors** (pilot group)

### 1.2 Scope (keep it small)
Choose **ONE** of the following as the pilot unit:
- One rotation (e.g., Internal Medicine Ward)
- One department/site
- One cohort segment (e.g., PGY1 only)

### 1.3 Data readiness
Confirm you can collect the minimal observation fields:
- Learner_ID, Date, EPA_ID, Entrustment_Level (1–5), Assessor_ID, Assessor_Role, Setting
Recommended:
- Case_Type, Narrative_Positive, Narrative_Improve, Flag

---

## 2. Pilot design (what you will implement)
### 2.1 EPA set for pilot
Use **10–15 EPAs** maximum for v1.0 pilot.  
Define expected entrustment levels by stage (PGY1/PGY2/PGY3+), aligned with your curriculum.

### 2.2 Decision system
Adopt in full:
- **Minimum Evidence Standard (per EPA)**
- CCC outcomes: **Green / Amber / Red / Data action**
- Recency window: default **8 weeks** (adjust if rotation shorter)

### 2.3 Operational cadence (minimal)
- **Weekly huddle** (15–30 minutes) — risk, flags, missing evidence
- **Monthly CCC** (60–90 minutes) — decisions + minutes + actions
- **Quarterly QI** (optional during pilot; mandatory when scaling)

---

## 3. Timeline overview (60–90 days)

### Week 1–2: Setup and alignment
**Objectives**
- Align stakeholders on purpose, rules, and roles.
- Set up data dictionary, templates, and a working dashboard.

**Tasks**
1) Confirm pilot scope, cohort, and EPA list.
2) Assign roles and confirm meeting cadence.
3) Publish **Decision Rules & Minimum Evidence Standard** to pilot assessors/coaches.
4) Configure minimal data capture (Sheet/Excel form or simple table).
5) Prepare dashboard file and test with demo dataset.

**Deliverables**
- Pilot EPA master + expected levels by stage
- RACI confirmation (who does what)
- Decision Rules (v1.0.0) adopted as pilot policy
- Dashboard running with demo dataset
- CCC minutes template ready

**Exit criteria**
- Everyone can describe the 4 CCC outcomes and when to use them.
- Data capture mechanism produces required fields without excessive burden.

---

### Week 3–4: Data collection + rater support (micro-calibration)
**Objectives**
- Start collecting real pilot assessments (or continue simulated if needed).
- Improve narrative quality and reduce variability.

**Tasks**
1) Begin observations using the minimal dataset structure.
2) Implement a **minimum narrative expectation** (e.g., ≥1 behavior-based improvement note per observed EPA where feasible).
3) Run a 30–45 minute **micro-calibration** session:
   - show 2–3 sample cases,
   - discuss what “Level 3 vs 4” looks like,
   - align on “actionable narrative” examples.
4) Data Steward runs weekly checks:
   - missingness, recency, assessor role diversity, narrative rate, flags.

**Deliverables**
- First 2 weeks of pilot data
- Weekly data quality summary (1 page)
- Calibration notes (brief)

**Exit criteria**
- At least 60–70% of observations have narratives (or improvement note where relevant).
- Evidence is accumulating toward minimum evidence standards.

---

### Week 5–6: First CCC cycle (decision-capable milestone)
**Objectives**
- Conduct the first CCC meeting using dashboard evidence.
- Produce auditable CCC minutes and action plans.

**Tasks**
1) Prepare dashboard outputs:
   - Learner Snapshot
   - EPA Progress
   - Quality & Fairness KPIs
2) Pre-brief CCC members:
   - confirm the rules,
   - identify learners with red flags or insufficient evidence.
3) Hold **CCC Meeting #1**:
   - apply decision rules,
   - assign outcomes (Green/Amber/Red/Data action),
   - document decisions and rationales.
4) Implement action plans:
   - Amber: coaching plan 4–6 weeks
   - Red: remediation plan 8–12 weeks
   - Data action: assessment plan to close gaps

**Deliverables**
- CCC minutes (complete for each learner reviewed)
- Action plan list with owners and follow-up dates
- Calibration/fairness notes (if assessor outliers identified)

**Exit criteria**
- CCC minutes capture: evidence sufficiency, rules applied, rationale, actions, follow-up.
- At least one Amber/Data action case has a documented plan and owner.

---

### Week 7–8: Follow-up evidence + improvement loop
**Objectives**
- Track improvement and close evidence gaps.
- Adjust rater guidance and data capture issues.

**Tasks**
1) Coaches deliver targeted support and document progress.
2) Data Steward monitors:
   - recency compliance,
   - EPA coverage,
   - follow-up completion (as feasible),
   - outlier assessor signals.
3) Run a second brief calibration (20–30 minutes) if:
   - variance remains high, or
   - narratives are low quality.

**Deliverables**
- Follow-up evidence (additional observations targeted to gaps)
- Updated dashboard snapshots
- Updated action status tracker (can be embedded in CCC minutes)

**Exit criteria**
- Evidence gaps reduced for learners previously “Data action”.
- Amber learners have at least 2–3 focused follow-up observations.

---

### Week 9–12 (optional if aiming for 90 days): Second CCC cycle + scale readiness
**Objectives**
- Demonstrate repeatable CCC decisions and sustainability.
- Decide whether to scale to additional rotations/cohorts.

**Tasks**
1) Hold **CCC Meeting #2** and reassess Amber/Red/Data action learners.
2) Summarize pilot outcomes:
   - decision distribution (Green/Amber/Red/Data action),
   - time-to-decision (if tracked),
   - quality KPIs trends (narrative rate, recency compliance).
3) Identify scaling requirements:
   - training needs,
   - data capture workflow refinement,
   - governance capacity.

**Deliverables**
- CCC minutes #2
- Pilot evaluation summary (2 pages)
- Scale plan (next 1–2 rotations)

**Exit criteria**
- CCC process is repeatable and auditable.
- Stakeholders agree on scaling decision and resource plan.

---

## 4. Minimal training package (recommended)
### 4.1 For assessors (30–45 minutes)
- Entrustment scale interpretation (1–5)
- What counts as “actionable narrative”
- Examples of good/poor narrative
- Red flag and escalation rules

### 4.2 For CCC members (45–60 minutes)
- Minimum evidence standard
- Consistent application of Green/Amber/Red/Data action
- Documentation expectations (auditability)
- Handling variability and assessor outliers

### 4.3 For coaches (30 minutes)
- Translating CCC decisions into SMART action plans
- Tracking follow-up and progress evidence

---

## 5. Common failure modes and how to prevent them
### 5.1 Too much scope
**Symptom:** data overload, CCC takes too long.  
**Prevention:** start with 1 rotation and 10–15 EPAs only.

### 5.2 Insufficient narratives
**Symptom:** dashboard shows numbers but cannot guide coaching actions.  
**Prevention:** set a minimal narrative expectation + provide examples.

### 5.3 Inconsistent ratings across assessors
**Symptom:** high variance, perceived unfairness.  
**Prevention:** micro-calibration + flag outliers for calibration (do not delete data).

### 5.4 Decisions not auditable
**Symptom:** outcomes decided but rationale not documented.  
**Prevention:** CCC minutes template required fields; Chair enforces documentation.

---

## 6. Scale-up guidance (after pilot)
Scale to the next site/rotation only when:
- the Minimum Evidence Standard is feasible within your context,
- CCC minutes are consistently complete,
- and quality KPIs are acceptable (narrative rate improving, recency compliance stable).

**Recommended scaling approach**
- Add one rotation at a time.
- Repeat the same training and cadence.
- Reuse dashboard structure; only update EPA master and expected levels.

---

## 7. Versioning and governance for changes
Any changes to:
- EPA definitions,
- expected entrustment levels,
- decision rules,
- or data dictionary fields  
should be versioned and documented in `CHANGELOG.md`.

Use semantic versioning:
- PATCH: minor fixes
- MINOR: non-breaking additions
- MAJOR: breaking changes

---

## 8. Implementation checklist (quick)
### Before starting
- [ ] Pilot scope selected (one rotation/site/cohort)
- [ ] Roles assigned (PD, CCC Chair/Members, coaches, data steward)
- [ ] EPA list and expected levels set
- [ ] Decision rules published to pilot team
- [ ] Data capture method ready

### First CCC
- [ ] Dashboard outputs prepared
- [ ] Evidence sufficiency checked
- [ ] CCC outcomes assigned and documented
- [ ] Action plans assigned with owners and follow-up dates

### After pilot
- [ ] QI review completed
- [ ] Scaling decision made
- [ ] Version update recorded
