# User Guide — CBME Programmatic Assessment Governance + Dashboard Kit (v1.0.0)

## 1. Purpose and scope
This toolkit supports **programmatic assessment (PA)** in **competency-based medical education (CBME)** by combining:
- a **governance model** (roles, cadence, due process),
- **decision rules** (minimum evidence standards and standardized CCC outcomes),
- and a **minimal-data dashboard** that enables **consistent, fair, and auditable** Clinical Competency Committee (CCC) decisions.

**Scope:** Conceptual and implementation-ready toolkit designed to run without LMS/EHR integration.  
**Not included (v1.0.0):** automated data feeds, advanced psychometric modeling, institution-specific legal language.

---

## 2. What’s included (files and locations)

### Governance and decision-making
- **PA governance 1-pager:** `/toolkit/governance-pack/PA-Gov_1pager_v1.0.0.md`
- **Decision rules & evidence standards:** `/toolkit/governance-pack/DecisionRules_v1.0.0.md`
- **CCC minutes template (auditable documentation):** `/toolkit/templates/CCC_Minutes_Template_v1.0.0.md`

### Data and dashboard
- **Data dictionary:** `/data/data-dictionary/DataDictionary_v1.0.0.md`
- **Demo dataset (simulated):** `/data/demo-dataset/DemoDataset_v1.0.0.csv`
- **Dashboard (Excel):** `/dashboard/excel/PA-Gov_DashboardKit_v1.0.0.xlsx` (to be uploaded)

### Implementation materials
- **Implementation guide:** `/docs/implementation-guide/Implementation_60-90days_v1.0.0.md` (optional in v1.0.0)

---

## 3. Roles and responsibilities (operational summary)
- **Program Director:** accountable for program-level decisions, due process, escalation, resourcing.
- **CCC Chair/Members:** apply decision rules consistently; document decisions and rationales.
- **Coach/Mentor:** converts CCC outcomes into action plans and monitors follow-up.
- **Assessors:** provide observations (entrustment ratings) + behavior-based narrative feedback.
- **Data Steward:** ensures data quality, maintains the dashboard, manages access and audit trail.

---

## 4. Standard workflow (end-to-end)
### Step 1 — Collect assessment evidence
Assessors submit:
- entrustment rating (1–5),
- brief narrative: “what went well” + “what to improve,”
- flags for patient safety/professionalism when relevant.

### Step 2 — Run data quality checks (before CCC)
The Data Steward reviews:
- **missingness** (required fields present),
- **recency** (enough observations in the last 8 weeks / current rotation),
- **assessor diversity** (≥2 assessors and ≥2 roles),
- **context diversity** (≥2 settings/case types),
- **coverage** (EPAs observed as expected for the stage).

### Step 3 — Review dashboard (3 views)
1) **Learner Snapshot:** readiness signals and risk flags at learner level  
2) **EPA Progress:** progress vs expected entrustment by stage, trend and sufficiency  
3) **Quality & Fairness:** quality KPIs (narrative rate, recency compliance) and fairness signals (assessor variance, leniency/stringency flags)

### Step 4 — CCC decision (using Decision Rules)
CCC applies:
- **Minimum Evidence Standard (per EPA)** and
- standardized outcomes: **Green / Amber / Red / Data action**.

### Step 5 — Document CCC minutes (auditability)
For every learner decision, document:
- evidence sufficiency met (Yes/No),
- rule applied and rationale,
- action plan owner, timeline, and follow-up date,
- learner notification and appeal status (if applicable).

### Step 6 — Follow-up and reassessment
Coaches implement the plan and CCC re-reviews at:
- **4–6 weeks** (Amber) or
- **8–12 weeks** (Red),  
or once evidence gaps are closed (Data action).

---

## 5. Data entry (minimum viable data)
### 5.1 Required tables
The dashboard runs on three tables:
1) **Observation table** (primary): each row is one observation/rating event  
2) **Learner master**: learner stage/rotation/coach  
3) **EPA master**: EPA domain + expected level by stage

### 5.2 Minimal required fields (Observation table)
Required:
- Learner_ID, Date, EPA_ID, Entrustment_Level, Assessor_ID, Assessor_Role, Setting  
Recommended:
- Case_Type, Narrative_Positive, Narrative_Improve, Flag

If narrative is missing, the dashboard can still compute progress but **quality KPIs** will reflect the gap.

### 5.3 Data format rules
- **Date:** ISO format `YYYY-MM-DD`
- **Entrustment_Level:** integer 1–5
- **Flag:** 0/1 (0 = none; 1 = patient safety/professionalism concern)
- **IDs:** use stable IDs (e.g., L001, A012, EPA01)

---

## 6. Interpreting decisions (quick reference)
### 6.1 Green — Progress as expected
Minimum evidence met, performance at/above expected stage level, no significant flags.

### 6.2 Amber — Targeted support (4–6 weeks)
Minimum evidence met but below expected by ~0.5–1 level, or recurring narrative themes suitable for coaching.

**Typical actions:** targeted coaching goals + 2–3 focused observations.

### 6.3 Red — Focused remediation (8–12 weeks)
Triggered by safety/professionalism flags, ≥1 level below expected with consistent narratives, or failure to improve after two Amber cycles.

**Typical actions:** remediation plan, reassessment schedule, and due process documentation.

### 6.4 Data action — Not enough evidence
Minimum evidence standard not met (missing recency/diversity/narratives/coverage).

**Typical actions:** create an assessment plan to close the evidence gap.

---

## 7. Dashboard outputs (what to expect)
### 7.1 Learner Snapshot
- sufficiency signals (met/not met),
- number of EPAs on track vs behind,
- flags count,
- follow-up status (if tracked).

### 7.2 EPA Progress
- expected vs observed entrustment by stage,
- trend over time,
- sufficiency and recency indicators.

### 7.3 Quality & Fairness
- narrative rates, actionable narrative rate,
- recency compliance,
- inter-assessor variance,
- assessor leniency/stringency signals (flagged for calibration).

---

## 8. Privacy, access, and audit trail (minimal viable)
- Share dashboard outputs only with authorized roles (CCC, program leadership, assigned coaches).
- Avoid storing direct identifiers in public demo data.
- Maintain a simple audit trail:
  - CCC minutes (decision + rationale),
  - dashboard version (v1.0.0),
  - dataset version (v1.0.0).

---

## 9. Troubleshooting
- **Dashboard shows many “Not enough evidence”:** check recency, role diversity, or missing fields.
- **High assessor variance:** consider calibration; do not delete data.
- **Low narrative rate:** introduce minimum narrative expectation and quick rater tips.

---

## 10. Versioning and updates
Use semantic versioning:
- PATCH: minor fixes (typos/formulas)
- MINOR: new KPIs/features without breaking the data model
- MAJOR: breaking changes to data model or decision logic
