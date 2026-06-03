# prd.md - HyIntel AI Product Requirements Document

## 1. Product overview

Working title: HyIntel AI

Product type: B2B SaaS web application presented as a hackathon MVP.

Tagline:

```text
AI-powered recruitment intelligence for faster, explainable, compliant hiring decisions.
```

HyIntel AI is a compliance-first recruitment intelligence platform for Talent Acquisition teams and hiring managers. The MVP helps users analyze a role, understand the market, map companies hiring for that role, identify candidate pools, view competitor demand, manage candidates in a talent pool, and generate a market overview report.

The hackathon version should prioritize a polished, believable, clickable dashboard over a production backend.

## 2. Primary users

| User | Primary need |
| --- | --- |
| Talent Acquisition Partner | Build a target list faster, search smarter, and explain candidate fit clearly. |
| Recruitment Lead | Understand competitor demand, talent availability, salary range, and search difficulty before opening the funnel wider. |
| Hiring Manager | Receive concise, evidence-based candidate and market summaries instead of raw profiles. |

## 3. Problem statement

Recruiters often stitch together market research, sourcing, candidate evaluation, and hiring-manager updates manually. This slows down hiring, creates inconsistent candidate judgments, and makes it difficult to explain why a candidate or sourcing market is recommended.

Key problems:

- Market intelligence is fragmented across job boards, company pages, salary benchmarks, recruiter notes, and competitor hiring activity.
- Recruiters repeatedly rewrite search strings, role summaries, and shortlist notes.
- Candidate evaluation can become subjective when evidence is scattered.
- Competitive hiring context is often missing when recruiters discuss shortlists with hiring managers.

## 4. Product objectives

| Objective | MVP behavior |
| --- | --- |
| Speed up sourcing setup | Parse a JD and recommend skills, keywords, titles, and Boolean strings. |
| Add market context | Summarize approved mock market data into a market map and competitor hiring view. |
| Improve candidate consistency | Rank candidates with a transparent scoring model and evidence notes. |
| Support hiring-manager decisions | Generate a one-page market overview and suitability-style report summary. |
| Maintain compliance-first trust | Use approved sample data only, show evidence trails, require human review. |

## 5. Demo scope

### Markets

- Malaysia
- Singapore

### Industry focus

- FinTech
- Professional services
- Shared services
- E-commerce
- BPO / Contact centre
- Banking and financial services

### Pilot roles

1. DevOps Engineer
2. Finance Manager
3. Customer Service Representative

Default selected role:

```text
DevOps Engineer - Malaysia - FinTech - Mandarin preferred - Permanent
```

The MVP must show that analysis has already been run for all three roles.

## 6. Product principles

1. Beautiful before complex.
2. Demo-ready before production-ready.
3. Explainable before opaque.
4. Approved sample data before live data.
5. Human review before any hiring decision.
6. Evidence before inference.
7. Role switching must prove breadth across three markets.

## 7. Recommended technical approach

Use:

- React + Vite or Next.js
- Tailwind CSS
- shadcn/ui-style components
- Recharts
- Local mock data / JSON seed data
- No external API dependency
- No real scraping
- No authentication needed for MVP

Recommended for this repo:

```text
React + Vite + TypeScript + Tailwind + Recharts + local data files
```

## 8. Information architecture

Persistent sidebar navigation:

1. Dashboard
2. Smart Search
3. Market Mapping
4. Competitor Intel
5. Candidate Discovery
6. Talent Pool
7. Overview Report

Important: Do not include a separate Salary Intelligence tab. Salary intelligence must live inside Market Mapping.

## 9. Global layout requirements

The app must have:

- Persistent left sidebar
- HyIntel AI logo
- Active page highlighted in green
- Talent Pool sidebar card showing "43 candidates in your referral pool"
- Bottom user profile: Jeremy Yap, TA Lead
- Top page header with title, description, role selector, country selector, industry selector, and action button
- Trust/compliance indicators

Use this UI style:

- White and very light gray background
- Green primary accent
- Soft cards with rounded corners
- Tables, charts, badges, dropdowns, progress bars, and report previews
- Professional enterprise dashboard look

## 10. Role selector requirements

The app must support role switching between:

- DevOps Engineer
- Finance Manager
- Customer Service Representative

Changing role must update:

- Dashboard metrics
- Market Mapping data
- Competitor Intel data
- Candidate Discovery data
- Talent Pool data
- Overview Report data

