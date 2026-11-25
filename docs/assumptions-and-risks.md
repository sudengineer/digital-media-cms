# Assumptions, Dependencies & Risks

## Assumptions
| ID | Assumption | Validation owner | Validation approach |
|---|---|---|---|
| A-01 | Article workflow is the highest-value MVP starting point. | Product | Stakeholder interviews and volume analysis |
| A-02 | Users can be mapped to a manageable initial role matrix. | Business / Security | Permission workshop |
| A-03 | Publishing channels expose or can expose stable APIs. | Architecture | Technical discovery |
| A-04 | Editorial taxonomy can be centrally governed. | Editorial / SEO | Taxonomy review |
| A-05 | Existing identity infrastructure can support SSO. | IT | Identity integration assessment |

## Role & Permission Assumptions

The five-role model is the proposed baseline for this case study:

- Journalist / Editor: content authoring and submission.
- Section Editor: editorial review, feedback, change requests, and approval.
- Publisher: scheduling and publishing approved content.
- SEO Specialist: SEO metadata maintenance and validation within an authorized scope.
- CMS Administrator: user, role, and permission administration.

The detailed matrix is maintained in [Role & Permission Matrix](role-permission-matrix.md). These role boundaries are proposed, not confirmed organizational policy. Section Editor authoring rights, SEO assignment scope, Publisher unpublishing rights, and administrator support access remain open for validation.

## Dependencies
- Identity and access management
- Publishing channel API contracts
- Taxonomy and metadata ownership
- Media storage and asset reference strategy
- Monitoring, alerting, and analytics
- Editorial policy and operational support model

## Risks
| ID | Risk | Probability | Impact | Mitigation |
|---|---|---:|---:|---|
| R-01 | Ambiguous approval ownership delays delivery. | Medium | High | Agree role matrix and state transitions before build |
| R-02 | Channel API instability causes failed publications. | Medium | High | Contract testing, retries, idempotency, failure queue |
| R-03 | Metadata rules are incomplete or inconsistent. | High | Medium | Define field ownership and validation by content type |
| R-04 | Permission gaps expose restricted actions. | Low/Medium | High | Server-side authorization tests and security review |
| R-05 | Scope expands before MVP workflow is validated. | Medium | Medium | Explicit MVP boundary and change-control process |
| R-06 | Users continue maintaining parallel trackers. | Medium | Medium | Co-design workflow, training, adoption measurement |

## Decision Log
| Date | Decision | Rationale | Status |
|---|---|---|---|
| 2026-11-18 | Start with article workflow for MVP. | Narrow, testable end-to-end vertical slice. | Proposed |
| 2026-11-18 | Treat all numeric targets as hypotheses until baselines exist. | Avoid presenting invented outcomes as measured facts. | Agreed for case study |


## Open Questions

| ID | Question | Why it matters | Suggested owner |
|---|---|---|---|
| OQ-01 | Can Section Editors create drafts, or are they limited to review and approval? | Determines authoring permissions and workflow separation. | Editorial leadership |
| OQ-02 | Are SEO Specialists global users or scoped to assigned sections/content? | Determines content visibility and metadata permissions. | SEO lead / Product |
| OQ-03 | Can Publishers unpublish content without a second approval? | Defines operational control for externally visible actions. | Publishing operations |
| OQ-04 | Does CMS Administrator need exceptional read access to content for support? | Balances supportability with least-privilege access. | IT / Security |
| OQ-05 | Which roles can view content across sections, and under what conditions? | Defines list, search, and direct-link authorization. | Editorial leadership / Security |
| OQ-06 | Can SEO metadata changes after editorial approval require re-approval? | Prevents unclear ownership of publish-ready content. | Editorial / SEO / Product |
