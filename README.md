# The CORE Method

The CORE Method is a universal project prioritization framework. It is a minimalist philosophy for decision-making that prioritizes technical confidence, strategic outcome, and financial return.

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

### 3. Making the Decision
Use the **Decision Matrix** to prioritize based on the combination of Strategic Fit (Project Score) and Financial Return (Efficiency Score).

| Category | Project Score | Efficiency Score | Action | Logic |
| :--- | :--- | :--- | :--- | :--- |
| **The Unicorn** | High | High | **Do Immediately** | The perfect project. Rare. |
| **The Cash Cow** | Low | High | **Do Next** | High return funds future strategy. |
| **The Strategy** | High | Low | **Schedule** | Important, but requires funding from Cash Cows. |
| **The Distraction** | Low | Low | **Drop** | Ignore. |

> [!NOTE]
> **Prioritization vs. Scheduling**: CORE is a framework for **Prioritization**, not **Scheduling**. To maintain objectivity, it excludes explicit calendar scheduling (dates), focusing instead on relative urgency and duration.

### The CORE Integrity Check
Before finalizing the prioritization, perform the following check:

* **If Strategy (Outcome) is "Avoid" and Return is Low:** The project is a distraction. Do not execute.
* **If Duration < (Work Days / Required Full Time Equivalent (FTE)):** The timeline is physically impossible. Adjust either the Scope, the Labor, or the **Urgency**.
* **If Work Days are unknown:** The "Confidence" score is a guess. Move the project back to the research phase.

## Data Structure

The CORE Method relies on **The CORE Data Object**: a flat CSV file.

### Project Assessment (`project-assessment.csv`)
The single source of truth for all projects.

| Column | Description | Comments |
|--------|-------------|----------|
| **Title** | Unique identifier. | e.g., "OKTO-1001" |
| **Description** | Brief summary. | Min 3 sentences. Max 6 sentences. Define scope clearly. |
| **Added By** | Person who proposed the project. | e.g., "Albert Leris" |
| **Checked By** | Person who verified the data. | e.g., "Peer Reviewer" |
| **Approved By** | Person who authorized the project. | e.g., "Steering Committee" |
| **Conclusion** | Final verdict + reasoning. | Detailed reasoning linking score to verdict. |
| **Confidence Score** | Technical Feasibility (1-5). | **5:** Routine, **3:** Unknowns, **1:** High Risk |
| **Outcome Score** | Strategic Impact (1-5). | **5:** Critical, **3:** Strong Feature, **1:** Nice to have |
| **Urgency Score** | Time Sensitivity Multiplier. | **2.0:** Critical Deadline, **1.0:** Standard, **0.5:** Deferrable |
| **Work Days** | Total effort required (Man-days). | Payroll Driver |
| **Required FTE** | Intensity of resource allocation. | e.g., `0.5` (half speed), `2.0` (two people) |

| **Duration** | Calendar days to delivery. | `(Work Days / FTE) + Wait Time (Lead Time, Shipment, etc.) + Weekends` |
| **Total Cost** | Full cost (Labor + Direct). | `(Work Days * Blended Daily Rate) + External Costs` |
| **Monthly Benefit** | Expected monthly value. | Revenue increase or Cost savings after implementation |
| **Project Score** | Strategic Fit Sum (Max 20). | `(Confidence Score + Outcome Score) * Urgency Score` |
| **Efficiency Score** | Financial Return per Day. | `((Monthly Benefit * 36) - Total Cost) / Work Days` |

## Implementation

The CORE Method is tool-agnostic. It applies to any spreadsheet, database, or text file. The key is the **Project Assessment CSV**.

### Example 1: Software (Migration)

**Context:** Determine if we should migrate legacy Postgres to Relational Database Service (RDS).

**CSV Entry:**

| Column | Value | Notes |
| :--- | :--- | :--- |
| **Title** | `OKTO-1010 Database Migration` | |
| **Description** | The current Postgres instance on legacy hardware is reaching capacity limits during peak hours (95% CPU). Migration to RDS will automate backups, enable auto-scaling, and reduce maintenance overhead. This project covers the migration of the core 'Orders' database, but excludes the archive service. | |
| **Added By** | `Albert Leris` | |
| **Checked By** | `Amata Almodovar` | |
| **Approved By** | `Stanislaus Braun` | |
| **Conclusion** | Viable. The project returns a positive efficiency score ($1,300/day) and addresses a critical outcome (Scale). Confidence matches the complexity. Approved for immediate scheduling. | |
| **Confidence** | `4` | High, but some data risk. |
| **Outcome** | `4` | Critical for scaling. |
| **Urgency** | `1.0` | Standard. |
| **Work Days** | `20` | 2 Eng * 2 Weeks. |
| **Required FTE** | `2.0` | |
| **Duration** | `14` | (20 / 2) + 0 + 4 weekends |
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
| **Description** | Unit #4 has failed three times this month, causing 42 hours of cumulative downtime. Repair costs are escalating, and parts are becoming obsolete. Replacing this unit with a modern 5-axis equivalent ensures production continuity for Line 4 and increases throughput by 15%. | |
| **Added By** | `Hank MacLean` | |
| **Checked By** | `Valery Barstow` | |
| **Approved By** | `Gwen McNamara` | |
| **Conclusion** | Viable. This is a classic 'Cash Cow'. While the strategic innovation is moderate, the financial return is massive ($6,000/day efficiency). The downtime risk makes this urgent. | |
| **Confidence** | `5` | Vendor installation. |
| **Outcome** | `5` | Line 4 is down without it. |
| **Urgency** | `1.0` | Standard. |
| **Work Days** | `5` | Install time. |
| **Required FTE** | `1.0` | |
| **Duration** | `64` | (5/1) + 45 + 14 weekends |
| **Total Cost** | `150,000` | Asset + Install. |
| **Monthly Benefit** | `5,000` | Production increase. |
| **Project Score** | **10.0** | (5+5)*1 |
| **Efficiency Score** | **6,000** | ((5000*36)-150000)/5 |

## Common Questions

*   **"Why is Urgency a multiplier?"**
    *   To prevent "Urgency Bias." If we just added points, a useless project (Outcome 1) due tomorrow (+5) would beat a strategic game-changer (Outcome 5) due next month (+1). Multiplication ensures that zero-value projects remain zero, regardless of the urgency.

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