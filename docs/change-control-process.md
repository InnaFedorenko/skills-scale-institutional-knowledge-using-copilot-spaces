# Change Control Process

**Owner:** Change Manager

**Purpose:** Standardize how proposed changes to scope, process, or major technical decisions are captured, assessed, approved, and scheduled to reduce risk and maintain traceability.

Related docs:
- [Roles & Personas](./octoacme-roles-and-personas.md) — Change Manager and Release Coordinator roles
- [Release Coordinator Checklist](./release-coordinator-checklist.md) — handoff for approved changes going to deployment

---

## Change Request Template

Fill in all required fields when submitting a change request. Incomplete requests will be returned to the requester.

```
Change Request ID:   [auto-assigned or sequential, e.g., CR-2024-001]
Title:
Requester:
Date submitted:
Affected project / component:

Description of change:

Reason / justification:

Proposed implementation approach:

Rollback plan:
```

---

## Impact Assessment

The Change Manager coordinates completion of this section with the relevant Team Lead(s) and SME(s).

```
Scope impact:      [ ] Low  [ ] Medium  [ ] High
Description of scope impact:

Timeline impact:   Estimated days/weeks: ___
Description of timeline impact:

Cost impact:       Estimate (or N/A):
Description of cost impact:

Risk assessment:
  - Risk 1:  [description] — Mitigation: [mitigation]
  - Risk 2:  [description] — Mitigation: [mitigation]

Resources required: [list teams, SMEs, or tools needed]
```

---

## Required Reviewers & Approvers

The following roles are the recommended approvers. Adjust based on impact level.

| Role | Required When | Name | Approval |
|---|---|---|---|
| Team Lead | Always | | [ ] Approved / [ ] Rejected |
| Project Manager | Always | | [ ] Approved / [ ] Rejected |
| Subject Matter Expert | Technical or compliance impact | | [ ] Approved / [ ] Rejected |
| Release Coordinator | Change requires deployment | | [ ] Approved / [ ] Rejected |
| Project Sponsor | High impact (major scope, budget, or timeline shift) | | [ ] Approved / [ ] Rejected |

---

## Approval Checklist

- [ ] Change request template fully completed
- [ ] Impact assessment completed (scope, timeline, cost, risk)
- [ ] All required reviewers have been engaged
- [ ] Rollback plan documented and reviewed
- [ ] Communication plan defined (who is notified, when, via what channel)
- [ ] Project Sponsor approval obtained (if high impact)
- [ ] Change scheduled with Release Coordinator or Project Manager

---

## Change Request Flow

```
1. Submit
   Requester (Contributor, PM, or Stakeholder) submits a change request using
   the template above.

2. Triage
   Change Manager reviews for completeness. Returns to requester if incomplete.
   Assigns impact assessment tasks to Team Lead and/or SME.

3. Assess
   Team Lead / SME produces estimates (timeline, cost) and risk analysis.
   Change Manager collects and documents findings.

4. Review & Approve / Reject
   Required reviewers (see table above) review and record decisions.
   - Approved: proceed to Schedule step.
   - Rejected: Change Manager documents reason and notifies requester.

5. Schedule
   Change Manager hands off approved change to Release Coordinator (for deployment)
   or Project Manager (for non-release work) for scheduling.
   (See: ./release-coordinator-checklist.md)

6. Communicate
   Notify impacted teams and stakeholders of the scheduled change, expected
   window, and rollback procedure before execution.

7. Execute
   Release Coordinator runs pre-release/deployment checks.
   Change is implemented per the schedule.

8. Post-Change Review
   Release Coordinator or PM confirms success metrics.
   Change Manager closes the change request and documents lessons learned.
   Retrospective notes are fed back into process documentation.
```

---

## Communication & Documentation Guidelines

- Notify impacted teams and stakeholders **before** the change is scheduled.
- Publish the change request record to the project decisions log (linked from the project README).
- After execution, update the change request with results, rollback status (if triggered), and retrospective notes.
- For emergency changes, document retroactively within 24 hours of execution.

---

## Sample Change Request (Completed Example)

```
Change Request ID:   CR-2024-007
Title:               Add audit logging to the user authentication service
Requester:           Alex (Team Lead, Platform)
Date submitted:      2024-03-15
Affected project:    OctoAcme Platform — Authentication Service

Description:
  Add structured audit logs for all authentication events (login, logout,
  failed attempts) to support a new compliance requirement.

Reason / justification:
  Required by the upcoming SOC 2 audit. Deadline: 2024-04-01.

Proposed implementation:
  Extend the AuthService to emit structured log events to the centralized
  logging pipeline. Estimated 3 developer-days.

Rollback plan:
  Feature-flag controls logging emission. Disable flag to roll back without
  a deployment. Flag owner: Platform Team Lead.
```

Impact assessment for CR-2024-007:
- Scope impact: Low — confined to AuthService
- Timeline impact: 3 developer-days; fits within current sprint
- Cost impact: No additional infrastructure cost
- Risk: Log volume increase may affect storage costs — mitigated by sampling config
- Resources: Platform Team Lead, Security SME (compliance review)
