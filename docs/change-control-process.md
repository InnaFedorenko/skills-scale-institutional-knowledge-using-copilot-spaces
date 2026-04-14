# Change Control Process

This document defines the change control process used by the **Change Manager** to capture, assess, approve, and communicate proposed changes to project scope, architecture, schedule, budget, or process.

> **Owner:** Change Manager  
> **Related roles:** [octoacme-roles-and-personas.md](octoacme-roles-and-personas.md)  
> **Related documents:** [project-sponsor-guidance.md](project-sponsor-guidance.md)

---

## Purpose

To ensure that all changes are evaluated for impact before being implemented, that approvals are obtained from the right stakeholders, and that affected parties are informed in a timely manner.

---

## Change Categories

| Category | Description | Approval Authority |
|----------|-------------|-------------------|
| **Minor** | Low risk; no impact to project baseline (schedule, budget, scope) | Change Manager |
| **Standard** | Moderate risk or minor baseline impact | Project Manager |
| **Major** | High risk or significant scope/budget/schedule change | Project Sponsor |
| **Emergency** | Critical defect or security vulnerability requiring immediate action | Project Manager (verbal) + retrospective CCB review |

---

## Change Request Flow

```
Requestor submits CR
        │
        ▼
Change Manager logs and triages (within 1 business day)
        │
        ▼
Impact Assessment (TL, SME as needed, ~2 business days)
        │
        ▼
Change Control Board (CCB) review — Change Manager facilitates
        │
   ┌────┴────┐
  Approve   Reject / Defer
        │
        ▼
Change Manager communicates decision to Requestor & stakeholders
        │
        ▼
Implementation & Verification (TL / Contributor)
        │
        ▼
Change Manager confirms outcome and closes CR
```

---

## Change Request Template

Copy and complete the following fields for each change request. Store completed forms in the project change log.

---

### Change Request (CR) Form

**CR ID:** `CR-YYYY-NNN` _(assigned by Change Manager)_

| Field | Detail |
|-------|--------|
| **Title** | Short descriptive title of the change |
| **Requestor** | Name and role |
| **Date submitted** | YYYY-MM-DD |
| **Category** | Minor / Standard / Major / Emergency |
| **Priority** | Low / Medium / High / Critical |

#### 1. Description of Change

> _What is being proposed? Be specific about what will change (code, process, document, scope, schedule, etc.)._

#### 2. Reason / Business Justification

> _Why is this change needed? What problem does it solve or what opportunity does it enable?_

#### 3. Impact Assessment

| Dimension | Impact | Detail |
|-----------|--------|--------|
| Scope | None / Low / Medium / High | |
| Schedule | None / Low / Medium / High | |
| Budget | None / Low / Medium / High | |
| Quality / Risk | None / Low / Medium / High | |
| Dependencies | None / Low / Medium / High | |

**Assessment completed by:** (Team Lead / SME name)  
**Assessment date:** YYYY-MM-DD

#### 4. Proposed Implementation Plan

> _High-level steps to implement the change, including who is responsible for each step._

| Step | Description | Owner | Target Date |
|------|-------------|-------|-------------|
| 1 | | | |
| 2 | | | |
| 3 | | | |

#### 5. Roll-Back Plan

> _How will the change be reversed if it causes unacceptable harm? Who triggers the rollback and how?_

| Field | Detail |
|-------|--------|
| Rollback trigger criteria | |
| Rollback steps | |
| Rollback owner | |
| Estimated rollback time | |

#### 6. Reviewers and Approvers

| Role | Name | Required? | Recommendation | Date |
|------|------|-----------|----------------|------|
| Change Manager | | Yes | Approve / Reject / Defer | |
| Project Manager | | Yes (Standard+) | Approve / Reject / Defer | |
| Team Lead | | Yes | Recommend | |
| SME | | If applicable | Recommend | |
| Project Sponsor | | Yes (Major/Emergency) | Approve / Reject | |

#### 7. Decision

| Field | Detail |
|-------|--------|
| **Decision** | Approved / Rejected / Deferred |
| **Decision date** | YYYY-MM-DD |
| **Decision maker** | Name and role |
| **Conditions / notes** | |

#### 8. Communication Plan

| Audience | Message | Channel | Owner | Date |
|----------|---------|---------|-------|------|
| Requestor | Decision notification | Email / Slack | Change Manager | |
| Project team | Implementation notice | Standup / Slack | Change Manager | |
| Stakeholders | Impact communication | Status report / Email | Project Manager | |

#### 9. Post-Implementation Review

| Field | Detail |
|-------|--------|
| **Verification steps** | How will the team confirm the change was implemented successfully? |
| **Verified by** | |
| **Verification date** | YYYY-MM-DD |
| **Outcome** | Successful / Partially successful / Failed — rollback triggered |
| **Lessons learned** | |

---

## Change Control Board (CCB)

The CCB meets on an as-needed basis (within 2 business days of a CR being submitted). For emergency changes, the CCB may convene within 4 hours via a video call or Slack thread.

**Standing members:**
- Change Manager (facilitator)
- Project Manager
- Team Lead(s) for the affected area

**Additional invitees (as needed):**
- Subject Matter Expert(s) relevant to the change
- Project Sponsor (for Major changes)
- Release Coordinator (if the change affects an upcoming release)

---

## Change Log

Maintain a running log of all change requests. This can be maintained as a table in the project repository or as a dedicated issue label in the project tracker.

| CR ID | Title | Category | Status | Decision Date | Decision |
|-------|-------|----------|--------|---------------|----------|
| CR-2024-001 | _Example: Add new API endpoint_ | Standard | Closed | 2024-03-15 | Approved |

---

_For escalation paths and sponsor approval guidance, see [project-sponsor-guidance.md](project-sponsor-guidance.md)._
