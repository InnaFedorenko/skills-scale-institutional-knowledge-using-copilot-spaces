# OctoAcme Roles & Personas

This document defines typical roles and responsibilities used in OctoAcme project docs and exercises. It has been expanded to include new personas that improve clarity, accountability, and handoffs across the project lifecycle.

Related process docs:
- [Onboarding Checklist](./onboarding-checklist.md)
- [Change Control Process](./change-control-process.md)
- [Project Sponsor Guidance](./project-sponsor-guidance.md)
- [Release Coordinator Checklist](./release-coordinator-checklist.md)

---

## Existing Roles

### Developers

#### Role Summary
Developers design, build, test, and deliver software components. They collaborate with product and project leads to implement features that meet acceptance criteria and quality standards.

#### Responsibilities
- Implement features and fixes to meet acceptance criteria
- Write and maintain tests and documentation
- Participate in design and code reviews
- Assist in estimating and planning work
- Help identify technical risks and propose mitigations

#### Goals
- Deliver reliable, maintainable code
- Reduce cycle time from idea to production
- Maintain high test coverage and observability

#### Typical Communication
- Daily standups and sprint planning
- PR descriptions and code review comments
- Technical design docs when needed

---

### Product Managers

#### Role Summary
Product Managers define what should be built to deliver customer and business value. They own the product vision, prioritize the backlog, and measure outcomes.

#### Responsibilities
- Define problem statements and success metrics
- Prioritize the roadmap and backlog
- Collaborate with stakeholders and engineering on trade-offs
- Validate solutions through user research and metrics

#### Goals
- Maximize customer value and impact
- Make clear, data-driven prioritization decisions
- Ensure product-market fit and usability

#### Typical Communication
- Weekly alignment with PM and engineering leads
- Roadmap updates and stakeholder briefings
- Acceptance criteria and feature specs

---

### Project Managers

#### Role Summary
Project Managers coordinate delivery activities, manage schedules, risks, and communications. They enable the team to deliver on commitments efficiently.

#### Responsibilities
- Create and maintain project plans and timelines
- Manage risks, dependencies, and resource constraints
- Facilitate meetings (kickoff, planning, retrospectives)
- Ensure consistent project documentation and status reporting
- Coordinate cross-team and stakeholder communication

#### Goals
- Deliver projects on time and within scope
- Minimize unplanned work and escalations
- Maintain transparency and alignment across stakeholders

#### Typical Communication
- Weekly status updates and stakeholder reports
- Risk registers and decision logs
- Coordination via project boards and meeting facilitation

---

## New Personas

The following personas have been added to address gaps in onboarding, change management, executive oversight, domain expertise, and release coordination.

---

### Onboarding Coordinator

**Summary:** Ensures new project members are integrated quickly and effectively so they can contribute with minimal ramp-up time.

#### Key Responsibilities
- Provision accounts, tool access, and workspace on Day 0–2
- Share project documentation and role expectations with new members
- Schedule introductory meetings and required training sessions
- Verify access and task readiness, and sign off on completion

#### Typical Interactions / Handoffs
- Works with the **Project Manager** to determine onboarding scope and schedule before a new member's start date
- Coordinates with the **Team Lead** for role-specific training and initial task assignment
- Notifies **Contributors** and **Stakeholders** when a new member is ready to contribute
- Hands off the new member to the Team Lead once environment setup and first tasks are confirmed (end of week 1)

#### Acceptance / Decision Authority
- Can approve standard account and tool access requests
- Escalates non-standard access, security exceptions, or contractor onboarding to the Project Manager or Security Owner

#### Example Scenarios
1. **New developer joins:** The Onboarding Coordinator provisions repository access, schedules a meet-and-greet with the Team Lead, and confirms the new member can run the local dev environment by day 3. The Team Lead signs off at the end of week 1.
2. **Contractor arrival:** Coordinates temporary account setup and ensures contract-based access expiry is documented and communicated to the Security Owner.

See the full checklist: [Onboarding Checklist](./onboarding-checklist.md)

---

### Change Manager

**Summary:** Manages proposed changes to scope, process, or major technical decisions to minimize risk and maintain traceability.

#### Key Responsibilities
- Triage submitted change requests and capture required metadata (title, requester, date, rationale)
- Coordinate impact assessments covering timeline, cost, and risk
- Manage the approval workflow and document decisions
- Track scheduled changes and facilitate post-change reviews

#### Typical Interactions / Handoffs
- Receives change requests from **Contributors**, **Project Managers**, or **Stakeholders**
- Coordinates impact assessments with **Team Leads** and **Subject Matter Experts (SMEs)**
- Hands off approved changes to the **Release Coordinator** or **Project Manager** for scheduling
- Escalates high-impact changes (budget, major scope) to the **Project Sponsor**

#### Acceptance / Decision Authority
- Can reject incomplete change requests or request additional information
- Major approvals (scope, cost, or risk above agreed thresholds) require Project Manager and/or Project Sponsor sign-off per the [Change Control Process](./change-control-process.md)