## 11. Screen requirements

### Screen 1 - Dashboard

Purpose: Show an overview of all completed role analyses.

Default DevOps Engineer top metrics:

| Metric | Value |
| --- | ---: |
| Active job requests | 12 |
| Available candidates | 348 |
| Candidate match rate | 74% |
| Avg time-to-shortlist | 18h |
| Companies mapped | 183 |
| Reports generated | 8 |

Required sections:

- Completed analysis overview with three role cards
- Smart Search Assistant card
- Recent searches table
- Top matches this week

Completed analysis overview cards:

| Role | Market | Industry | Companies mapped | Available candidates | Competitor roles open | Status |
| --- | --- | --- | ---: | ---: | ---: | --- |
| DevOps Engineer | Malaysia / Singapore | FinTech | 183 | 348 | 286 | Analysis complete |
| Finance Manager | Malaysia / Singapore | Finance, shared services, professional services | 146 | 612 | 194 | Analysis complete |
| Customer Service Representative | Malaysia / Singapore | BPO, e-commerce, banking, FinTech, contact centre | 312 | 15,800 | 1,840 | Analysis complete |

Top matches this week:

- Chen Wei Ming - DevOps Engineer - 92% - Kubernetes, AWS, CI/CD - Moderate salary risk
- Priya Nair - Finance Manager - 89% - SAP, reconciliation, reporting - Notice period risk
- Nurul Aina - Customer Service Representative - 91% - Mandarin, CRM, complaint handling - High competing demand

### Screen 2 - Smart Search / Hiring Manager Intake

Purpose: Simulate the intake workflow.

Required sections:

- Upload or select JD
- Prefilled JD text area based on selected role
- Role dropdown
- Parse JD button
- Parsed role output cards

Parsed role output must include:

- Core role
- Seniority
- Must-have skills
- Nice-to-have skills
- Business context
- Hiring challenge
- Suggested search titles
- Recommended Boolean strings

### Screen 3 - Market Mapping

Purpose: Help recruiters understand where the selected role exists in the approved dataset and which companies are best to source from.

This is the hero page of the MVP.

It must answer:

1. All companies in the approved dataset that have the selected role.
2. How many employees are in that role or similar role in each company.
3. How many open roles each company currently has for that role in the approved demo dataset.
4. What salary each company is offering for that role.
5. The years-of-experience range of employees in that role within each company.
6. How competitive each company is as a sourcing or hiring competitor.
7. Which companies are best to target for sourcing.

Top metric cards:

| Metric | DevOps Engineer | Finance Manager | Customer Service Representative |
| --- | --- | --- | --- |
| Companies mapped | 183 | 146 | 312 |
| Employees in similar roles | 2,184 | 3,420 | 18,600 |
| Open roles found | 286 | 194 | 1,840 |
| Median salary offered | RM 14.5k | RM 12.8k | RM 4.2k |
| Experience range | 4-9 years | 5-12 years | 0-5 years |
| Hiring difficulty | High | Moderate | Moderate / High volume |

Hero table title:

```text
All companies with this role
```

Required table columns:

- Company
- Industry
- Country
- Matching role titles
- Estimated employees in role
- Open roles
- Years of experience range
- Salary offered
- Work setup
- Hiring intensity
- Sourcing recommendation

Required filters:

- Country
- Industry
- Salary range
- Years of experience
- Hiring intensity
- Work setup
- Company size

Required search placeholder:

```text
Search company, title, or skill
```

Required sorting:

- Sort by employees in role
- Sort by open roles
- Sort by salary offered
- Sort by years of experience
- Sort by hiring intensity

Salary Intelligence requirement:

- Salary benchmarks, salary ranges, and salary charts must be inside Market Mapping.
- Do not create a separate Salary Intelligence navigation item.

### Screen 4 - Competitor Intel

Purpose: Show competitor demand and hiring activity for the selected role.

Required elements:

- Competitor overview cards
- Total open roles
- Hiring intensity indicators
- Role-by-role headcount breakdowns
- Common skill demand
- Adjacent-industry guidance
- Flat intelligence table listing competitor role title and headcount/openings

### Screen 5 - Candidate Discovery

Purpose: Answer who to approach first.

Required elements:

- Ranked candidate list
- Fit score
- Key match
- Main risk
- Current salary
- Expected salary
- Score breakdown across six evidence-based factors
- Expandable evidence panel
- Sort by Fit Score and Experience

