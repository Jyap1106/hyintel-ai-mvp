# Tasks.md - HyIntel AI MVP Implementation Plan

This task list is designed for a hackathon/demo build. Prioritize a polished, believable, clickable MVP over production backend work.

## Priority legend

| Priority | Meaning |
| --- | --- |
| P0 | Required for demo credibility |
| P1 | Important polish or interactivity |
| P2 | Nice to have if time remains |

## Milestone 0 - Repository setup

- [ ] P0 Create GitHub repository named `hyintel-ai`.
- [ ] P0 Add Readme.md, Agents.md, Tasks.md, dataset.md, prd.md, and roadmap.md to the repository root.
- [ ] P0 Scaffold React + Vite + TypeScript app.
- [ ] P0 Install Tailwind CSS.
- [ ] P0 Install Recharts and lucide-react.
- [ ] P1 Install shadcn/ui-style components or create equivalent local components.
- [ ] P0 Add `npm run dev` local start script.
- [ ] P0 Create base folder structure under `src/`.

Acceptance criteria:

- Repository opens cleanly on GitHub.
- App starts locally with one command.
- Docs explain the MVP scope and compliance guardrails.

## Milestone 1 - Data model and seed data

- [ ] P0 Create `src/data/roles.ts` with the three pilot roles.
- [ ] P0 Set DevOps Engineer as the default selected role.
- [ ] P0 Create role-level metrics for Dashboard.
- [ ] P0 Create Market Mapping company data for DevOps Engineer, Finance Manager, and Customer Service Representative.
- [ ] P0 Create salary benchmark data by role and country.
- [ ] P0 Create competitor demand data by role.
- [ ] P0 Create candidate profile data with evidence notes and scoring factors.
- [ ] P0 Create talent pool data with 43 referral pool candidates represented in summary/count form and enough visible candidate rows for the demo.
- [ ] P0 Create overview report seed content by role.
- [ ] P1 Add realistic work setup, company size, hiring intensity, and sourcing recommendation fields.

Acceptance criteria:

- No page depends on live data.
- Role switching returns different data for all three roles.
- Data labels clearly indicate demo/sample data.

## Milestone 2 - Global layout

- [ ] P0 Build persistent left sidebar.
- [ ] P0 Add HyIntel AI logo/wordmark.
- [ ] P0 Add exact navigation items: Dashboard, Smart Search, Market Mapping, Competitor Intel, Candidate Discovery, Talent Pool, Overview Report.
- [ ] P0 Highlight active page in green.
- [ ] P0 Add Talent Pool sidebar card with "43 candidates in your referral pool".
- [ ] P0 Add bottom user profile: Jeremy Yap, TA Lead.
- [ ] P0 Build page header with title, description, role selector, country selector, industry selector, and action button.
- [ ] P1 Add trust/compliance badge strip.
- [ ] P1 Add responsive behavior for laptop and desktop screen sizes.

Acceptance criteria:

- Layout feels like a B2B SaaS dashboard.
- All pages share the same filters and action area.
- Sidebar persists during navigation.

## Milestone 3 - Dashboard page

- [ ] P0 Build top metric cards.
- [ ] P0 Default DevOps metrics: 12 active job requests, 348 available candidates, 74% match rate, 18h avg time-to-shortlist, 183 companies mapped, 8 reports generated.
- [ ] P0 Add Completed Analysis Overview role cards for all three pilot roles.
- [ ] P0 Add Smart Search Assistant card and Start Smart Search button.
- [ ] P0 Add Recent Searches table.
- [ ] P0 Add Top Matches This Week mini-cards for Chen Wei Ming, Priya Nair, and Nurul Aina.
- [ ] P1 Add a small chart showing demand or completion status.

Acceptance criteria:

- Dashboard communicates that analysis is already complete for all three roles.
- Switching the selected role updates top metrics.

## Milestone 4 - Smart Search page

- [ ] P0 Add JD role dropdown.
- [ ] P0 Add prefilled JD textarea based on selected role.
- [ ] P0 Add Parse JD button.
- [ ] P0 Show parsed role output after clicking Parse JD.
- [ ] P0 Include Core role, Seniority, Must-have skills, Nice-to-have skills, Business context, Hiring challenge, Suggested search titles, and Recommended Boolean strings.
- [ ] P0 Add correct DevOps Engineer skills and titles.
- [ ] P0 Add correct Finance Manager skills and titles.
- [ ] P0 Add correct Customer Service Representative skills and titles.
- [ ] P1 Add a parsed completeness score or JD quality indicator.

Acceptance criteria:

- Page simulates hiring manager intake convincingly.
- Parse JD interaction works without external API calls.

## Milestone 5 - Market Mapping page

