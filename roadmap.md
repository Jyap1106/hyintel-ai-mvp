# roadmap.md - HyIntel AI Roadmap

HyIntel AI should evolve from a polished hackathon MVP into a controlled, compliance-first recruitment intelligence platform. The MVP must remain simple, auditable, explainable, and easy to demo.

## Roadmap principles

1. Compliance before connectivity.
2. Approved data before live discovery.
3. Explainable scoring before advanced AI.
4. Recruiter workflow before automation.
5. Human review before hiring decisions.
6. Demo polish before production architecture.

## Repository strategy

### Now: single demo repository

Recommended repository:

```text
hyintel-ai
```

Purpose:

- Frontend MVP
- Local mock data
- Documentation
- Demo-ready dashboard

### Later: split only when needed

Potential future repositories:

| Future repository | Purpose | Create when |
| --- | --- | --- |
| hyintel-ai-api | Backend APIs, scoring services, report generation | A controlled pilot needs server-side persistence |
| hyintel-ai-data-import | Approved data import and normalization layer | Multiple data providers or ATS imports are approved |
| hyintel-ai-docs | Product, compliance, and customer-facing docs | External collaborators need separated docs |
| hyintel-ai-design-system | Shared components and design tokens | Multiple HyIntel apps need the same UI system |

For the hackathon, do not split repositories unless it helps the team move faster.

## Phase 0 - Repo and documentation foundation

Target: Before coding starts.

Deliverables:

- GitHub repo created.
- Readme.md added.
- Agents.md added.
- Tasks.md added.
- dataset.md added.
- prd.md added.
- roadmap.md added.
- React + Vite scaffold created.
- Basic Tailwind configuration added.

Exit criteria:

- New contributor can understand what to build in less than 10 minutes.
- App starts locally with one command.
- Compliance boundaries are documented.

## Phase 1 - Hackathon MVP demo

Target: Demo-ready local web app.

Focus:

- Polished UI
- Local mock data
- Clickable navigation
- Role switching
- Market Mapping hero table
- Candidate scoring transparency
- Overview report preview

Deliverables:

- Dashboard
- Smart Search
- Market Mapping with salary intelligence
- Competitor Intel
- Candidate Discovery
- Talent Pool
- Overview Report
- Local data for DevOps Engineer, Finance Manager, and Customer Service Representative
- Trust indicators and compliance notes

Exit criteria:

- Full demo can run without internet.
- No external APIs or scraping.
- Role switching updates all major pages.
- Candidate scoring shows six factor breakdowns.
- Missing evidence shows Not evidenced.
- Market Mapping includes salary intelligence and no separate Salary Intelligence tab exists.

## Phase 2 - Pilot-ready local prototype

Target: Make the MVP credible for internal review or a small pilot discussion.

Focus:

- More robust data import simulation
- Configurable role profiles
- Better report generation
- Improved search/filtering
- Better auditability

Potential deliverables:

- CSV upload for approved demo files
- Import validation screen
- Data source labels per row
- Deterministic scoring test cases
- Better candidate detail drawer
- Print-friendly overview report
- Saved local report snapshots
- Basic browser storage for demo state
- More sample roles and industries

Exit criteria:

- Recruiter can load approved sample files locally.
- App explains what data powered each insight.
- Scoring output can be reproduced from the same input.

## Phase 3 - Controlled pilot architecture

Target: Prepare for limited internal or customer pilot using approved data sources.

Focus:

- Backend foundation
- Data import governance
- Persistence
- Audit logging
- Security review

Potential deliverables:

- API layer using FastAPI, Node, or equivalent
- Database for roles, companies, candidates, reports, and audit events
- User roles for recruiter, recruitment lead, and hiring manager
- Internal ATS import proof of concept
- Approved API connector proof of concept
- Source-level audit trails
- Report export service
- Organization-level configuration

Exit criteria:

- Pilot data sources are approved and documented.
- Every candidate recommendation has an audit trail.
- Human review is required before any shortlist action.
- Security and privacy review is complete.

## Phase 4 - Production recruitment intelligence platform

