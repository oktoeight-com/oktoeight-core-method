# Oktoeight CORE Method

## Introduction

The Oktoeight CORE Method is a universal project prioritization and resource planning framework. It is a minimalist philosophy for decision-making that prioritizes technical confidence, strategic outcome, and financial return.

## Core Philosophy

We believe complexity is the enemy of execution. CORE is built on two immutable tenets:

1.  **Plain Text over SaaS:** Decisions should live in portable, universal formats (CSV/Markdown), not locked in proprietary tools.
2.  **Return over Abstraction:** We prioritize tangible financial outcomes over abstract complexity points.

## Why CORE?

Standard frameworks often collapse variables into a single abstract number. CORE uses a **Tension Model** to expose trade-offs:

* **Strategy (Outcome):** Should we do it? (Brand/Compliance)
* **Finance (Return):** Is it profitable? (ROI/Efficiency)
* **Technical (Confidence):** Can we do it? (Feasibility/Risk)

By scoring on independent axes, we identify:

* **Ideal Project:** High Outcome / High Return.
* **Strategic Necessity:** High Outcome / Low Return (Compliance).
* **Cash Cow:** Low Outcome / High Return (Pure Profit).
* **Avoid:** Low Outcome / Low Return.

## The CORE Framework

CORE stands for:

| Attribute | Question | Focus |
|-----------|----------|-------|
| **C**onfidence | *Can we do it?* | Technical feasibility, risk, and competency. |
| **O**utcome | *Should we do it?* | Strategic value, safety, compliance, and brand. |
| **R**eturn | *Is it profitable?* | Financial ROI and efficiency score. |
| **E**ffort | *What does it cost?* | Actual resource time in Work Days. |

## Assessment Pillars

The CORE Method evaluates projects through three primary lenses.

| Pillar | Focus | Dimensions | Archetype Suggestion |
|--------|-------|------------|----------------------|
| **Value** | *Should we do it?* & *Is it profitable?* | **Outcome** (Strategy) + **Return** (Economy) | Product Manager, Strategist, CFO |
| **Feasibility** | *Can we do it?* | **Confidence** (Technical) | Tech Lead, Senior Engineer |
| **Effort** | *What does it cost?* | **Effort** (Execution) | Project Manager, Team Lead |

### Verification
A final **Integrity Check** (Validator) is performed to ensure data consistency. Specifically, `Duration` must satisfy the minimum constraints of `Work Days` and `FTE` allocation.

## Data Structure

The CORE Method relies on a **Dual-Ledger** system: two flat CSV files.

### 1. Project Assessment (`project-assessment.csv`)
The single source of truth for all projects.

#### Identity & Scope
| Column | Description |
|--------|-------------|
| **Title** | Unique identifier (e.g., "FP-4100"). |
| **Description** | Brief summary (2-3 sentences). |
| **Status** | `Draft`, `Scheduled`, `Ongoing`, `Completed`, `On Hold`. |
| **Conclusion** | `Viable`, `Conditional`, `Not Recommended`. |

#### CORE Scoring (Rubric 1-5)
| Column | Description | Scoring Legend |
|--------|-------------|----------------|
| **Confidence Score** | Technical Feasibility. | **5:** Routine/Done before.<br>**3:** Some unknowns.<br>**1:** High risk/New tech. |
| **Outcome Score** | Strategic Impact. | **5:** Critical/Compliance.<br>**3:** Strong feature.<br>**1:** Nice to have. |

#### Resources & Finance
| Column | Description | Math / Notes |
|--------|-------------|--------------|
| **Work Days** | Total effort required (Man-days). | *Payroll Driver.* |
| **Required FTE** | Intensity of resource allocation. | e.g., `0.5` (half speed), `2.0` (two people). |
| **Duration** | Calendar days to delivery. | Formula: `(Work Days / FTE) + Wait Time + Weekends`. |
| **Total Cost** | Full cost (Labor + Direct). | `(Work Days * Blended Daily Rate) + External Costs`. |
| **Monthly Benefit** | Expected monthly value (post-launch). | Revenue increase or Cost savings. |

### 2. Resource Capacity Ledger (`available-resource.csv`)
Tracks the monthly available FTE capacity to ensure realistic scheduling.

| Column | Description | Example |
|--------|-------------|---------|
| **Month** | First day of the month (dd.mm.yyyy). | `01.05.2026` |
| **Available FTE** | Total capacity including planned changes. | `3.5` |
| **Comment** | Explanation of capacity sources. | `Product Manager + 2 Engineers` |

## Scoring Logic

The CORE Method uses specific calculations to drive objective prioritization.

### 1. Project Score (Strategic Fit)
`Confidence Score + Outcome Score = Project Score (Max 10)`

* **Focus:** Identifies projects that are both strategically critical and safe to execute.
* **Goal:** Score > 7.

### 2. Efficiency Score (Return)
`((Monthly Benefit * 36) - Total Cost) / Work Days = Efficiency Score`

* **Focus:** Return per Day of Effort.
* **The "36" Constant:** We standardize on a **36-Month Value Horizon**. This is a tangible duration to evaluate outcome and savings without worrying about replacement by new technologies.
* **Goal:** Identifying "Cash Cows" (High Efficiency) regardless of strategic "sexiness."

### 3. The Duration Integrity Check
Before scheduling, verify the relationship between effort and time:

`Duration >= (Work Days / Required FTE)`

* **Logic:** `Work Days` are the actual days of labor. `Duration` is the timeline (including waiting).
* **Example:** If a project needs **10 Work Days** but you only allocate **0.5 FTE**, the minimum Duration is **20 Days**.
* **Note:** Duration is usually *higher* than the raw math suggests due to weekends and external waiting, but it can never be *lower*.

## Contributing

We welcome improvements that align with our minimalist philosophy. Please see [CONTRIBUTING.md](CONTRIBUTING.md) for details on how to propose changes.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.