- [ ] P0 Build top metric cards for all three roles.
- [ ] P0 DevOps metrics: 183 companies mapped, 2,184 employees in similar roles, 286 open roles found, RM 14.5k median salary, 4-9 years experience range, High hiring difficulty.
- [ ] P0 Finance Manager metrics: 146 companies mapped, 3,420 employees in similar roles, 194 open roles found, RM 12.8k median salary, 5-12 years experience range, Moderate hiring difficulty.
- [ ] P0 Customer Service Representative metrics: 312 companies mapped, 18,600 employees in similar roles, 1,840 open roles found, RM 4.2k median salary, 0-5 years experience range, Moderate / High volume hiring difficulty.
- [ ] P0 Build hero table titled "All companies with this role".
- [ ] P0 Add columns: Company, Industry, Country, Matching role titles, Estimated employees in role, Open roles, Years of experience range, Salary offered, Work setup, Hiring intensity, Sourcing recommendation.
- [ ] P0 Add filters for Country, Industry, Salary range, Years of experience, Hiring intensity, Work setup, Company size.
- [ ] P0 Add search input placeholder: "Search company, title, or skill".
- [ ] P0 Add sorting by employees in role, open roles, salary offered, years of experience, and hiring intensity.
- [ ] P0 Add salary benchmark chart or salary range cards inside Market Mapping.
- [ ] P0 Do not create Salary Intelligence as a separate tab.
- [ ] P1 Add company detail drawer or expandable row.

Acceptance criteria:

- Market Mapping is the hero page.
- Salary intelligence is clearly present inside Market Mapping.
- "All companies" is clearly scoped to the approved demo dataset.

## Milestone 6 - Competitor Intel page

- [ ] P0 Add competitor overview cards with open role counts and intensity signals.
- [ ] P0 Add competitor table by selected role.
- [ ] P0 Show common skills demanded by competitors.
- [ ] P0 Show role-by-role headcount/opening breakdowns.
- [ ] P0 Add adjacent-industry guidance.
- [ ] P1 Add Recharts bar chart for competitor demand.
- [ ] P1 Add expandable competitor rows.

Acceptance criteria:

- Page explains who else is hiring for the role and how intense demand is.
- Page uses only approved sample data.

## Milestone 7 - Candidate Discovery page

- [ ] P0 Build ranked candidate table/cards.
- [ ] P0 Include candidate name, fit score, current salary, expected salary, key match, main risk, location/language signal, and availability.
- [ ] P0 Add score breakdown with six factors.
- [ ] P0 Add evidence panel for each candidate.
- [ ] P0 Display Not evidenced wherever data is missing.
- [ ] P0 Add sorting by Fit Score and Experience.
- [ ] P1 Add candidate detail drawer for suitability one-pager preview.
- [ ] P1 Add filter chips for location, salary risk, language, industry, and availability.

Acceptance criteria:

- Recruiter can explain why a candidate is recommended.
- The page never implies automated hiring decisions.

## Milestone 8 - Talent Pool page

- [ ] P0 Build candidate talent pool table.
- [ ] P0 Include status dropdowns.
- [ ] P0 Include status options: New, Reviewed, Contacted, Shortlisted, HM Review, Interviewing, Offer, Nurture, Rejected.
- [ ] P0 Include owner, source, next action, last updated, and notes.
- [ ] P0 Show count: 43 candidates in referral pool.
- [ ] P1 Add simple pipeline summary cards.
- [ ] P1 Add drag/drop or kanban-style view if time allows.

Acceptance criteria:

- User can manage candidate status in a credible demo flow.
- State changes work locally.

## Milestone 9 - Overview Report page

- [ ] P0 Add Generate Overview Report button.
- [ ] P0 Render a one-page report for the selected role.
- [ ] P0 Include market summary, market size, companies mapped, open roles, salary benchmark, experience range, competitor demand, sourcing targets, candidate pool summary, risks, and recommended next steps.
- [ ] P0 Include compliance note in report preview.
- [ ] P1 Add Export PDF-style button as visual-only or print-friendly output.
- [ ] P1 Add report timestamp label such as "Generated from approved demo dataset".

Acceptance criteria:

- Report is credible enough to show a hiring manager.
- Report changes when the role changes.

## Milestone 10 - Polish and QA

- [ ] P0 Verify all navigation paths.
- [ ] P0 Verify role switching on all pages.
- [ ] P0 Verify no network dependency is required.
- [ ] P0 Verify no scraping package is installed.
- [ ] P0 Verify all compliance labels are visible.
- [ ] P0 Verify missing candidate evidence displays Not evidenced.
- [ ] P0 Verify salary intelligence is not a separate tab.
- [ ] P1 Improve empty states, hover states, chart labels, and table density.
- [ ] P1 Add loading/success micro-interactions for Parse JD, Run Analysis, and Generate Overview Report.
- [ ] P1 Run Lighthouse or basic browser performance check.

Acceptance criteria:

- Demo can be completed end-to-end without code changes.
- UI feels polished and professional.

## Milestone 11 - GitHub and deployment

- [ ] P0 Commit all source and docs.
- [ ] P0 Add `.gitignore`.
- [ ] P0 Add basic GitHub issues for remaining tasks.
- [ ] P1 Deploy to Vercel, Netlify, or GitHub Pages if allowed by hackathon rules.
- [ ] P1 Add screenshots or a short GIF to Readme.md.
- [ ] P2 Add GitHub Actions for lint/build.

Acceptance criteria:

- Repo is shareable.
- Demo can be run locally by judges or teammates.

## Demo blocker checklist

These items block the demo if incomplete:

- [ ] App does not start locally.
- [ ] Sidebar navigation is missing.
- [ ] Default role is not DevOps Engineer.
- [ ] Role switching does not update pages.
- [ ] Market Mapping lacks company table.
- [ ] Salary intelligence appears as a separate tab.
- [ ] Candidate scoring lacks evidence breakdown.
- [ ] Missing evidence is inferred instead of marked Not evidenced.
- [ ] UI implies live scraping or real LinkedIn/JobStreet/Indeed integration.
- [ ] Overview Report is missing.
