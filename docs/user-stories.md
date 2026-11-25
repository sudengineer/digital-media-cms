# Epics, User Stories & Acceptance Criteria

Stories use the format: **As a [user], I want [capability], so that [outcome].**

## Epic E-01 — Content Authoring
### US-001 — Create a draft
As a journalist, I want to create and save a draft article so that I can prepare content before submitting it for review.

**Acceptance criteria**
- Given I have create permission, when I start a new article, then the system creates a draft with a unique ID.
- Given required minimum fields are entered, when I save, then the draft is persisted and its last-updated timestamp is refreshed.
- Given I do not have create permission, when I call the create endpoint, then the API returns an authorization error and no item is created.

### US-002 — Edit a draft
As the content owner, I want to edit my draft so that I can improve it before review.

**Acceptance criteria**
- Given I own an editable draft, when I save changes, then the latest version is stored.
- Given the draft is locked or no longer editable, when I attempt to save, then the system explains why the update is blocked.
- Every successful save records actor and timestamp in version metadata.

## Epic E-02 — Editorial Review
### US-003 — Submit for review
As a journalist, I want to submit a complete draft for review so that an editor can assess it.

**Acceptance criteria**
- Given all mandatory fields are complete, when I submit, then status changes from Draft to In Review.
- Given mandatory metadata is missing, when I submit, then submission is blocked and field-level errors are displayed.
- The system records the submission actor and timestamp.

### US-004 — Request changes
As a section editor, I want to return content with comments so that the author knows what must be changed.

**Acceptance criteria**
- Given an item is In Review and I have review permission, when I request changes with a comment, then status becomes Changes Requested.
- The author can view the feedback and resubmit the item.
- A reviewer without permission cannot perform the transition.

### US-005 — Approve content
As a section editor, I want to approve an eligible item so that it can proceed to publishing.

**Acceptance criteria**
- Only an authorized reviewer can approve an In Review item.
- Approval records the approved content version.
- If publishable content changes after approval, the approval is invalidated according to the configured rule.

## Epic E-03 — Publishing
### US-006 — Schedule publication
As a publisher, I want to schedule approved content for a channel so that it is published at the intended time.

**Acceptance criteria**
- Only approved content can be scheduled.
- A valid future timestamp and at least one permitted channel are required.
- The selected timezone is visible before confirmation.
- The schedule is visible in the content detail and publishing queue.
- Duplicate scheduling requests do not create duplicate publication jobs.

### US-007 — Publish immediately
As a publisher, I want to publish approved content immediately so that time-sensitive stories can go live.

**Acceptance criteria**
- The item is approved and the publisher has permission.
- The system sends the approved version to the selected channel.
- Success or failure is visible to the user.
- A publication event is recorded with channel, version, actor, and timestamp.

## Epic E-04 — Governance
### US-008 — View version history
As an editor, I want to inspect previous versions so that I can understand what changed.

**Acceptance criteria**
- Version history lists version number, actor, timestamp, and change summary.
- Users without access to the content cannot view its versions.
- A previous version can be inspected without silently replacing the current version.

### US-009 — Enforce role permissions
As an administrator, I want to assign approved roles so that users can access only the actions required for their responsibilities.

**Acceptance criteria**
- Role assignment is restricted to authorized administrators.
- Permission checks are enforced by the API.
- Role changes are recorded in the audit log.
- Revoked permissions take effect within the agreed propagation window.

## Epic E-05 — Find and Monitor Content
### US-010 — Search editorial content
As an editor, I want to filter content by status, owner, type, and date so that I can find work requiring attention.

**Acceptance criteria**
- Supported filters can be combined.
- Results respect the user's access permissions.
- Empty results provide a useful empty state.
- Pagination and sorting are deterministic.
