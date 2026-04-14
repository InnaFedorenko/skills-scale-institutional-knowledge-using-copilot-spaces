# OctoAcme Personas

This document defines typical roles and responsibilities used in OctoAcme project docs and exercises.

---

## Developers

### Role Summary
Developers design, build, test, and deliver software components. They collaborate with product and project leads to implement features that meet acceptance criteria and quality standards.

### Responsibilities
- Implement features and fixes to meet acceptance criteria
- Write and maintain tests and documentation
- Participate in design and code reviews
- Assist in estimating and planning work
- Help identify technical risks and propose mitigations

### Goals
- Deliver reliable, maintainable code
- Reduce cycle time from idea to production
- Maintain high test coverage and observability

### Typical Communication
- Daily standups and sprint planning
- PR descriptions and code review comments
- Technical design docs when needed

---

## Product Managers

### Role Summary
Product Managers define what should be built to deliver customer and business value. They own the product vision, prioritize the backlog, and measure outcomes.

### Responsibilities
- Define problem statements and success metrics
- Prioritize the roadmap and backlog
- Collaborate with stakeholders and engineering on trade-offs
- Validate solutions through user research and metrics

### Goals
- Maximize customer value and impact
- Make clear, data-driven prioritization decisions
- Ensure product-market fit and usability

### Typical Communication
- Weekly alignment with PM and engineering leads
- Roadmap updates and stakeholder briefings
- Acceptance criteria and feature specs

---

## Project Managers

### Role Summary
Project Managers coordinate delivery activities, manage schedules, risks, and communications. They enable the team to deliver on commitments efficiently.

### Responsibilities
- Create and maintain project plans and timelines
- Manage risks, dependencies, and resource constraints
- Facilitate meetings (kickoff, planning, retrospectives)
- Ensure consistent project documentation and status reporting
- Coordinate cross-team and stakeholder communication

### Goals
- Deliver projects on time and within scope
- Minimize unplanned work and escalations
- Maintain transparency and alignment across stakeholders

### Typical Communication
- Weekly status updates and stakeholder reports
- Risk registers and decision logs
- Coordination via project boards and meeting facilitation

---

## Team Leads

### Role Summary
Team Leads guide a small delivery team, serving as a bridge between the Project Manager and individual Contributors on day-to-day execution.

### Responsibilities
- Break down work items into tasks and assign them to Contributors
- Monitor team progress and remove blockers
- Conduct code and design reviews
- Escalate risks or blockers to the Project Manager
- Mentor Contributors on technical and process standards

### Goals
- Keep the team productive and unblocked
- Maintain code quality and adherence to standards
- Provide accurate status reporting to the Project Manager

### Typical Communication
- Daily standups with Contributors
- Weekly syncs with the Project Manager
- PR and design review threads

---

## Contributors

### Role Summary
Contributors are the individual team members—engineers, designers, QA testers—who complete the hands-on work that delivers project outcomes.

### Responsibilities
- Complete assigned tasks to the Definition of Done
- Raise blockers early to the Team Lead
- Participate in planning and retrospective ceremonies
- Document work in pull requests and issue comments

### Goals
- Deliver high-quality work on schedule
- Collaborate openly and seek help when blocked
- Continuously improve skills and process knowledge

### Typical Communication
- Daily standups and team channels
- PR descriptions and code review comments
- Issue updates and status comments

---

## Stakeholders

### Role Summary
Stakeholders are individuals or groups with a vested interest in project outcomes—customers, business units, or partner teams—who provide requirements and accept deliverables.

### Responsibilities
- Provide clear requirements and success criteria
- Review and approve deliverables at defined checkpoints
- Escalate business-level concerns to the Project Sponsor
- Participate in demos and UAT sessions

### Goals
- Ensure the delivered solution meets business needs
- Stay informed on project progress and risk
- Provide timely feedback to avoid rework

### Typical Communication
- Monthly stakeholder updates from the Project Manager
- Demo and review sessions at milestone boundaries
- Ad-hoc escalation to Project Sponsor when needed