#### Example Scenarios
1. **Feature scope change:** Change Manager collects estimates from the Team Lead, assesses impact with the Project Manager, and escalates to the Project Sponsor if the change shifts timeline or cost materially.
2. **Emergency rollback:** After detecting a regression in production, Change Manager initiates the rollback plan, coordinates with the Release Coordinator, and communicates status to Stakeholders.

See the full template: [Change Control Process](./change-control-process.md)

---

### Project Sponsor

**Summary:** Executive-level champion who ensures the project has resources, strategic visibility, and authority to resolve escalated decisions.

#### Key Responsibilities
- Advocate for project funding and resources at the organizational level
- Resolve escalated conflicts related to strategy, cross-team resources, or major trade-offs
- Approve major scope, budget, or timeline changes that exceed Project Manager authority
- Participate in key milestone reviews and scheduled sponsor check-ins

#### Typical Interactions / Handoffs
- Receives escalations from the **Project Manager** for decisions outside the PM's authority
- Reviews and signs off on major change requests submitted by the **Change Manager**
- Coordinates with organizational **Stakeholders** to unblock resources or resolve competing priorities

#### Acceptance / Decision Authority
- Final approval authority on major scope changes, budget increases, and strategic trade-offs
- May delegate specific decisions with explicit written authority

#### Example Scenarios
1. **Resource shortfall:** The Project Manager escalates competing resource requests from two teams. The Project Sponsor decides on the allocation or recruits additional funding to cover both needs.
2. **Major scope change:** A new regulatory requirement doubles the implementation effort. The Project Sponsor approves the timeline extension and additional budget before scheduling begins.

See detailed guidance: [Project Sponsor Guidance](./project-sponsor-guidance.md)

---

### Subject Matter Expert (SME)

**Summary:** Provides deep domain or technical expertise to clarify requirements, validate designs, and reduce rework.

#### Key Responsibilities
- Advise on technical or domain-specific decisions during design and planning
- Review proposed changes, architecture decisions, and risk assessments
- Participate in acceptance criteria reviews and technical sign-offs
- Help identify constraints or regulatory requirements that affect delivery

#### Typical Interactions / Handoffs
- Engaged by the **Project Manager** or **Team Lead** for scoped design reviews or risk assessments
- Works with **Contributors** to clarify requirements and provide sign-off for deliverables
- Feeds findings into **Change Manager** when a design constraint requires a scope change

#### Acceptance / Decision Authority
- Can approve technical designs within agreed domain boundaries
- Cross-cutting or architectural decisions are escalated to the Project Manager or an Architecture Board

#### Example Scenarios
1. **Complex integration:** An SME identifies a vendor API constraint that requires changes to the design. They work with the Team Lead to adjust the approach and update the schedule before implementation begins.
2. **Compliance check:** An SME confirms that a proposed change meets regulatory requirements before the Release Coordinator schedules the release.

---

### Release Coordinator

**Summary:** Orchestrates releases and deployments, ensuring pre-release checks, approval gates, rollout, and post-release validation are all complete.

#### Key Responsibilities
- Maintain the release schedule and run release readiness reviews
- Coordinate deployment owners, rollback plans, and approval gates
- Communicate release status to Stakeholders before, during, and after deployment
- Verify post-release success metrics and hand off monitoring to responsible teams

#### Typical Interactions / Handoffs
- Receives approved changes from the **Change Manager** and schedules the release with the **Project Manager** and **Team Leads**
- Coordinates with **SMEs** and Ops/SRE teams for deployment and rollback procedures
- Notifies **Stakeholders** of release windows and outcomes
- Hands off post-release monitoring tasks to the responsible team after confirming a successful deployment

#### Acceptance / Decision Authority
- Can approve release readiness when all pre-release gates are green
- Can halt or roll back a release if critical checks fail, notifying the Project Manager and Stakeholders immediately

#### Example Scenarios
1. **Major release day:** Release Coordinator verifies all approvals are in place, triggers deployment, monitors key metrics, and confirms rollback readiness with Ops/SRE before declaring success.
2. **Hotfix:** Coordinates an expedited release process, ensures rollback plan is documented, and communicates the compressed timeline to Stakeholders and the Project Manager.

See the full checklist: [Release Coordinator Checklist](./release-coordinator-checklist.md)

---

## Cross-Role Collaboration & Handoffs

| From | To | When | For What |
|---|---|---|---|
| Onboarding Coordinator | Team Lead | End of new member's first week | Hand off integrated member with environment access confirmed |
| Project Manager | Change Manager | When a change affects scope, timeline, or cost | Submit a formal change request |
| Change Manager | Release Coordinator | After a change request is approved | Schedule the change for deployment |
| Project Manager | Project Sponsor | When decisions exceed PM authority | Escalate for funding, major scope, or cross-team conflicts |
| SME | Change Manager | When a design constraint requires a scope change | Feed findings into the change request |
| Release Coordinator | Change Manager | After deployment completes | Close related change requests |

---

## How these personas are used in the exercise
- Use these persona definitions to frame scenarios and sample interactions in the Skills Exercise.
- Each persona can be used as a persona prompt for Copilot Spaces to shape role-specific guidance.

