# The CORE Method

The CORE Method is a universal project prioritization and resource planning framework. It is a minimalist philosophy for decision-making that prioritizes technical confidence, strategic outcome, and financial return.

## Core Philosophy

We believe **"Complexity is the enemy of execution."** CORE is built on three immutable tenets:

1.  **Plain Text over Software as a Service (SaaS):** Decisions should be recorded in portable, universal formats, such as *.Comma-Separated Values (CSV), *.Markdown (MD), or even pen and paper. Not locked in proprietary tools.
2.  **Return over Abstraction:** We prioritize tangible financial outcomes over abstract complexity points (e.g., magic numbers or subjective scores).
3.  **Calculated over Subjective:** Decisions must be rooted in verifiable math and data, not intuition or internal politics.

## Why CORE?

Standard frameworks collapse variables into a single abstract number. CORE uses a **Tension Model** to expose trade-offs.

| Approach | Statement | Impact |
| :--- | :--- | :--- |
| **Gut Feel** | *"I think this is a good idea."* | Subjective bias: decisions based on the Highest Paid Person's Opinion (HiPPO). |
| **CORE Method** | *"This has High Return and High Confidence."* | Objective, calculated prioritization. |

### vs. The Alternatives

| Framework | Focus | Blind Spot | CORE Solution |
|-----------|-------|------------|---------------|
| **MoSCoW** | Requirements Scope | Ignores profitability/Return on Investment (ROI). | Explicit **Return** metric. |
| **RICE** | Prioritization Score | Blends risk & value into one number. | Separates **Confidence** from **Outcome**. |
| **WSJF** | Cost of Delay | Abstract math; guesswork. | Concrete **Efficiency Score** (Currency per Day). |

## The CORE Framework

CORE stands for **C**onfidence, **O**utcome, **R**eturn, and **E**ffort. These four attributes are detailed in the following structure:

| Attribute | Question | Focus |
|-----------|----------|-------|
| **C**onfidence | *"Can we do it?"* | Feasibility, risk, competency. |
| **O**utcome | *"Should we do it?"* | Strategy, safety, compliance. |
| **R**eturn | *"Is it profitable?"* | ROI, efficiency, cash. |
| **E**ffort | *"What does it cost?"* | Labor, days, budget. |

### Responsibility Model

| Role | Responsibility |
| :--- | :--- |
| **Confidence** | Tech Lead / Senior Engineer |
| **Outcome** | Product Manager / Strategist |
| **Return** | Chief Financial Officer (CFO)  / Business Analyst |
| **Effort** | Project Manager / Team Lead |

## Operating Logic

The CORE Method uses specific calculations to drive objective prioritization.

### 1. Project Score (Strategic Fit)
`Project Score = (Confidence Score + Outcome Score) * Urgency Score`

* **Focus:** Identifies projects that are both strategically critical and safe to execute.
* **Goal:** Score > 10.

### 2. Efficiency Score (Return)
`Efficiency Score = ((Monthly Benefit * 36) - Total Cost) / Work Days`

* **Focus:** Return per Day of Effort.
* **The "36" Constant:** We standardize on a **36-Month Value Horizon**. This is a tangible duration to evaluate outcome and savings without worrying about replacement by new technologies.
* **Goal:** Identifying "Cash Cows" (High Efficiency) regardless of strategic "sexiness."

### The CORE Integrity Check
Before finalizing the prioritization, perform the following check:

* **If Strategy (Outcome) is "Avoid" and Return is Low:** The project is a distraction. Do not execute.
* **If Duration < (Work Days / Required Full Time Equivalent (FTE)):** The timeline is physically impossible. Adjust either the scope, the labor, or the deadline.
* **If Work Days are unknown:** The "Confidence" score is a guess. Move the project back to the research phase.

## Data Structure

The CORE Method uses specific calculations to drive objective prioritization.

The CORE Method relies on **The CORE Data Object (Dual-Ledger)**: two flat CSV files.

### 1. Project Assessment (`project-assessment.csv`)
The single source of truth for all projects.

| Column | Description | Comments |
|--------|-------------|----------|
| **Title** | Unique identifier. | e.g., "OKTO-1001" |
| **Description** | Brief summary. | 2-3 sentences. |
| **Owner** | Full Name of responsible person. | e.g., "Albert Leris" |
| **Status** | Project state. | `Draft`, `Scheduled`, `Ongoing`, `Completed`, `On Hold` |
| **Conclusion** | Final verdict + reasoning. | `Viable`, `Conditional`, `Not Recommended` |
| **Confidence Score** | Technical Feasibility (1-5). | **5:** Routine, **3:** Unknowns, **1:** High Risk |
| **Outcome Score** | Strategic Impact (1-5). | **5:** Critical, **3:** Strong Feature, **1:** Nice to have |
| **Urgency Score** | Time Sensitivity Multiplier. | **2.0:** Critical Deadline, **1.0:** Standard, **0.5:** Deferrable |
| **Work Days** | Total effort required (Man-days). | Payroll Driver |
| **Required FTE** | Intensity of resource allocation. | e.g., `0.5` (half speed), `2.0` (two people) |
| **Duration** | Calendar days to delivery. | `(Work Days / FTE) + Wait Time + Weekends` |
| **Total Cost** | Full cost (Labor + Direct). | `(Work Days * Blended Daily Rate) + External Costs` |
| **Monthly Benefit** | Expected monthly value. | Revenue increase or Cost savings after implementation |
| **Project Score** | Strategic Fit Sum. | `Confidence Score + Outcome Score` |
| **Efficiency Score** | Financial Return per Day. | `((Monthly Benefit * 36) - Total Cost) / Work Days` |