When a recruiter clicks a candidate row, show a candidate suitability one-pager within the same workflow or as a drawer/modal.

Candidate suitability one-pager must include:

- Weighted scoring transparency
- Strengths and gaps
- Interview question recommendations
- Relocation or compensation risk visibility
- Language assessment indicators
- Salary insights
- Recruiter-ready recommendation summary

### Screen 6 - Talent Pool

Purpose: Manage candidates in the referral/talent pool.

Required elements:

- 43 candidates in referral pool summary
- Candidate table or cards
- Status dropdowns
- Owner
- Source
- Last updated
- Next action
- Notes
- Risk indicator

### Screen 7 - Overview Report

Purpose: Generate a one-page overview of the selected role in market context.

Required elements:

- Generate Overview Report button
- Market summary
- Companies mapped
- Employees in similar roles
- Open roles found
- Salary benchmark
- Experience range
- Competitor demand
- Candidate availability
- Sourcing recommendations
- Key risks
- Suggested next actions
- Compliance note

## 12. Data requirements

Use realistic mock data for:

- Job descriptions
- Market role data
- Companies hiring each role
- Estimated employees in role by company
- Open roles per company
- Salary offered by company
- Years of experience range
- Competitor companies
- Candidate profiles
- Salary benchmarks
- Talent pool status
- Overview report data

## 13. Compliance and trust requirements

Display this note in the UI:

```text
Compliance-first MVP
This demo uses approved uploaded/sample data only. Candidate recommendations are evidence-based and require human review. The system does not make automated hiring decisions.
```

Additional trust labels:

- Approved sample data
- Evidence-based
- Human review required
- Demo intelligence only

When showing "all companies," use supporting copy:

```text
All companies found in the approved demo dataset for the selected role.
```

## 14. Candidate scoring model

| Scoring factor | Weight |
| --- | ---: |
| Must-have skill match | 35% |
| Relevant experience | 25% |
| Industry/domain match | 15% |
| Seniority match | 10% |
| Location/language fit | 10% |
| Compensation/availability signal | 5% |

Trust rule:

```text
If evidence is missing, mark it as Not evidenced. Do not infer unsupported claims.
```

## 15. Functional requirements

| Requirement | Priority |
| --- | --- |
| Local app starts with one command | P0 |
| Persistent sidebar navigation | P0 |
| Role selector updates all main pages | P0 |
| Dashboard shows completed analyses for three roles | P0 |
| Smart Search parses mock JD output | P0 |
| Market Mapping table is searchable and sortable | P0 |
| Salary intelligence appears inside Market Mapping | P0 |
| Competitor Intel shows demand and intensity | P0 |
| Candidate Discovery shows ranked candidates and evidence | P0 |
| Candidate score breakdown uses six weighted factors | P0 |
| Talent Pool status dropdown works locally | P0 |
| Overview Report renders for each role | P0 |
| Trust/compliance notes are visible | P0 |
| No external API calls or scraping | P0 |

## 16. Non-goals

- No live scraping.
- No real LinkedIn, JobStreet, Indeed, or external recruitment platform integration.
- No automated hiring decisions.
- No opaque AI ranking without evidence trails.
- No full ATS, CRM, or email-sequencing workflow in phase one.
- No production authentication.
- No production backend.

## 17. Success criteria

The demo is successful when a recruiter or hiring manager believes HyIntel AI can:

- Reduce time spent preparing a sourcing search.
- Explain where to source candidates.
- Show competitor demand and salary pressure.
- Rank candidates transparently.
- Preserve compliance by using evidence and human review.
- Produce a recruiter-ready market overview report.

## 18. Risks and mitigations

| Risk | Mitigation |
| --- | --- |
| Demo looks too static | Add role switching, filters, sorting, status dropdowns, charts, and generated report states. |
| Users think data is live scraped | Add clear sample-data and demo-intelligence labels. |
| Candidate ranking feels opaque | Show six-factor score breakdown and evidence notes. |
| Scope expands too far | Keep no backend, no auth, and no external integrations for MVP. |
| Salary Intelligence becomes a separate page | Keep salary benchmarks inside Market Mapping only. |

## 19. Open questions for post-demo

- Which data sources will be approved for a controlled pilot?
- Which ATS or HRIS integration should be prioritized first?
- What audit log requirements are needed for enterprise customers?
- What fairness, bias, and explainability review will be required before production candidate ranking?
- What export formats are needed for hiring-manager reports?
