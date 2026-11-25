# Product Metrics & KPI Framework

## 1. North Star Metric
**Weekly Successfully Published Content Items (WSPCI)**

Definition: Count of distinct content items successfully published to at least one eligible channel during a calendar week.

Why it is useful: It reflects the platform's core job of helping editorial teams move content through to successful publication. It must be interpreted alongside quality and reliability guardrails; maximizing volume alone is not the goal.

## 2. KPI Tree
- **Editorial throughput**
  - Successfully published items per week
  - Median draft-to-publication time
  - Median review cycle time
- **Content readiness**
  - First-pass metadata completeness rate
  - Submission rework rate
- **Publishing reliability**
  - On-time publication rate
  - Publication success rate
  - Duplicate publication incident rate
- **Adoption and usability**
  - Weekly active editorial users
  - Workflow completion rate
  - Task abandonment rate
- **Governance**
  - Unauthorized action attempts
  - Audit event completeness
  - Time to resolve publishing incidents

## 3. Metric Definitions
| Metric | Formula | Frequency |
|---|---|---|
| On-time publication rate | Items published within agreed tolerance of scheduled time ÷ items due for publication × 100 | Weekly |
| Publication success rate | Successful publication attempts ÷ all publication attempts × 100 | Daily / weekly |
| First-pass metadata completeness | Submissions accepted without metadata correction ÷ total submissions × 100 | Weekly |
| Median review cycle time | Median time from In Review to Approved or Changes Requested | Weekly |
| Workflow completion rate | Items reaching Published ÷ items entering In Review, for a defined cohort | Weekly |
| Weekly active editorial users | Distinct eligible users performing a meaningful CMS action in a week | Weekly |

## 4. Proposed Initial Targets (Hypotheses)
Targets must be reset after baseline measurement and stakeholder agreement.

- Improve on-time publication rate by 10 percentage points within one quarter of adoption.
- Improve first-pass metadata completeness by 15 percentage points.
- Reduce median review cycle time by 15%.
- Maintain publication success rate at or above 99.5% after stabilization.

These are illustrative targets, not actual product results.

## 5. Guardrail Metrics
- Content correction / takedown rate
- Unauthorized publication attempts
- Duplicate publishing incidents
- Critical accessibility defects
- User-reported workflow errors

## 6. Instrumentation Principles
- Define event names and properties before implementation.
- Use stable content IDs and correlation IDs.
- Include role and workflow state where appropriate.
- Do not collect article body text or unnecessary personal data in analytics events.
- Document event ownership, retention, and access controls.
- Validate event quality before using metrics for product decisions.

## 7. Review Cadence
- Daily: publishing reliability and incident review during launch.
- Weekly: workflow funnel, review time, and metadata completeness.
- Monthly: adoption, outcome trends, and roadmap implications.