### 2. Resource Capacity Ledger (`available-resource.csv`)
Tracks the monthly available FTE capacity to ensure realistic scheduling.

| Column | Description | Comments |
|--------|-------------|----------|
| **Month** | First day of the month. | Format: `dd.mm.yyyy` (e.g., 01.05.2026) |
| **Available FTE** | Total capacity including planned changes. | Decimal format (e.g., `3.5` for 3 full-time + 1 part-time) |
| **Comment** | Explanation of capacity sources. | e.g., "Product Manager + 2 Engineers" |

## Implementation

The CORE Method is tool-agnostic. It applies to any spreadsheet, database, or text file. The key is the **Project Assessment CSV**.

### Example 1: Software (Migration)

**Context:** Determine if we should migrate legacy Postgres to Relational Database Service (RDS).

**CSV Entry:**

| Column | Value | Notes |
| :--- | :--- | :--- |
| **Title** | `‌OKTO-1010 Database Migration` | |
| **Confidence** | `4` | High, but some data risk. |
| **Outcome** | `4` | Critical for scaling. |
| **Urgency** | `1.0` | Standard. |
| **Work Days** | `20` | 2 Eng * 2 Weeks. |
| **Total Cost** | `10,000` | Labor. |
| **Monthly Benefit** | `1,000` | Maintenance savings. |
| **Project Score** | **8.0** | (4+4)*1 |
| **Efficiency Score** | **1,300** | ((1000*36)-10000)/20 |

### Example 2: Hardware (New Machine)

**Context:** Purchase new 5-Axis CNC to replace failing unit.

**CSV Entry:**

| Column | Value | Notes |
| :--- | :--- | :--- |
| **Title** | `OKTO-1011 5-Axis CNC Procurement` | |
| **Confidence** | `5` | Vendor installation. |
| **Outcome** | `5` | Line 4 is down without it. |
| **Urgency** | `1.0` | Standard. |
| **Work Days** | `5` | Install time. |
| **Total Cost** | `150,000` | Asset + Install. |
| **Monthly Benefit** | `5,000` | Production increase. |
| **Project Score** | **10.0** | (5+5)*1 |
| **Efficiency Score** | **6,000** | ((5000*36)-150000)/5 |

## Common Questions

*   **"Why is Urgency a multiplier?"**
    *   To prevent "Urgency Bias." If we just added points, a useless project (Outcome 1) due tomorrow (+5) would beat a strategic game-changer (Outcome 5) due next month (+1). Multiplication ensures that zero-value projects remain zero, regardless of the deadline.

*   **"What if I am a solo entrepreneur?"**
    *   You are all the Archetypes. However, you must score "Return" while wearing your "Business Owner" hat, strictly separating it from your "Engineer" excitement (Confidence) or "Product" vision (Outcome).
    *   
*   **"What if I don't have a CFO?"**
    *   Assign the "Return" attribute to the business stakeholder closest to the money. The goal is logical consistency, not forensic accounting accuracy.

*   **"Why plain text (CSV)?"**
    *   Complexity prevents transparency. Proprietary tools hide logic behind paywalls. CSVs are universal, version-controllable, and force focus on the data, not the tool.

*   **"Can I add more columns?"**
    *   The core philosophy is minimalism. Every new column dilutes the decision. If you must, ensure it drives the decision, not just describes the project.

## Abbreviations

| Abbreviation | Definition |
|--------------|------------|
| **CFO** | Chief Financial Officer |
| **CORE** | Confidence, Outcome, Return, Effort |
| **CSV** | Comma-Separated Values |
| **HiPPO** | Highest Paid Person's Opinion |
| **FTE** | Full-Time Equivalent |
| **MD** | Markdown |
| **MoSCoW** | Must have, Should have, Could have, Won't have |
| **RICE** | Reach, Impact, Confidence, Effort |
| **ROI** | Return on Investment |
| **SaaS** | Software as a Service |
| **WSJF** | Weighted Shortest Job First |

## Contributing

We welcome improvements that align with our minimalist philosophy. Please see [CONTRIBUTING.md](CONTRIBUTING.md) for details on how to propose changes.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.