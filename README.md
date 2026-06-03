# HyIntel AI

AI-powered recruitment intelligence for faster, explainable, compliant hiring decisions.

HyIntel AI is a polished hackathon MVP demo web application for Talent Acquisition teams, recruitment leads, and hiring managers. It helps users analyze a role, understand the market, map companies hiring for that role, identify candidate pools, view competitor demand, manage candidates in a talent pool, and generate a market overview report.

This repository is designed as a beautiful, believable, clickable MVP. It uses approved mock/sample data only. It does not scrape, call LinkedIn, JobStreet, Indeed, or any external recruitment platform.

## MVP status

| Area | Decision |
| --- | --- |
| Product type | B2B SaaS dashboard MVP |
| Demo style | Clickable, polished, local-first hackathon demo |
| Primary users | Talent Acquisition teams, recruitment leads, hiring managers |
| Demo markets | Malaysia and Singapore |
| Default selected role | DevOps Engineer - Malaysia - FinTech - Mandarin preferred - Permanent |
| Data | Local mock JSON/CSV seed data only |
| External APIs | None for MVP |
| Authentication | Not required for MVP |
| Compliance stance | Approved sample data, evidence-based recommendations, human review required |

## Recommended stack

Use one of these frontend stacks. For the main MVP demo, React + Vite is recommended because it is fast to scaffold, easy to run locally, and suitable for a hackathon dashboard.

- React + Vite
- TypeScript
- Tailwind CSS
- shadcn/ui-style components
- Recharts
- Local mock data in JSON or TypeScript seed files
- No production backend
- No live scraping
- No authentication for MVP

## Quick start

```bash
# 1. Create the app
npm create vite@latest hyintel-ai -- --template react-ts
cd hyintel-ai

# 2. Install dependencies
npm install
npm install lucide-react recharts clsx tailwind-merge class-variance-authority
npm install -D tailwindcss postcss autoprefixer
npx tailwindcss init -p

# 3. Add these markdown files to the repository root
# Readme.md, Agents.md, Tasks.md, dataset.md, prd.md, roadmap.md

# 4. Run locally
npm run dev
```

Optional shadcn/ui setup:

```bash
npx shadcn@latest init
npx shadcn@latest add button card badge input textarea select table tabs dropdown-menu progress sheet
```

## Suggested repository structure

```text
hyintel-ai/
  Readme.md
  Agents.md
  Tasks.md
  dataset.md
  prd.md
  roadmap.md
  package.json
  vite.config.ts
  tailwind.config.js
  index.html
  src/
    App.tsx
    main.tsx
    data/
      roles.ts
      marketCompanies.ts
      competitors.ts
      candidates.ts
      talentPool.ts
      reports.ts
      scoringModel.ts
    components/
      layout/
        Sidebar.tsx
        TopFilters.tsx
        PageHeader.tsx
      shared/
        MetricCard.tsx
        StatusBadge.tsx
        TrustBadge.tsx
        RoleSelector.tsx
        DataTable.tsx
        ScoreBreakdown.tsx
      charts/
        DemandChart.tsx
        SalaryBenchmarkChart.tsx
        CompetitorIntensityChart.tsx
    pages/
      Dashboard.tsx
      SmartSearch.tsx
      MarketMapping.tsx
      CompetitorIntel.tsx
      CandidateDiscovery.tsx
      TalentPool.tsx
      OverviewReport.tsx
    lib/
      scoring.ts
      filters.ts
      formatters.ts
      constants.ts
    styles/
      globals.css
```

## Product promise

HyIntel AI turns a role request into an explainable recruitment intelligence workflow:

1. Parse the job description.
2. Identify must-have skills, nice-to-have skills, alternative titles, and Boolean strings.
3. Map companies with the selected role in the approved dataset.
4. Show employees in similar roles, open roles, salary ranges, and years of experience.
5. Compare competitor demand and hiring intensity.
6. Rank candidates using a transparent weighted model.
7. Manage candidates in a talent pool.
8. Generate a market overview report.

## Pilot roles

The MVP must clearly show that analysis has already been completed for all three roles and that role switching updates the dashboard, market mapping, competitor intel, candidate discovery, talent pool, and overview report.

| Pilot role | Markets | Industry focus | Key demo pattern |
| --- | --- | --- | --- |
| DevOps Engineer | Malaysia / Singapore | FinTech, banking, e-commerce, payments | High-skill technical search with salary competition |
| Finance Manager | Malaysia / Singapore | Finance, shared services, professional services | Mid-senior finance market with domain and ERP skill matching |
| Customer Service Representative | Malaysia / Singapore | BPO, e-commerce, banking, FinTech, contact centre | High-volume candidate market with language and SLA signals |

## Default role metrics

Default selected role: DevOps Engineer - Malaysia - FinTech - Mandarin preferred - Permanent.

| Metric | Value |
| --- | ---: |
| Active job requests | 12 |
| Available candidates | 348 |
| Candidate match rate | 74% |
| Avg time-to-shortlist | 18h |
| Companies mapped | 183 |
| Reports generated | 8 |