---

## Onboarding Coordinator

### Role Summary
The Onboarding Coordinator ensures that new project team members are set up for success from day one by managing access, introductions, and knowledge transfer.

### Key Responsibilities
- Create and maintain the team onboarding checklist (see [onboarding-checklist.md](onboarding-checklist.md))
- Provision or coordinate access to repositories, tools, and communication channels
- Schedule orientation meetings with the Project Manager, Team Lead, and relevant Subject Matter Experts
- Track onboarding completion and flag gaps to the Project Manager
- Gather feedback from new members to improve the onboarding process

### Typical Interactions / Handoffs
- **Project Manager**: receives the list of new team members and their planned start dates; reports onboarding completion status
- **Team Lead**: coordinates tool access and first-week task assignments
- **Contributor (new member)**: the primary person being onboarded; guides them through each checklist step
- **Subject Matter Expert (SME)**: schedules domain knowledge sessions for new members who need specialist context

### Acceptance / Decision Authority
- Can approve and provision standard tool access independently
- Escalates non-standard access requests or unresolved blockers to the Project Manager

### Example Scenarios
1. **New developer joins mid-sprint**: The Onboarding Coordinator follows the [onboarding checklist](onboarding-checklist.md), grants repository access, schedules a 30-minute orientation with the Team Lead, and marks the developer ready to pick up tasks by the end of day 2.
2. **New stakeholder representative**: The Onboarding Coordinator schedules an introductory call with the Project Manager, shares the project overview doc, and confirms they have access to the status dashboard before the next stakeholder update.

---

## Change Manager

### Role Summary
The Change Manager governs the change control process, ensuring that all proposed changes to scope, architecture, or process are documented, assessed, approved, and communicated.

### Key Responsibilities
- Maintain the change request log and facilitate the change control board (CCB)
- Ensure each change request follows the [change control process](change-control-process.md)
- Coordinate impact assessment with the Team Lead and relevant SMEs
- Communicate approved or rejected changes to all affected parties
- Track post-change outcomes and document lessons learned

### Typical Interactions / Handoffs
- **Project Manager**: aligns on scope impact and schedule adjustments resulting from approved changes; receives escalations for changes that affect project baselines
- **Team Lead**: requests technical impact assessment for proposed changes
- **Stakeholder**: receives communication on approved changes; may submit change requests
- **Project Sponsor**: escalates changes with significant budget, schedule, or strategic impact for sponsor approval

### Acceptance / Decision Authority
- Can approve minor changes (low risk, no baseline impact) independently
- Escalates medium/high-risk changes to the Project Manager or Project Sponsor as defined in the [change control process](change-control-process.md)

### Example Scenarios
1. **Scope addition request from a stakeholder**: The Change Manager logs the request, asks the Team Lead for a t-shirt size estimate, presents the impact to the Project Manager, and communicates the approved (or deferred) decision back to the stakeholder within two business days.
2. **Critical bug discovered post-release**: The Change Manager fast-tracks an emergency change request, coordinates a rollback assessment with the Team Lead and Release Coordinator, and obtains verbal Project Sponsor approval before the fix is deployed.

---

## Project Sponsor

### Role Summary
The Project Sponsor is an executive or senior leader who champions the project, provides strategic direction, removes organizational blockers, and approves major decisions on scope, budget, and resources.

### Key Responsibilities
- Approve the project charter and any changes to budget or strategic scope
- Remove cross-organizational blockers that the Project Manager cannot resolve
- Attend milestone review checkpoints and provide executive sign-off
- Advocate for the project within the broader organization
- Review and act on escalations from the Project Manager

### Typical Interactions / Handoffs
- **Project Manager**: primary point of contact; receives regular status summaries and escalation requests; the PM prepares briefing materials before sponsor checkpoints
- **Stakeholder**: sponsors may directly engage key stakeholders on priority decisions
- **Change Manager**: reviews and approves high-impact change requests

### Acceptance / Decision Authority
- Has final authority on changes to project scope, budget, or strategic direction
- Approves go/no-go for major releases when requested by the Project Manager