Target: Production-grade SaaS foundation.

Focus:

- Secure multi-user workflows
- Licensed data integrations
- ATS/CRM interoperability
- Explainability and compliance review
- Operational reliability

Potential deliverables:

- Authentication and RBAC
- Organization workspaces
- ATS integrations
- Licensed recruitment data provider integration
- Permission-based crawling where legally approved
- Report templates and exports
- Advanced salary benchmarking
- Candidate consent and data retention controls
- Bias and fairness monitoring
- Admin audit logs
- Usage analytics
- Error monitoring and observability

Exit criteria:

- Data processing agreements and source permissions are in place.
- Customer admins can manage users and data retention.
- Compliance team can review evidence and decision trails.

## Phase 5 - Enterprise intelligence layer

Target: Enterprise-ready recruitment intelligence and workforce planning.

Focus:

- Predictive hiring signals
- Skills adjacency
- Workforce planning insights
- Multi-country compensation intelligence
- Executive reporting

Potential deliverables:

- Skills adjacency graph
- Talent movement heatmaps
- Competitive hiring alerts
- Market demand forecasting
- Role difficulty prediction
- Workforce planning dashboards
- Executive report packs
- Scenario planning by country, industry, and salary band

Exit criteria:

- Insights support strategic TA planning beyond a single requisition.
- Customers can configure markets, roles, and compliance controls.

## Release plan

| Release | Name | Goal | Must include |
| --- | --- | --- | --- |
| v0.0 | Docs and scaffold | Repo is ready for contributors | Docs, app scaffold, local start command |
| v0.1 | Clickable MVP | Demo-ready dashboard | Seven screens, role switching, mock data |
| v0.2 | Polished demo | Strong hackathon presentation | Charts, filters, status changes, report preview |
| v0.3 | Pilot prototype | Approved data import simulation | CSV import, validation, audit labels |
| v1.0 | Controlled pilot | Real internal pilot with approved data | Backend, persistence, auth, audit logs |
| v1.1 | Production beta | Customer-ready SaaS beta | Integrations, RBAC, compliance review, export workflows |

## Future integrations

These are future-state only and must not be implemented in the hackathon MVP unless approved access exists:

- Internal ATS integrations
- HRIS integrations
- Approved recruitment APIs
- Licensed labor market intelligence feeds
- Permission-based crawling
- LinkedIn, JobStreet, Indeed, and other recruitment platform integrations

## Future compliance roadmap

| Area | Future control |
| --- | --- |
| Data provenance | Source labels, import history, row-level evidence |
| Explainability | Score breakdown, evidence notes, model versioning |
| Human oversight | Recruiter approval before shortlist or outreach |
| Privacy | Data minimization, retention controls, deletion workflows |
| Fairness | Bias checks, adverse impact monitoring, review workflows |
| Security | Authentication, RBAC, audit logs, encryption, monitoring |

## Not now

Do not add these during the MVP:

- Live scraping
- Real external recruitment platform integrations
- Automated hiring decisions
- Full ATS workflow
- Email sequencing
- Production authentication
- Complex backend architecture
- Vector database
- Paid AI dependency
- Separate Salary Intelligence tab

## Success metrics by phase

| Phase | Success metric |
| --- | --- |
| Hackathon MVP | Judges understand the end-to-end recruiter workflow in under 5 minutes. |
| Pilot prototype | Recruiters can reproduce insights from approved sample uploads. |
| Controlled pilot | Hiring teams can compare market and candidate evidence with audit trails. |
| Production beta | Customers can safely use approved data integrations with human-reviewed recommendations. |
| Enterprise | Recruitment leaders can plan talent strategy across roles, countries, and competitors. |

## Demo narrative for roadmap slide

HyIntel AI starts as a local, compliance-first MVP using approved sample data. The first demo proves the recruiter workflow: parse the role, map the market, compare competitors, rank candidates with explainable evidence, manage the talent pool, and generate a market overview report. After the hackathon, the roadmap adds approved imports, audit logs, persistence, and only then licensed or permission-based data integrations.