## Main screens

### 1. Dashboard

Shows completed analysis overview for the three pilot roles, top metrics for the selected role, recent searches, a Smart Search Assistant card, and top matches this week.

### 2. Smart Search

Simulates the hiring manager intake workflow. Users can select a pilot role, view a prefilled JD, click Parse JD, and see parsed output: core role, seniority, must-have skills, nice-to-have skills, business context, hiring challenge, suggested search titles, and Boolean strings.

### 3. Market Mapping

Hero section of the product. Shows all companies in the approved demo dataset for the selected role. Includes salary intelligence here. There must not be a separate Salary Intelligence tab.

Market Mapping must include:

- Companies mapped
- Employees in similar roles
- Open roles found
- Median salary offered
- Experience range
- Hiring difficulty
- Searchable and sortable company table
- Filters for country, industry, salary, experience, hiring intensity, work setup, and company size
- Salary benchmark chart and company salary ranges

### 4. Competitor Intel

Shows competitor hiring demand, open role counts, common skill demand, hiring intensity, adjacent industry guidance, and role-by-role headcount breakdowns.

### 5. Candidate Discovery

Shows ranked candidate comparison with fit score, current salary, expected salary, key match, main risk, score breakdown, and evidence panels. Missing evidence must display as Not evidenced.

### 6. Talent Pool

Shows candidates in the referral pool, status updates, source, owner, next action, notes, risk indicators, and shortlist stage.

Sidebar status card:

```text
Talent Pool
43 candidates in your referral pool
```

User profile at bottom:

```text
Jeremy Yap
TA Lead
```

### 7. Overview Report

Generates a one-page market overview report for the selected role. The report should include market size, salary benchmark, competitor demand, best sourcing targets, candidate availability, risks, and recommended next steps.

## Sidebar navigation

The app has a persistent left sidebar with these exact items:

1. Dashboard
2. Smart Search
3. Market Mapping
4. Competitor Intel
5. Candidate Discovery
6. Talent Pool
7. Overview Report

Important: Do not add a separate Salary Intelligence tab. Salary intelligence lives inside Market Mapping.

## Compliance-first MVP note

Add this message visibly in the UI:

> Compliance-first MVP: This demo uses approved uploaded/sample data only. Candidate recommendations are evidence-based and require human review. The system does not make automated hiring decisions.

When the UI says "all companies," it means:

> All companies found in the approved demo dataset for the selected role.

The MVP must never imply that it scanned the entire internet.

## Candidate fit scoring model

Candidate score must be transparent and calculated from these weights:

| Scoring factor | Weight |
| --- | ---: |
| Must-have skill match | 35% |
| Relevant experience | 25% |
| Industry/domain match | 15% |
| Seniority match | 10% |
| Location/language fit | 10% |
| Compensation/availability signal | 5% |

Trust rule: if evidence is missing, display Not evidenced. Do not infer unsupported claims.

## GitHub repository setup

Recommended repo name:

```text
hyintel-ai
```

Create and push with GitHub CLI:

```bash
git init
git add .
git commit -m "Initial HyIntel AI MVP docs and app scaffold"
gh repo create hyintel-ai --public --source=. --remote=origin --push
```

Recommended branch model for the hackathon:

```text
main        demo-ready branch
feature/*   small feature branches
fix/*       bug fixes and polish
```

Suggested labels:

```text
mvp, ui, data, compliance, scoring, report, polish, demo-blocker
```

## Definition of done

The MVP is demo-ready when:

- The app runs locally with one command.
- All seven navigation items work.
- Role switching updates all major pages.
- DevOps Engineer is the default selected role.
- Market Mapping contains salary intelligence and has no separate Salary Intelligence tab.
- Candidate fit scores show the six weighted factors.
- Missing evidence is shown as Not evidenced.
- The UI includes Approved sample data, Evidence-based, Human review required, and Demo intelligence only trust indicators.
- No external APIs, scraping, authentication, or live platform integrations are used.
- Overview Report renders a credible one-page report for each role.

## Demo script

1. Open Dashboard and show the three completed role analyses.
2. Switch between DevOps Engineer, Finance Manager, and Customer Service Representative to prove pre-analysis exists for all roles.
3. Go to Smart Search, click Parse JD, and show parsed skills, titles, and Boolean strings.
4. Go to Market Mapping, search or sort the company table, and point out salary intelligence inside the same tab.
5. Go to Candidate Discovery, open a candidate score breakdown, and highlight evidence plus Not evidenced fields.
6. Go to Talent Pool, update a candidate status.
7. Go to Overview Report and generate the one-page market overview.

## Non-goals

- No live scraping.
- No real LinkedIn, JobStreet, Indeed, or external recruitment platform integration.
- No automated hiring decisions.
- No opaque AI ranking without evidence trails.
- No full ATS, CRM, or email-sequencing workflow in phase one.
- No production authentication or RBAC in the MVP.

## License

For hackathon/demo use. Add your preferred license before public launch.
