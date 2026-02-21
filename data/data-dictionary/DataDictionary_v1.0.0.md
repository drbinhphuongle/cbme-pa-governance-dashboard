# Data Dictionary — CBME PA Governance + Dashboard Kit (v1.0.0)

## 1. Overview
The dashboard operates with three tables:
1) **Observation** (required)
2) **Learner master** (required)
3) **EPA master** (required)

This dictionary defines minimal required fields, allowed values, and key derived metrics.

---

## 2. Table: Observation (required)
**One row = one observation / assessment event**

### Required fields
| Field | Type | Required | Allowed values / format | Notes |
|------|------|----------|--------------------------|------|
| Learner_ID | string | Yes | e.g., `L001` | Stable learner identifier |
| Date | date | Yes | `YYYY-MM-DD` | ISO date |
| EPA_ID | string | Yes | e.g., `EPA01` | Must match EPA master |
| Entrustment_Level | integer | Yes | 1–5 | See entrustment scale |
| Assessor_ID | string | Yes | e.g., `A001` | Stable assessor identifier |
| Assessor_Role | string | Yes | Faculty / SeniorResident / Resident / Nurse / AlliedHealth / Other | Use a controlled vocabulary |
| Setting | string | Yes | OPD / Ward / OR / ED / ICU / Sim / Other | Choose a standard set |

### Recommended fields
| Field | Type | Required | Allowed values / format | Notes |
|------|------|----------|--------------------------|------|
| Case_Type | string | No | free text or controlled list | For context diversity |
| Narrative_Positive | string | No | free text | What went well |
| Narrative_Improve | string | No | free text | What to improve (actionable) |
| Flag | integer | No | 0 or 1 | 1 = safety/professionalism concern |
| Observation_ID | string | No | optional | If you want unique IDs |

### Entrustment scale (1–5)
1 = Observe only  
2 = Direct supervision required  
3 = Indirect supervision (immediately available)  
4 = Independent  
5 = Independent + may supervise others

---

## 3. Table: Learner master (required)
**One row = one learner**

| Field | Type | Required | Allowed values / format | Notes |
|------|------|----------|--------------------------|------|
| Learner_ID | string | Yes | must match Observation | Primary key |
| Stage | string | Yes | PGY1 / PGY2 / PGY3+ (or local stage) | Use consistent stages |
| Rotation | string | Yes | e.g., InternalMed, Surgery, EM | Current rotation/site |
| Coach | string | No | e.g., `C001` or name | Coach/Mentor identifier |

---

## 4. Table: EPA master (required)
**One row = one EPA**

| Field | Type | Required | Allowed values / format | Notes |
|------|------|----------|--------------------------|------|
| EPA_ID | string | Yes | e.g., `EPA01` | Primary key |
| EPA_Title | string | No | e.g., “Handover & communication” | Optional but recommended |
| Domain | string | No | e.g., Communication, Patient care | Optional |
| Expected_Level_PGY1 | integer | Yes | 1–5 | Expected entrustment by stage |
| Expected_Level_PGY2 | integer | Yes | 1–5 |  |
| Expected_Level_PGY3plus | integer | Yes | 1–5 |  |

> If your program uses different stages, rename expected level fields accordingly.

---

## 5. Evidence sufficiency (derived indicators)
These indicators operationalize the Minimum Evidence Standard (per EPA).

### 5.1 Minimum Evidence Standard (per learner x EPA)
A learner is “decision-ready” for an EPA if:
- Min observations: ≥ 4  
- Min assessors: ≥ 2  
- Role diversity: ≥ 2 roles  
- Recency: ≥ 2 observations within last 8 weeks (or current rotation)  
- Context diversity: ≥ 2 settings and/or case types  
- Narrative requirement: ≥ 2 narratives; ≥ 1 actionable improvement  
- Any Flag triggers CCC review (not automatic pass)

---

## 6. Dashboard KPIs (Quality & Fairness tab) — definitions
### KPI 1 — Observation count per learner
**Definition:** total observations per learner across all EPAs  
**Formula:** count(rows) grouped by Learner_ID

### KPI 2 — Observation count per EPA (per learner)
**Definition:** observations per EPA per learner  
**Formula:** count(rows) grouped by Learner_ID + EPA_ID

### KPI 3 — Assessor diversity index (role count)
**Definition:** number of distinct assessor roles contributing to a learner’s assessments  
**Formula:** distinct_count(Assessor_Role) by Learner_ID (or by Learner_ID+EPA_ID)

### KPI 4 — Recency compliance (%)
**Definition:** proportion of observations within a defined recent window (default 8 weeks)  
**Formula:** count(Date >= today-56)/count(all) (or within rotation dates if provided)

### KPI 5 — Narrative rate (%)
**Definition:** proportion of observations with any narrative text  
**Formula:** count(Narrative_Positive not empty OR Narrative_Improve not empty) / count(all)

### KPI 6 — Actionable narrative rate (%)
**Definition:** proportion of observations with an actionable improvement note  
**Operational definition:** Narrative_Improve length ≥ 20 characters (minimal proxy) OR contains a verb-based action phrase (optional enhanced rule)  
**Formula (minimal):** count(len(Narrative_Improve) >= 20) / count(all)

### KPI 7 — Missing data rate (%)
**Definition:** proportion of observations missing required fields  
**Formula:** count(rows with missing required field)/count(all)

### KPI 8 — Assessor leniency/stringency signal (z-score)
**Definition:** assessor mean entrustment relative to overall mean  
**Formula (conceptual):** z = (mean_assessor - mean_all)/sd_all  
**Use:** flag assessors with |z| ≥ 1.5 for calibration (threshold adjustable)

### KPI 9 — Inter-assessor variance (SD by learner x EPA)
**Definition:** variability of ratings for the same learner and EPA  
**Formula:** SD(Entrustment_Level) grouped by Learner_ID + EPA_ID

### KPI 10 — EPA coverage (%)
**Definition:** proportion of EPAs with at least one observation (or meeting minimum evidence)  
**Formula:** EPAs_observed / EPAs_total (and/or EPAs_meeting_min_evidence / EPAs_total)

### KPI 11 — Red flags count
**Definition:** total number of flagged observations per learner  
**Formula:** sum(Flag==1) by Learner_ID

### KPI 12 — Time-to-decision (days) (optional if dates available)
**Definition:** days from first observation in a period to CCC decision date  
**Required fields:** CCC decision date captured in minutes or a decision log  
**Formula:** Decision_Date - min(Observation.Date)

### KPI 13 — Follow-up completion rate (optional)
**Definition:** proportion of action plans completed by the follow-up review date  
**Required fields:** action plan tracking table or structured notes in CCC minutes  
**Formula:** completed / total action plans due in period

---

## 7. Notes for implementation
- Keep controlled vocabularies for **Assessor_Role** and **Setting** to improve interpretability.
- For real deployments, consider using pseudonymized Learner_ID/Assessor_ID.
- Maintain version alignment:
  - Dataset version matches dictionary version
  - Dashboard version matches rules version
