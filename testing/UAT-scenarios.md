# User Acceptance Testing (UAT) Scenarios

## 1. Purpose
Validate that the MVP supports critical editorial journeys and business rules from the perspective of representative users.

## 2. Entry Criteria
- UAT environment is available and stable.
- Test users exist for each agreed role.
- Test channel endpoints and test content are configured.
- Requirements and workflow states are baselined.
- No unresolved blocker defect prevents execution.

## 3. Scenarios
| ID | Scenario | Role | Expected result | Priority |
|---|---|---|---|---|
| UAT-01 | Create and save a draft article | Journalist | Draft is created and can be reopened | Critical |
| UAT-02 | Submit draft with missing required metadata | Journalist | Submission blocked with field-level errors | Critical |
| UAT-03 | Submit complete draft for review | Journalist | Status changes to In Review | Critical |
| UAT-04 | Request changes with reviewer comment | Section Editor | Status changes and feedback is visible to author | High |
| UAT-05 | Approve eligible content | Section Editor | Status becomes Approved; approved version recorded | Critical |
| UAT-06 | Attempt approval without permission | Journalist | Action denied by server; no state change | Critical |
| UAT-07 | Schedule approved content | Publisher | Schedule created with correct timezone and channel | Critical |
| UAT-08 | Attempt to schedule unapproved content | Publisher | Request rejected; no job created | Critical |
| UAT-09 | Simulate channel publication failure | Publisher / Ops | Failure is visible and recoverable; no false Published state | Critical |
| UAT-10 | Inspect version and audit history | Editor | Actor, timestamp, version, and action are visible | High |
| UAT-11 | Search by status and owner | Editor | Results match filters and access permissions | Medium |
| UAT-12 | Withdraw published content with reason | Authorized Publisher | Content is withdrawn and audit event recorded | High |

## 4. Defect Severity
- **Critical:** Security breach, data loss, unauthorized publication, or core workflow blocked.
- **Major:** Important functionality fails with no acceptable workaround.
- **Minor:** Limited impact with a reasonable workaround.
- **Cosmetic:** Visual or wording issue without functional impact.

## 5. Exit Criteria
- All critical scenarios pass.
- No open critical defects.
- Major defects have an approved resolution plan or explicit business acceptance.
- Evidence is attached to each executed scenario.
- Product owner and business representative approve UAT outcome.

## 6. Evidence Template
| Scenario ID | Tester | Test date | Actual result | Pass/Fail | Defect ID / Evidence |
|---|---|---|---|---|---|
| UAT-01 | TBD | TBD | TBD | TBD | TBD |
