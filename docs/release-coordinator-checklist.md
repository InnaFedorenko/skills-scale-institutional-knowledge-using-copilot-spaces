# Release Coordinator Checklist

**Owner:** Release Coordinator

**Purpose:** Ensure releases and deployments are coordinated, safe, and predictable by defining responsibilities, approval gates, rollback verification, and post-release validation tasks.

Related docs:
- [Roles & Personas](./octoacme-roles-and-personas.md) — Release Coordinator persona and handoff model
- [Change Control Process](./change-control-process.md) — approved changes that flow into a release

---

## Pre-Release Readiness (T-2 Days to T-1 Day)

| # | Task | Owner | Due |
|---|---|---|---|
| 1 | Confirm release scope: verify all included changes have approved change requests | PM / Change Manager | T-2 days |
| 2 | Confirm all pull requests are merged and the main/release branch is stable | Team Leads | T-1 day |
| 3 | CI pipeline is fully green (builds, unit tests, integration tests) | Team Leads | T-1 day |
| 4 | Smoke tests and staging validation completed and signed off by QA | QA / Team | T-1 day |
| 5 | Rollback plan documented, reviewed, and confirmed testable | Release Coordinator | T-1 day |
| 6 | Rollback procedure rehearsed in staging (if high-risk release) | Release Coordinator / Ops | T-1 day |
| 7 | Monitoring and alerting confirmed active and tuned for release | Ops / SRE | T-1 day |
| 8 | Deployment runbook reviewed and available to the on-call team | Release Coordinator | T-1 day |
| 9 | Communication drafted for stakeholders and customers (what changes, when) | PM / Release Coordinator | T-1 day |
| 10 | Release notes completed and available for stakeholders | Release Coordinator | T-1 day |

- [ ] All pre-release readiness tasks complete

---

## Approval Gate (T-1 Day)

All approvals must be collected before the release window opens.

| Approver | Role | Approval | Date |
|---|---|---|---|
| | Team Lead | [ ] Approved / [ ] Rejected | |
| | Project Manager | [ ] Approved / [ ] Rejected | |
| | QA Owner | [ ] Approved / [ ] Rejected | |
| | Ops / SRE Owner | [ ] Approved / [ ] Rejected | |
| | Change Manager | [ ] Approved / [ ] Rejected | |

- [ ] All required approvals obtained

---

## Release Day

| # | Task | Owner |
|---|---|---|
| 11 | Confirm deployment window and on-call owners are available | Release Coordinator |
| 12 | Send release-start notification to stakeholders and impacted teams | PM / Release Coordinator |
| 13 | Trigger deployment per the runbook | Ops / SRE |
| 14 | Monitor deployment progress and key metrics (error rate, latency, uptime) | Ops / SRE / Release Coordinator |
| 15 | Run post-deploy smoke tests / validation checks | QA / Team |
| 16 | If failure detected: execute rollback plan and notify Release Coordinator and PM immediately | Ops / SRE |
| 17 | If rollback executed: confirm rollback success and notify stakeholders | Release Coordinator |

- [ ] Deployment completed successfully (or rollback confirmed)

---

## Rollback Verification

If a rollback is triggered, complete all of the following before closing the incident:

| # | Task | Owner |
|---|---|---|
| R1 | Confirm rollback to previous stable version completed | Ops / SRE |
| R2 | Smoke tests pass on rolled-back version | QA / Team |
| R3 | Monitoring confirms system is back to pre-release baseline | Ops / SRE |
| R4 | Stakeholders and customers notified of rollback and status | PM / Release Coordinator |
| R5 | Incident documented: what failed, why rollback was triggered | Release Coordinator |
| R6 | Change Manager notified to reopen the change request for the failed change | Release Coordinator |

- [ ] Rollback verified and documented

---

## Post-Release Validation (Within 24–48 Hours)

| # | Task | Owner | Due |
|---|---|---|---|
| 18 | Confirm success metrics are stable (error rates, latency, business KPIs) | Team / Ops | +24 hours |
| 19 | Confirm no regressions found in production monitoring | Ops / SRE | +24 hours |
| 20 | Stakeholder confirmation received (if applicable) | PM / Release Coordinator | +48 hours |
| 21 | Publish brief post-release report (what shipped, any issues, lessons learned) | Release Coordinator | +48 hours |
| 22 | Close related change requests in the change log | Change Manager | +48 hours |
| 23 | Update release notes and project documentation if needed | Release Coordinator | +48 hours |
| 24 | Add retrospective notes to the continuous improvement log | PM / Release Coordinator | +48 hours |

- [ ] Post-release validation complete

---

## Sign-Offs

| Role | Name | Signature | Date |
|---|---|---|---|
| Release Coordinator | | | |
| Project Manager | | | |
| Ops / SRE Owner | | | |
| QA Owner | | | |

---

## Common Release Scenarios

### Scenario 1: Standard Planned Release
- T-2: Scope confirmed, all PRs merged, CI green
- T-1: Staging validated, approvals collected, rollback plan reviewed, stakeholder comms sent
- Release day: Deployment triggered, monitored, post-deploy smoke tests pass, success confirmed
- +24h: Metrics stable, post-release report published, change requests closed

### Scenario 2: Hotfix (Expedited)
- Hotfix branch created from the current production tag
- Abbreviated checklist: CI must be green, QA smoke test required, rollback plan documented
- Change Manager creates an emergency change request (documented retroactively within 24 hours if needed)
- Notify stakeholders of the compressed timeline before deployment
- Full post-release validation still required within 24 hours

### Scenario 3: Failed Deployment with Rollback
- Deployment triggered; monitoring detects elevated error rate within 15 minutes
- Release Coordinator calls rollback; Ops executes rollback per the runbook
- QA confirms rollback via smoke tests; PM notifies stakeholders
- Release Coordinator documents the incident and notifies Change Manager to reopen the change request
- Team conducts a post-incident review within 48 hours
