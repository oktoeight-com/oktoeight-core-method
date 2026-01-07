# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/), and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

### Added
- "Decision Matrix" to Operating Logic (Unicorn, Cash Cow, Strategy, Distraction).
- "Making the Decision" section clarifying "Gatekeeper" (Selection) vs "Ranker" (Scheduling) roles.
- "Prioritization vs. Scheduling" disclaimer to ensure objectivity.
- Explicit "Wait Time" examples (Lead Time, Shipment) to the Duration formula.

### Changed
- Refine core philosophy, definitions, and examples in README.
- Updated "Project Score" formula to explicitly include Urgency multiplier (Max 20).
- Renamed "Deadline" to "Urgency" in Integrity Check to align with prioritization focus.
- Removed "Wait Time" as a dedicated column from Data Structure and Examples (retained in Duration calculation).
- Expanded "Description" and "Conclusion" definitions in Project Assessment to enforce stricter rules (min/max sentences, detailed reasoning).
- Rewrote Example 1 and Example 2 to provide substantial context and justification.

### Fixed
- Duplicate text in Operating Logic.
- Hidden character typo in Example 1 title.
- Missing columns in Examples 1 and 2 (Description, Owner, Status, Conclusion, FTE).

## [0.2.0] - 2026-01-04

### Added
- "Urgency Score" mechanism to the prioritization logic and Project Assessment.
- "Project Score" and "Efficiency Score" fields to the Project Assessment.
- "Common Questions" section.
- "Implementation" section with Software and Hardware examples.
- "Abbreviations" section.
- "Operating Logic" section detailing "Project Score" and "Efficiency Score" formulas.
- "Responsibility Model" matrix for attribute ownership.
- "Calculated over Subjective" principle to Core Philosophy.
- "The CORE Integrity Check" section with expanded logic.

### Changed
- Refined "Why CORE?" section with a comparative approach table.
- Updated "vs. The Alternatives" table comparisons and removed ICE.
- Consolidated "Assessment Pillars" and "Archetype Assignment" into "Responsibility Model".
- Expanded acronyms (CSV, MD, CFO, FTE) throughout the documentation.
- Clarified "abstract complexity points" in Core Philosophy.
- Overhauled `CONTRIBUTING.md` with strict documentation standards ("Power of Three", "Structural Blueprint", "Visual Identity").
- Updated `LICENSE` to include the correct copyright year.

### Removed
- "ICE" from the alternatives comparison.
- "The Duration Integrity Check" (replaced by consolidated CORE Integrity Check).

## [0.1.0] - 2025-12-28

### Added
- Initial release of "The CORE Method".
- Comprehensive README explaining the CORE framework.
- "vs. The Alternatives" section comparing CORE to RICE, MoSCoW, ICE, and WSJF.
- "Owner" field (Full Name) to the Project Assessment identity table.
- "Archetype Assignment" guidelines to RECOMMENDED strategies.
- Contribution guidelines.

### Changed
- Consolidated "CORE Framework" and "Assessment Pillars" into a single, unified table.
- Consolidated "Project Assessment" data structure into a single unified table.
- Standardized data structure tables with a unified "Comments" column.
- Reordered "Assessment Pillars" in README to match the CORE acronym (Confidence, Outcome, Return, Effort).
- Updated "Conclusion" field definition to include a brief reasoning summary.
