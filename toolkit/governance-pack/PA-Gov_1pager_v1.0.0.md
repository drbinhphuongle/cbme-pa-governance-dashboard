# CBME Programmatic Assessment Governance (PA-Gov) — Minimal-Data, Decision-Oriented Model (v1.0.0)

## Purpose
Establish a practical governance model for programmatic assessment in CBME that enables **consistent, transparent, and auditable** Clinical Competency Committee (CCC) decisions using **minimal viable data** (no LMS/EHR integration required).

## Design principles
1) **Decision-oriented:** data serve decisions, not display.  
2) **Triangulation & sufficiency:** multiple sources + minimum evidence standard.  
3) **Recency matters:** prioritize recent evidence aligned with the current stage/rotation.  
4) **Fairness & consistency:** detect assessor bias/leniency and reduce unjustified variation.  
5) **Auditability:** traceable path from evidence → rule → decision → action → follow-up.  
6) **Minimal viable data:** small set of fields that still supports CCC decisions.  
7) **Feedback-to-action loop:** decisions always translate into coaching/remediation actions and monitored outcomes.

## Governance structure (roles)
- **Program Director (Accountable):** ultimate accountability for decisions, due process, resourcing, and escalation.
- **CCC Chair (Responsible):** runs CCC meetings; ensures decision rules are applied consistently.
- **CCC Members (Responsible/Consulted):** review evidence, interpret patterns, and agree on outcomes.
- **Coach/Mentor (Responsible):** creates and follows up learner action plans; reports progress to CCC.
- **Assessors (Responsible):** provide observations (entrustment ratings) and behavior-based narrative feedback.
- **Data Steward (Responsible):** runs data quality checks, maintains the dashboard, manages access and audit trail.

## Operating workflow (end-to-end)
1) **Collect** assessment data (observations, entrustment, narratives, flags).  
2) **Validate** data quality (missingness, recency, diversity, coverage).  
3) **Synthesize** evidence in the dashboard (Learner Snapshot, EPA Progress, Quality & Fairness).  
4) **Decide** in CCC using **Decision Rules + Evidence Standards** (document rationale).  
5) **Act**: coaching plan, remediation plan, or request additional evidence.  
6) **Follow up**: reassess at defined intervals and record outcomes.

## Cadence (minimal operational rhythm)
- **Weekly huddle (15–30 min):** review red flags, missing evidence, and at-risk learners.
- **Monthly CCC (60–90 min):** apply decision rules and finalize outcomes; document minutes.
- **Quarterly QI review (60 min):** review assessment quality/fairness KPIs; run calibration and system improvements.

## Due process & appeals (defensibility)
- Publish the **decision rules** and **minimum evidence standard** to learners and faculty at the start of training/rotation.
- Ensure decisions are documented with: **evidence sufficiency**, **rule(s) applied**, and **rationale**.
- Provide a clear **appeal pathway** with timelines and an independent reviewer when needed.
- Maintain professional confidentiality and appropriate access control.

## Minimal data requirements (MVD)
The system operates with three core tables:
- **Observation table:** Learner_ID, Date, EPA_ID, Entrustment_Level (1–5), Assessor_ID, Assessor_Role, Setting, Case_Type, Narrative_Positive, Narrative_Improve, Flag.
- **Learner master:** Learner_ID, Stage (e.g., PGY), Rotation, Coach.
- **EPA master:** EPA_ID, Domain, Expected_Level_by_Stage.

## Outputs (toolkit components)
- Governance model (this 1-pager) + RACI overview
- Decision rules & evidence standards
- CCC minutes template (auditable decision documentation)
- Data dictionary + demo dataset (simulated)
- Minimal dashboard (3 views) + user guide

## Versioning
This toolkit follows semantic versioning: **vMAJOR.MINOR.PATCH**.  
- PATCH: typo fixes, minor formula corrections  
- MINOR: new features/KPIs without breaking data model  
- MAJOR: breaking changes to data model or decision logic