### Example Scenarios
1. **Budget overrun risk**: The Project Manager escalates a forecast overrun to the Project Sponsor two weeks in advance. The Sponsor approves a budget contingency and communicates the decision to affected stakeholders.
2. **Organizational dependency blocked**: A third-party team is unresponsive to the Project Manager's requests. The Sponsor engages their executive counterpart to unblock the dependency within 48 hours.

For detailed guidance see [project-sponsor-guidance.md](project-sponsor-guidance.md).

---

## Subject Matter Expert (SME)

### Role Summary
Subject Matter Experts provide authoritative domain knowledge—technical, regulatory, or business—that informs project decisions, risk assessments, and solution design.

### Key Responsibilities
- Provide domain-specific guidance during planning and design activities
- Review and sign off on deliverables that require specialist validation
- Support the Change Manager with impact assessments for changes in their domain
- Participate in onboarding sessions for new team members who need domain context
- Flag domain-specific risks to the Project Manager or Team Lead

### Typical Interactions / Handoffs
- **Project Manager**: engaged at initiation and planning to scope domain complexity; consulted for risk assessments
- **Team Lead**: works closely during design and implementation phases; reviews technical decisions
- **Onboarding Coordinator**: provides domain knowledge sessions for new members
- **Change Manager**: consulted on technical or domain impact of proposed changes

### Acceptance / Decision Authority
- Final authority on domain-specific technical correctness within their area
- Escalates cross-domain conflicts or resource constraints to the Project Manager

### Example Scenarios
1. **Security review**: A security SME reviews the solution architecture before the release gate, identifies a potential vulnerability, and works with the Team Lead to resolve it before the go/no-go decision.
2. **Regulatory requirement clarification**: A compliance SME is engaged during planning to clarify data retention requirements, which are incorporated into the acceptance criteria before sprint work begins.

---

## Release Coordinator

### Role Summary
The Release Coordinator manages the logistics, communication, and verification steps for each release and deployment, ensuring smooth handoffs from development to production.

### Key Responsibilities
- Maintain the [release coordinator checklist](release-coordinator-checklist.md) for each release
- Coordinate go/no-go reviews with the Project Manager, Team Lead, and QA
- Communicate release schedules, change windows, and post-release status to Stakeholders
- Manage rollback decisions in coordination with the Team Lead and Project Sponsor
- Document release outcomes and feed lessons learned back to the Project Manager

### Typical Interactions / Handoffs
- **Project Manager**: receives release plan and go/no-go sign-off authority delegation; reports release outcomes
- **Team Lead**: receives build artifacts and deployment scripts; coordinates deployment steps
- **Change Manager**: confirms all change requests associated with the release are approved and documented
- **Stakeholder**: communicates release schedule and any user-facing impacts

### Acceptance / Decision Authority
- Can approve low-risk, pre-planned releases within an agreed change window
- Escalates go/no-go decisions for high-risk or emergency releases to the Project Manager and Project Sponsor

### Example Scenarios
1. **Scheduled minor release**: The Release Coordinator confirms all checklist items are complete, sends a release notification to Stakeholders, coordinates deployment with the Team Lead, and posts a success confirmation within one hour of deployment.
2. **Emergency hotfix**: A critical defect is found in production. The Release Coordinator initiates the emergency change request with the Change Manager, confirms rollback readiness with the Team Lead, and obtains Project Sponsor verbal approval before deploying the fix.

For detailed checklist see [release-coordinator-checklist.md](release-coordinator-checklist.md).

---

## How these personas are used in the exercise
- Use these persona definitions to frame scenarios and sample interactions in the Skills Exercise.
- Each persona can be used as a persona prompt for Copilot Spaces to shape role-specific guidance.
- Related process documents: [onboarding-checklist.md](onboarding-checklist.md) | [change-control-process.md](change-control-process.md) | [project-sponsor-guidance.md](project-sponsor-guidance.md) | [release-coordinator-checklist.md](release-coordinator-checklist.md)

