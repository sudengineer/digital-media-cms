# Requirements Traceability Matrix (RTM)

## 1. Purpose

This matrix connects each user story and tracked functional requirement to its backlog item and User Acceptance Testing (UAT) coverage. It is used to identify untested requirements, orphan backlog items, and tests that do not have a clear requirement source.

## 2. Traceability Matrix

| Requirement / User Story | Backlog reference | UAT coverage | Coverage status |
|---|---|---|---|
| US-001 — Create a draft | US-001 | UAT-01 | Covered |
| US-002 — Edit a draft | US-002 | UAT-16 | Covered |
| US-003 — Submit for review | US-003 | UAT-02, UAT-03 | Covered |
| US-004 — Request changes | US-004 | UAT-04 | Covered |
| US-005 — Approve content | US-005 | UAT-05, UAT-06 | Covered |
| US-006 — Schedule publication | US-006 | UAT-07, UAT-08 | Covered |
| US-007 — Publish immediately | US-007 | UAT-09, UAT-15 | Covered |
| US-008 — View version history | US-008 | UAT-10 | Covered |
| US-009 — Enforce role permissions | US-009 | UAT-06, UAT-14, UAT-18 | Covered |
| US-010 — Search editorial content | US-010 | UAT-11 | Covered |
| US-011 — Maintain SEO metadata | US-011; FR-10 | UAT-13, UAT-14 | Covered |
| US-012 — Autosave draft changes | US-012; FR-03 | UAT-17 | Covered |
| US-013 — Unpublish or withdraw published content | US-013; FR-15 | UAT-12 | Covered |

## 3. Coverage Summary

- **13 of 13 user stories** have at least one linked backlog item and UAT scenario.
- **3 of 3 separately tracked functional requirement references** are linked to a user story: FR-03 → US-012, FR-10 → US-011, and FR-15 → US-013.
- **18 UAT scenarios** are maintained in the UAT suite.
- Coverage indicates that a scenario is defined; it does not mean the scenario has been executed or passed.

## 4. Traceability Rules

1. Every approved user story must have a unique ID and a corresponding backlog item.
2. Every user story must link to one or more UAT scenarios before release acceptance.
3. Backlog entries using functional requirement IDs (for example, FR-03) must reference the user story that delivers the requirement.
4. If a requirement changes, its acceptance criteria, backlog item, and linked UAT scenarios must be reviewed together.
5. UAT execution evidence and Pass/Fail results are recorded in the UAT evidence log; this matrix tracks coverage, not execution results.
6. A UAT scenario without a requirement link must be reviewed to determine whether it represents a missing requirement or unnecessary test scope.

## 5. Change Impact Examples

| Change | Items to review |
|---|---|
| Draft validation rules change | US-003, backlog US-003, UAT-02 and UAT-03 |
| SEO field permissions change | US-011, backlog US-011 / FR-10, UAT-13 and UAT-14 |
| Publication withdrawal policy changes | US-013, backlog US-013 / FR-15, UAT-12 |
| Autosave timing or failure behavior changes | US-012, backlog US-012 / FR-03, UAT-17 |

## 6. Ownership

The Product Manager / Business Analyst maintains requirement-to-backlog traceability. The QA / UAT owner maintains test scenario references and execution evidence. Changes to requirements are reviewed with the relevant business owner before the baseline is updated.
