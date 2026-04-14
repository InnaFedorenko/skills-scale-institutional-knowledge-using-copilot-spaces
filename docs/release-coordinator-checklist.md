# Release Coordinator Checklist

This checklist is used by the **Release Coordinator** to manage every release from planning through post-deployment verification. Complete all applicable items and record the date and owner for each step.

> **Owner:** Release Coordinator  
> **Supporting roles:** Project Manager, Team Lead, Change Manager, QA  
> **Related roles:** [octoacme-roles-and-personas.md](octoacme-roles-and-personas.md)  
> **Related documents:** [octoacme-release-and-deployment.md](octoacme-release-and-deployment.md) | [change-control-process.md](change-control-process.md)

---

## Release Metadata

| Field | Value |
|-------|-------|
| Release name / version | |
| Target release date | |
| Release type | Scheduled / Hotfix / Emergency |
| Release Coordinator | |
| Project Manager | |
| Team Lead | |
| Change Request ID (if applicable) | |

---

## 1. Pre-Release Planning (≥ 5 business days before release)

| # | Item | Owner | Done |
|---|------|-------|------|
| 1.1 | Confirm release scope with the Project Manager and Team Lead | RC | ☐ |
| 1.2 | Verify all associated change requests are approved (see [change-control-process.md](change-control-process.md)) | RC / Change Manager | ☐ |
| 1.3 | Identify and confirm the release change window with operations/infrastructure | RC | ☐ |
| 1.4 | Communicate planned release date and scope to Stakeholders | RC / PM | ☐ |
| 1.5 | Confirm rollback plan is documented and tested (see Section 5) | RC / TL | ☐ |
| 1.6 | Identify any dependencies on external teams or services; confirm readiness | RC / PM | ☐ |
| 1.7 | Confirm that release notes or changelog are drafted | TL / RC | ☐ |

---

## 2. Build & QA Readiness (2–3 business days before release)

| # | Item | Owner | Done |
|---|------|-------|------|
| 2.1 | Confirm release candidate build is tagged in the repository | TL | ☐ |
| 2.2 | All automated tests pass on the release candidate | TL / QA | ☐ |
| 2.3 | Manual / exploratory testing completed for high-risk areas | QA | ☐ |
| 2.4 | All open blocking or critical bugs are resolved or risk-accepted | TL / PM | ☐ |
| 2.5 | QA sign-off obtained for release candidate | QA | ☐ |
| 2.6 | Deployment runbook / scripts reviewed and validated in staging | TL / RC | ☐ |
| 2.7 | Database migrations (if any) reviewed and tested in staging | TL | ☐ |

---

## 3. Go / No-Go Review (1 business day before release)

Conduct the go/no-go review meeting with the Project Manager, Team Lead, QA, and Change Manager. Document the decision below.

| # | Item | Owner | Done |
|---|------|-------|------|
| 3.1 | All pre-release and QA checklist items are complete | RC | ☐ |
| 3.2 | No open blocking issues | TL / QA | ☐ |
| 3.3 | Rollback plan is confirmed and ready | TL / RC | ☐ |
| 3.4 | All required approvals (change requests, sponsor sign-off if applicable) are in place | RC / Change Manager | ☐ |
| 3.5 | On-call / incident response team is notified and available during the release window | RC | ☐ |
| 3.6 | Go / No-Go decision recorded | PM / Sponsor (Major releases) | ☐ |

**Go / No-Go Decision:**

| Field | Value |
|-------|-------|
| Decision | ☐ Go &nbsp; ☐ No-Go &nbsp; ☐ Conditional Go |
| Decision maker | |
| Decision date & time | |
| Conditions (if conditional) | |

---

## 4. Deployment (Release Day)

| # | Item | Owner | Done |
|---|------|-------|------|
| 4.1 | Send release start notification to Stakeholders | RC | ☐ |
| 4.2 | Execute deployment runbook step-by-step | TL / RC | ☐ |
| 4.3 | Monitor deployment logs and dashboards in real time | TL | ☐ |
| 4.4 | Run smoke tests immediately after deployment | QA / TL | ☐ |
| 4.5 | Confirm key user-facing features are operational | QA | ☐ |
| 4.6 | Confirm monitoring alerts are configured and active | TL | ☐ |
| 4.7 | Send release completion notification to Stakeholders | RC | ☐ |

---

## 5. Rollback Plan

Complete this section during pre-release planning and review it at go/no-go.

| Field | Detail |
|-------|--------|
| Rollback trigger criteria | _(e.g., critical error rate >1%, service unavailable for >5 min)_ |
| Rollback decision authority | Release Coordinator + Project Manager (or Sponsor for Major releases) |
| Rollback steps | _(reference deployment runbook rollback section)_ |
| Estimated rollback time | |
| Rollback test date | _(confirm rollback was tested in staging)_ |

---

## 6. Post-Release Verification (within 24 hours of deployment)

| # | Item | Owner | Done |
|---|------|-------|------|
| 6.1 | Monitor error rates and performance metrics for 24 hours post-release | TL | ☐ |
| 6.2 | Review support tickets or user feedback for release-related issues | PM / RC | ☐ |
| 6.3 | Confirm all release notes are published to the appropriate channel | RC | ☐ |
| 6.4 | Close associated change requests in the change log | Change Manager | ☐ |
| 6.5 | Update project documentation to reflect the new release state | TL / RC | ☐ |
| 6.6 | Capture lessons learned and feed back to the Project Manager | RC | ☐ |

---

## 7. Release Sign-Off

| Field | Value |
|-------|-------|
| Release outcome | ☐ Successful &nbsp; ☐ Partial (see notes) &nbsp; ☐ Rolled back |
| Release Coordinator sign-off | |
| Project Manager sign-off | |
| Sign-off date | |
| Notes / follow-up items | |

---

_For change approval requirements, see [change-control-process.md](change-control-process.md)._  
_For release process overview, see [octoacme-release-and-deployment.md](octoacme-release-and-deployment.md)._  
_For role definitions, see [octoacme-roles-and-personas.md](octoacme-roles-and-personas.md)._
