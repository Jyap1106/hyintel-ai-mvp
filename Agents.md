# Agents.md - HyIntel AI Coding Agent Guide

This file gives AI coding agents, copilots, and contributors the rules for building HyIntel AI without breaking the MVP intent.

## Product context

HyIntel AI is a compliance-first recruitment intelligence dashboard for Talent Acquisition teams. The hackathon MVP is a polished local web app that uses approved mock/sample data only. It should feel like a real B2B SaaS product, but it is not a production backend and must not connect to live recruitment platforms.

Tagline:

```text
AI-powered recruitment intelligence for faster, explainable, compliant hiring decisions.
```

Primary user:

```text
Talent Acquisition teams, recruitment leads, and hiring managers.
```

Default selected role:

```text
DevOps Engineer - Malaysia - FinTech - Mandarin preferred - Permanent
```

## Non-negotiable guardrails

1. Use mock/sample data only.
2. Do not scrape websites.
3. Do not integrate LinkedIn, JobStreet, Indeed, or external recruitment platforms.
4. Do not add authentication for the MVP.
5. Do not add a separate Salary Intelligence tab.
6. Salary intelligence must live inside Market Mapping.
7. Do not imply that the app scanned the whole internet.
8. If the UI says "all companies," clarify that it means all companies found in the approved demo dataset for the selected role.
9. Do not make automated hiring decisions.
10. Candidate recommendations must require human review.
11. Missing evidence must display as Not evidenced.
12. Candidate ranking must show the transparent weighted scoring model.

## Build stack

Recommended implementation:

- React + Vite
- TypeScript
- Tailwind CSS
- shadcn/ui-style components
- Recharts
- Local JSON or TypeScript seed data
- No external API dependency

## UI rules

Use a clean enterprise B2B SaaS style:

- White and very light gray background
- Green as the primary accent color
- Soft rounded cards
- Left sidebar navigation
- Top page summary cards
- Tables, charts, progress bars, badges, status dropdowns, and report previews
- Small trust indicators such as Approved sample data, Evidence-based, Human review required, and Demo intelligence only

The app must feel like a working product, not a wireframe.

## Required navigation

The persistent sidebar must include exactly:

1. Dashboard
2. Smart Search
3. Market Mapping
4. Competitor Intel
5. Candidate Discovery
6. Talent Pool
7. Overview Report

Sidebar bottom card:

```text
Talent Pool
43 candidates in your referral pool
```

Sidebar user profile:

```text
Jeremy Yap
TA Lead
```

## Required global page header

Each page must include:

- Page title
- Short page description
- Role selector dropdown
- Country selector dropdown
- Industry selector dropdown
- Run Analysis button, or Generate Overview Report button on Overview Report

## Role switching rule

The app must support these three pre-analyzed roles:

- DevOps Engineer
- Finance Manager
- Customer Service Representative

Changing the role must update:

- Dashboard metrics
- Market Mapping data
- Competitor Intel data
- Candidate Discovery data
- Talent Pool data
- Overview Report data

## Candidate scoring model

Always use this weighted model:

| Factor | Weight |
| --- | ---: |
| Must-have skill match | 35 |
| Relevant experience | 25 |
| Industry/domain match | 15 |
| Seniority match | 10 |
| Location/language fit | 10 |
| Compensation/availability signal | 5 |

Implementation guidance:

```ts
export type ScoreFactorKey =
  | 'mustHaveSkillMatch'
  | 'relevantExperience'
  | 'industryDomainMatch'
  | 'seniorityMatch'
  | 'locationLanguageFit'
  | 'compensationAvailabilitySignal';

export const SCORING_WEIGHTS: Record<ScoreFactorKey, number> = {
  mustHaveSkillMatch: 35,
  relevantExperience: 25,
  industryDomainMatch: 15,
  seniorityMatch: 10,
  locationLanguageFit: 10,
  compensationAvailabilitySignal: 5,
};
```

Trust rule:

```text
If evidence is missing, mark it as Not evidenced. Do not infer unsupported claims.
```

## Suggested agent responsibilities

### Product Agent

Owns product consistency and acceptance criteria.

Responsibilities:

- Keep the implementation aligned to prd.md.
- Enforce the no-scraping/no-external-API rule.
- Check that all role switching updates are visible.
- Verify that salary intelligence is inside Market Mapping only.

### UI Agent

Owns layout, visual polish, and component consistency.

Responsibilities:

- Build the sidebar, page headers, metric cards, tables, charts, and report preview.
- Use Tailwind and shadcn/ui-style patterns.
- Keep the dashboard professional and demo-ready.
- Maintain responsive behavior for laptop demo screens.

### Data Agent

Owns mock seed data.

Responsibilities:

- Create realistic local data for roles, companies, competitors, candidates, talent pool, and reports.
- Keep all data clearly labeled as demo/sample data.
- Ensure no real scraping or API calls are introduced.
- Keep data consistent across pages.

### Scoring Agent

Owns candidate scoring transparency.

Responsibilities:

- Implement deterministic scoring based on the six weighted factors.
- Show score breakdowns per candidate.
- Display Not evidenced where data is missing.
- Avoid hidden or opaque ranking logic.

### Report Agent

Owns overview report generation.

Responsibilities:

- Generate a credible one-page market overview report from local data.
- Include market size, competitor demand, salary benchmark, sourcing targets, candidate availability, hiring risks, and next actions.
- Add trust/compliance labels to the report.

### QA Agent

Owns demo readiness.

Responsibilities:

- Test all navigation items.
- Test role switching.
- Test filters, sorting, search, status dropdowns, charts, and report preview.
- Verify that no external network call is required.
- Check copy for compliance language.

## File-level guidance

Recommended files:

```text
src/data/roles.ts              role definitions and default selected role
src/data/marketCompanies.ts    Market Mapping company rows
src/data/competitors.ts        competitor demand and intensity
src/data/candidates.ts         candidate profiles and evidence
src/data/talentPool.ts         candidate pipeline status
src/data/reports.ts            overview report content
src/data/scoringModel.ts       scoring weights and factor labels
src/lib/scoring.ts             scoring utility functions
src/lib/filters.ts             table filters and sort helpers
src/lib/formatters.ts          salary, number, and percent formatting
```

## Component rules

Use reusable components where possible:

```text
MetricCard
TrustBadge
StatusBadge
RoleSelector
TopFilters
DataTable
ScoreBreakdown
CandidateCard
SalaryRangeBar
ReportPreview
```

Do not hard-code role-specific content inside page components when it can live in `src/data`.

## Pull request checklist

Before merging any branch:

- The app runs with `npm run dev`.
- No external API calls were added.
- No scraping packages were added.
- No authentication flow was added.
- All seven navigation items render.
- Role switching updates at least one obvious section per page.
- Candidate scoring has all six factors.
- Missing evidence appears as Not evidenced.
- Trust badges are visible.
- Market Mapping includes salary intelligence.
- There is no separate Salary Intelligence tab.
- The default role is DevOps Engineer.

## Common mistakes to avoid

- Adding a live data connector because it feels more realistic.
- Calling external AI APIs for summaries during the demo.
- Building a backend before the click-through experience is polished.
- Making candidate rankings look like final hiring decisions.
- Hiding scoring logic behind vague AI language.
- Creating a Salary Intelligence tab separate from Market Mapping.
- Referring to "all companies in the market" instead of "all companies in the approved demo dataset."

## Demo copy snippets

Use these snippets across the UI:

```text
Approved sample data
Evidence-based
Human review required
Demo intelligence only
Compliance-first MVP
```

Compliance note:

```text
This demo uses approved uploaded/sample data only. Candidate recommendations are evidence-based and require human review. The system does not make automated hiring decisions.
```
