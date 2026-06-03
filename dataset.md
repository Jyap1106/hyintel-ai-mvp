# dataset.md - HyIntel AI Approved Demo Dataset

This document defines the local mock/sample data for the HyIntel AI MVP. The dataset is intentionally realistic but not live. It is approved demo data only.

## Compliance position

HyIntel AI MVP uses approved uploaded/sample data only.

Rules:

- No live scraping.
- No real LinkedIn, JobStreet, Indeed, or external recruitment platform integration.
- No external APIs.
- No automated hiring decisions.
- Candidate recommendations are evidence-based and require human review.
- If evidence is missing, display Not evidenced.
- "All companies" means all companies found in the approved demo dataset for the selected role.

## Recommended local data files

```text
src/data/
  roles.ts
  marketCompanies.ts
  competitors.ts
  candidates.ts
  talentPool.ts
  reports.ts
  scoringModel.ts
```

CSV-style equivalents can be kept in `data/seed/` if the team wants visible data files:

```text
data/seed/
  sample_jd_devops.txt
  sample_jd_finance_manager.txt
  sample_jd_customer_service.txt
  market_companies.csv
  competitor_roles.csv
  candidate_profiles.csv
  talent_pool.csv
  overview_reports.json
```

## Pilot role configuration

| Role ID | Role | Market | Industry | Language | Role type | Default |
| --- | --- | --- | --- | --- | --- | --- |
| devops-engineer | DevOps Engineer | Malaysia / Singapore | FinTech | Mandarin preferred | Permanent | Yes |
| finance-manager | Finance Manager | Malaysia / Singapore | Finance, shared services, professional services | Mandarin preferred | Permanent | No |
| customer-service-representative | Customer Service Representative | Malaysia / Singapore | BPO, e-commerce, banking, FinTech, contact centre | Mandarin preferred | Permanent | No |

## Dashboard role summary data

| Role | Companies mapped | Available candidates | Competitor roles open | Status |
| --- | ---: | ---: | ---: | --- |
| DevOps Engineer | 183 | 348 | 286 | Analysis complete |
| Finance Manager | 146 | 612 | 194 | Analysis complete |
| Customer Service Representative | 312 | 15,800 | 1,840 | Analysis complete |

## Dashboard metrics by selected role

| Metric | DevOps Engineer | Finance Manager | Customer Service Representative |
| --- | ---: | ---: | ---: |
| Active job requests | 12 | 9 | 38 |
| Available candidates | 348 | 612 | 15,800 |
| Candidate match rate | 74% | 68% | 81% |
| Avg time-to-shortlist | 18h | 22h | 9h |
| Companies mapped | 183 | 146 | 312 |
| Reports generated | 8 | 6 | 11 |

## Market Mapping top metrics

| Metric | DevOps Engineer | Finance Manager | Customer Service Representative |
| --- | --- | --- | --- |
| Companies mapped | 183 | 146 | 312 |
| Employees in similar roles | 2,184 | 3,420 | 18,600 |
| Open roles found | 286 | 194 | 1,840 |
| Median salary offered | RM 14.5k | RM 12.8k | RM 4.2k |
| Experience range | 4-9 years | 5-12 years | 0-5 years |
| Hiring difficulty | High | Moderate | Moderate / High volume |

## Market Mapping company schema

| Field | Type | Description |
| --- | --- | --- |
| id | string | Stable row ID |
| roleId | string | Pilot role ID |
| company | string | Company name |
| industry | string | Industry cluster |
| country | string | Malaysia, Singapore, or Malaysia / Singapore |
| matchingRoleTitles | string[] | Similar titles found in approved demo dataset |
| estimatedEmployeesInRole | number | Estimated employees in role or similar role |
| openRoles | number | Open roles in approved demo dataset |
| experienceRange | string | Typical employee experience range |
| salaryOffered | string | Salary range shown in local dataset |
| salaryMinMonthly | number | Normalized monthly minimum for sorting |
| salaryMaxMonthly | number | Normalized monthly maximum for sorting |
| currency | string | RM or SGD |
| workSetup | string | On-site, Hybrid, Remote, Shift, or Mixed |
| hiringIntensity | string | Low, Moderate, High, Very High |
| sourcingRecommendation | string | Recommended sourcing action |
| companySize | string | Startup, Mid-market, Enterprise, Large enterprise |

## DevOps Engineer company seed rows

| Company | Industry | Country | Matching role titles | Employees in role | Open roles | Experience range | Salary offered | Work setup | Hiring intensity | Sourcing recommendation |
| --- | --- | --- | --- | ---: | ---: | --- | --- | --- | --- | --- |
| Grab | FinTech / Superapp | Malaysia / Singapore | DevOps Engineer; SRE; Platform Engineer | 148 | 12 | 4-9 years | RM 14k-22k | Hybrid | Very High | Target adjacent platform teams; expect salary pressure |
| Shopee | E-commerce / FinTech | Malaysia / Singapore | SRE; Cloud Engineer; DevOps Engineer | 136 | 9 | 3-8 years | RM 13k-21k | Hybrid | High | Strong source for high-scale CI/CD and cloud experience |
| Touch n Go Digital | E-wallet | Malaysia | DevOps Engineer; Cloud Platform Engineer | 84 | 6 | 4-8 years | RM 12k-19k | Hybrid | High | Good target for FinTech domain fit |
| BigPay | FinTech | Malaysia | Cloud Engineer; Platform Engineer | 61 | 5 | 4-9 years | RM 13k-20k | Hybrid | High | Target candidates with payments and AWS exposure |
| Boost | FinTech | Malaysia | DevSecOps Engineer; DevOps Engineer | 56 | 4 | 5-10 years | RM 13k-21k | Hybrid | Moderate | Strong DevSecOps overlap |
| Razer Fintech | FinTech | Malaysia / Singapore | SRE; Cloud Engineer | 42 | 3 | 4-8 years | RM 12k-20k | Hybrid | Moderate | Source for cloud operations profiles |
| AirAsia MOVE | Travel / FinTech | Malaysia | Platform Engineer; DevOps Engineer | 73 | 5 | 3-8 years | RM 12k-18k | Hybrid | Moderate | Good for high-traffic platform experience |
| Maybank | Banking | Malaysia | Infrastructure Engineer; DevOps Engineer | 95 | 4 | 5-12 years | RM 11k-18k | Hybrid | Moderate | Target cloud transformation teams |
| CIMB | Banking | Malaysia | Cloud Engineer; DevOps Engineer | 88 | 3 | 5-12 years | RM 11k-17k | Hybrid | Moderate | Good for regulated banking experience |
| Wise | FinTech | Singapore | SRE; Platform Engineer | 52 | 4 | 4-9 years | SGD 9k-16k | Hybrid | High | High salary competitor; use for market benchmark |
| Stripe | Payments | Singapore | Infrastructure Engineer; SRE | 49 | 3 | 5-10 years | SGD 11k-18k | Hybrid | High | Premium compensation competitor |
| Ant International | Payments | Malaysia / Singapore | DevOps Engineer; SRE | 67 | 6 | 4-10 years | RM 14k-23k | Hybrid | High | Target Mandarin and payments-domain profiles |

## Finance Manager company seed rows

| Company | Industry | Country | Matching role titles | Employees in role | Open roles | Experience range | Salary offered | Work setup | Hiring intensity | Sourcing recommendation |
| --- | --- | --- | --- | ---: | ---: | --- | --- | --- | --- | --- |
| WPP | Advertising / Shared Services | Malaysia | Finance Manager; GL Accountant; Reporting Manager | 92 | 7 | 5-12 years | RM 10k-17k | Hybrid | High | Source for shared services and reporting depth |
| Averis | Shared Services | Malaysia | Finance Manager; AP Accountant; AR Accountant | 128 | 9 | 4-10 years | RM 9k-15k | Hybrid | High | Large pool for AP/AR/GL operations |
| KPMG | Professional Services | Malaysia / Singapore | Finance Manager; Audit Manager; Reporting Manager | 115 | 8 | 5-12 years | RM 11k-18k | Hybrid | High | Strong audit-to-finance conversion pool |
| Deloitte | Professional Services | Malaysia / Singapore | Finance Manager; Accounting Manager; FP&A Manager | 122 | 10 | 5-13 years | RM 12k-20k | Hybrid | Very High | High demand; strong domain and stakeholder skills |
| PwC | Professional Services | Malaysia / Singapore | Finance Manager; Tax Manager; Audit Manager | 119 | 8 | 5-13 years | RM 12k-20k | Hybrid | High | Strong tax, audit, and reporting skill base |
| Bain & Partners | Consulting | Malaysia / Singapore | Finance Manager; Finance Business Partner | 46 | 3 | 6-12 years | RM 14k-22k | Hybrid | Moderate | Premium finance business partnering profiles |
| Shopee | E-commerce | Malaysia / Singapore | Finance Manager; Cost Controller; FP&A Manager | 84 | 6 | 5-11 years | RM 12k-19k | Hybrid | High | Good for fast-paced commercial finance |
| British American Tobacco | FMCG | Malaysia | Finance Manager; Cost Controller; Reporting Manager | 76 | 5 | 6-12 years | RM 13k-21k | Hybrid | Moderate | Strong cost control and reporting profiles |
| Grab | Superapp / FinTech | Malaysia / Singapore | Finance Manager; FP&A Manager | 69 | 4 | 5-11 years | RM 12k-20k | Hybrid | Moderate | Good for FinTech and stakeholder reporting |
| AirAsia MOVE | Travel / Digital | Malaysia | Finance Manager; Cost Controller | 58 | 4 | 5-10 years | RM 10k-17k | Hybrid | Moderate | Source cost-control and digital finance profiles |
| Maybank | Banking | Malaysia | Finance Manager; GL Accountant | 140 | 5 | 6-14 years | RM 12k-20k | Hybrid | Moderate | Strong regulated finance experience |
| CIMB | Banking | Malaysia | Finance Manager; Reporting Manager | 132 | 4 | 6-14 years | RM 12k-19k | Hybrid | Moderate | Good for financial reporting and governance |
| Maxis | Telecommunications | Malaysia | Finance Manager; FP&A Manager | 63 | 3 | 5-12 years | RM 11k-18k | Hybrid | Low | Source stable corporate finance profiles |
| Axiata | Telecommunications | Malaysia | Finance Manager; Treasury Analyst | 59 | 3 | 5-12 years | RM 11k-18k | Hybrid | Low | Target treasury and group reporting profiles |
| Nestle Malaysia | FMCG | Malaysia | Finance Manager; Cost Controller | 71 | 4 | 5-12 years | RM 12k-19k | Hybrid | Moderate | Strong FMCG cost and operations finance pool |
| EY | Professional Services | Malaysia / Singapore | Accounting Manager; Audit Manager | 108 | 7 | 5-12 years | RM 11k-18k | Hybrid | High | Good audit and accounting manager talent pool |
| Accenture | Consulting / Shared Services | Malaysia | Finance Manager; Finance Business Partner | 88 | 6 | 5-11 years | RM 10k-17k | Hybrid | High | Good for transformation and shared-services finance |

## Finance Manager market titles

- Finance Manager
- Full Set Accountant
- Senior Accountant
- Cost Controller
- AP Accountant
- AR Accountant
- GL Accountant
- Accounting Manager
- Finance Business Partner
- FP&A Manager
- Reporting Manager
- Treasury Analyst
- Tax Analyst
- Audit Manager
- Commercial Finance Manager

## Finance Manager skillsets

- Reconciliation
- SAP
- BukuApp
- Accounts Payable
- Accounts Receivable
- General Ledger
- Month-End Closing
- Financial Reporting
- Budgeting
- Forecasting
- Cost Control
- Tax Compliance
- Audit
- IFRS
- MFRS
- Power BI
- Advanced Excel
- Oracle NetSuite
- Variance Analysis
- Stakeholder Reporting

## Customer Service Representative company seed rows

Customer Service Representative should have higher numbers because the market is larger and more volume-driven.

| Company | Industry | Country | Matching role titles | Employees in role | Open roles | Experience range | Salary offered | Work setup | Hiring intensity | Sourcing recommendation |
| --- | --- | --- | --- | ---: | ---: | --- | --- | --- | --- | --- |
| TDCX | BPO / Contact centre | Malaysia / Singapore | Customer Service Representative; Customer Experience Agent; Live Chat Agent | 1,260 | 180 | 0-5 years | RM 3.5k-6.0k | Shift / Hybrid | Very High | Strong multilingual volume pool |
| Concentrix | BPO / Contact centre | Malaysia / Singapore | Customer Support Specialist; Call Centre Agent; Escalation Specialist | 1,480 | 220 | 0-5 years | RM 3.2k-5.8k | Shift | Very High | Primary high-volume sourcing target |
| Teleperformance | BPO / Contact centre | Malaysia | Customer Service Representative; Helpdesk Agent; Email Support Specialist | 1,350 | 210 | 0-5 years | RM 3.0k-5.5k | Shift | Very High | Good for call handling and SLA experience |
| Accenture | Consulting / BPO | Malaysia | Customer Support Specialist; Contact Centre Executive | 820 | 95 | 1-5 years | RM 3.8k-6.5k | Hybrid / Shift | High | Source process-oriented support profiles |
| Shopee | E-commerce | Malaysia / Singapore | Customer Experience Agent; Live Chat Agent; Email Support Specialist | 940 | 130 | 0-4 years | RM 3.6k-6.2k | Hybrid / Shift | Very High | Strong e-commerce support experience |
| Lazada | E-commerce | Malaysia / Singapore | Customer Service Representative; Seller Support Agent | 710 | 88 | 0-4 years | RM 3.5k-6.0k | Hybrid / Shift | High | Source marketplace support profiles |
| Grab | Superapp / FinTech | Malaysia / Singapore | Customer Experience Specialist; Escalation Specialist; Payment Support Agent | 760 | 92 | 1-5 years | RM 4.0k-7.0k | Hybrid / Shift | High | Good for payments and complex escalation |
| Maybank | Banking | Malaysia | Banking Customer Care Executive; Call Centre Agent | 1,120 | 75 | 1-6 years | RM 3.8k-6.8k | On-site / Shift | High | Strong regulated customer care pool |
| CIMB | Banking | Malaysia | Banking Customer Care Executive; Helpdesk Agent | 980 | 64 | 1-6 years | RM 3.7k-6.5k | On-site / Shift | High | Source for banking and KYC support |
| Touch n Go Digital | E-wallet | Malaysia | Customer Support Specialist; Payment Support Agent; Fraud Escalation Agent | 420 | 58 | 1-5 years | RM 4.2k-7.2k | Hybrid / Shift | High | Best for wallet, fraud, and payment support |
| BigPay | FinTech | Malaysia | Customer Support Specialist; KYC Support Agent | 260 | 34 | 1-5 years | RM 4.0k-6.8k | Hybrid | Moderate | Good FinTech domain overlap |
| Boost | FinTech | Malaysia | Customer Service Representative; Merchant Support Agent | 310 | 42 | 1-5 years | RM 3.8k-6.5k | Hybrid / Shift | Moderate | Good for merchant support skills |
| AirAsia MOVE | Travel / Digital | Malaysia | Customer Experience Agent; Live Chat Agent | 650 | 70 | 0-5 years | RM 3.5k-6.0k | Shift / Hybrid | High | Source travel disruption and live-chat experience |
| Agoda | Travel / E-commerce | Malaysia | Customer Experience Specialist; Email Support Specialist | 530 | 55 | 1-5 years | RM 4.0k-7.0k | Hybrid / Shift | High | Good for multilingual travel support |
| foodpanda | E-commerce / Delivery | Malaysia / Singapore | Customer Support Agent; Escalation Specialist | 480 | 62 | 0-4 years | RM 3.5k-6.2k | Hybrid / Shift | High | Source fast-paced issue resolution profiles |
| Maxis | Telecommunications | Malaysia | Customer Care Consultant; Contact Centre Executive | 870 | 76 | 0-5 years | RM 3.3k-5.8k | Shift | High | Good for high-volume phone support |
| Astro | Media / Telecommunications | Malaysia | Customer Service Executive; Call Centre Agent | 690 | 48 | 0-5 years | RM 3.2k-5.5k | Shift | Moderate | Strong call handling source pool |
| HSBC | Banking | Malaysia | Banking Customer Care Executive; KYC Support Agent | 620 | 46 | 1-6 years | RM 4.2k-7.5k | On-site / Hybrid | Moderate | Strong compliance and banking service profiles |
| Standard Chartered | Banking | Malaysia / Singapore | Customer Care Executive; Escalation Specialist | 540 | 38 | 1-6 years | RM 4.3k-7.8k | Hybrid | Moderate | Good for regulated support and escalation |
| RHB | Banking | Malaysia | Call Centre Agent; Customer Service Executive | 760 | 52 | 1-5 years | RM 3.6k-6.2k | On-site / Shift | Moderate | Source banking call centre experience |

## Smart Search JD summaries

### DevOps Engineer

Must-have skills:

- AWS
- Kubernetes
- Docker
- Terraform
- CI/CD
- Linux

Nice-to-have skills:

- Mandarin
- FinTech domain experience
- Security automation
- Observability tools
- Python scripting

Alternative titles:

- Site Reliability Engineer
- Cloud Infrastructure Engineer
- Platform Engineer
- DevSecOps Engineer
- Release Engineer

Example Boolean string:

```text
("DevOps Engineer" OR SRE OR "Site Reliability Engineer" OR "Platform Engineer" OR "Cloud Infrastructure Engineer") AND (AWS OR Kubernetes OR Docker OR Terraform OR CI/CD OR Linux) AND (FinTech OR payments OR banking OR e-wallet)
```

### Finance Manager

Must-have skills:

- Full set accounting
- Financial reporting
- Reconciliation
- SAP
- Accounts payable
- Accounts receivable
- General ledger
- Month-end closing
- Budgeting and forecasting

Nice-to-have skills:

- BukuApp
- Power BI
- Oracle NetSuite
- IFRS / MFRS
- Tax compliance
- Audit background
- Shared services experience
- Mandarin

Alternative titles:

- Finance Manager
- Senior Accountant
- Full Set Accountant
- Accounting Manager
- FP&A Manager
- Finance Business Partner
- Cost Controller
- GL Accountant
- AP Accountant
- AR Accountant
- Reporting Manager
- Treasury Analyst

Example Boolean string:

```text
("Finance Manager" OR "Accounting Manager" OR "Senior Accountant" OR "Full Set Accountant" OR "FP&A Manager" OR "Finance Business Partner") AND (SAP OR reconciliation OR "general ledger" OR "month-end closing" OR budgeting OR forecasting) AND (shared services OR professional services OR banking OR FinTech)
```

### Customer Service Representative

Must-have skills:

- Customer support
- Call handling
- Live chat
- Email support
- CRM
- Complaint handling
- SLA management
- Bahasa Malaysia
- English

Nice-to-have skills:

- Mandarin
- Zendesk
- Salesforce
- FinTech or banking support
- E-commerce support
- KYC support
- Payment support
- Fraud escalation
- Omnichannel support

Alternative titles:

- Customer Service Representative
- Customer Support Specialist
- Customer Experience Agent
- Contact Centre Executive
- Call Centre Agent
- Live Chat Agent
- Email Support Specialist
- Helpdesk Agent
- Banking Customer Care Executive
- Escalation Specialist
- Mandarin Speaking Customer Support

Example Boolean string:

```text
("Customer Service Representative" OR "Customer Support Specialist" OR "Customer Experience Agent" OR "Contact Centre Executive" OR "Call Centre Agent" OR "Live Chat Agent") AND (CRM OR Zendesk OR Salesforce OR "complaint handling" OR SLA OR "live chat" OR "email support") AND (Mandarin OR Bahasa OR English)
```

## Candidate profile schema

| Field | Type | Description |
| --- | --- | --- |
| id | string | Candidate ID |
| roleId | string | Best matching pilot role |
| name | string | Demo candidate name |
| currentTitle | string | Current or most recent title |
| location | string | Candidate location |
| yearsExperience | number | Years of relevant experience |
| currentCompany | string | Demo current company |
| industryExperience | string[] | Domains evidenced in profile |
| skills | string[] | Evidenced skills |
| languages | string[] | Evidenced languages |
| currentSalary | string | Current monthly salary signal |
| expectedSalary | string | Expected monthly salary signal |
| availability | string | Availability or notice period signal |
| fitScore | number | Weighted score out of 100 |
| keyMatch | string | Top positive signal |
| mainRisk | string | Recruiter risk signal |
| evidenceNotes | string[] | Short evidence notes |
| scoreBreakdown | object | Six factor scores and evidence labels |

## Candidate fit scoring model

| Factor | Weight | Evidence rule |
| --- | ---: | --- |
| Must-have skill match | 35% | Count evidenced must-have skills against role requirements |
| Relevant experience | 25% | Match years of relevant experience to target range |
| Industry/domain match | 15% | Check domain evidence such as FinTech, banking, BPO, e-commerce, shared services |
| Seniority match | 10% | Match title level and scope to role seniority |
| Location/language fit | 10% | Match country and language signals |
| Compensation/availability signal | 5% | Compare salary expectation and availability/notice period |

Trust rule:

```text
If evidence is missing, mark it as Not evidenced. Do not infer unsupported claims.
```

## Candidate seed rows

| Candidate | Target role | Fit score | Key match | Main risk | Evidence highlights |
| --- | --- | ---: | --- | --- | --- |
| Chen Wei Ming | DevOps Engineer | 92% | Kubernetes, AWS, CI/CD | Moderate salary risk | AWS, Kubernetes, Terraform, Docker, Linux, Mandarin, FinTech deployment evidence |
| Amir Hakim | DevOps Engineer | 86% | Terraform, Docker, Linux | Mandarin not evidenced | Banking infrastructure and CI/CD evidence |
| Li Xiu Wen | DevOps Engineer | 83% | SRE, observability, AWS | Availability risk | SRE and platform operations evidence |
| Priya Nair | Finance Manager | 89% | SAP, reconciliation, reporting | Notice period risk | Full set accounting, SAP, GL, reporting, audit background |
| Wong Mei Lin | Finance Manager | 84% | FP&A, Power BI, budgeting | SAP depth not evidenced | Commercial finance and stakeholder reporting evidence |
| Daniel Tan | Finance Manager | 80% | Shared services, AP/AR, month-end | Mandarin not evidenced | AP, AR, GL, month-end closing evidence |
| Nurul Aina | Customer Service Representative | 91% | Mandarin, CRM, complaint handling | High competing demand | Mandarin, English, Bahasa Malaysia, Zendesk, SLA evidence |
| Jason Lim | Customer Service Representative | 86% | Live chat, e-commerce, escalation | Salary expectation risk | Live chat, CRM, marketplace support evidence |
| Siti Farah | Customer Service Representative | 84% | Banking support, KYC, call handling | Shift preference risk | Banking call centre, KYC, SLA, complaint handling evidence |

## Example candidate score breakdown

```json
{
  "candidateId": "cand-devops-001",
  "name": "Chen Wei Ming",
  "roleId": "devops-engineer",
  "fitScore": 92,
  "breakdown": [
    {
      "factor": "Must-have skill match",
      "weight": 35,
      "score": 33,
      "evidence": "AWS, Kubernetes, Docker, Terraform, CI/CD and Linux evidenced."
    },
    {
      "factor": "Relevant experience",
      "weight": 25,
      "score": 23,
      "evidence": "7 years relevant DevOps and platform engineering experience."
    },
    {
      "factor": "Industry/domain match",
      "weight": 15,
      "score": 14,
      "evidence": "FinTech and payments platform experience evidenced."
    },
    {
      "factor": "Seniority match",
      "weight": 10,
      "score": 9,
      "evidence": "Senior individual contributor scope matches role."
    },
    {
      "factor": "Location/language fit",
      "weight": 10,
      "score": 9,
      "evidence": "Malaysia-based and Mandarin evidenced."
    },
    {
      "factor": "Compensation/availability signal",
      "weight": 5,
      "score": 4,
      "evidence": "Expected salary is slightly above target midpoint."
    }
  ]
}
```

## Talent pool schema

| Field | Type | Description |
| --- | --- | --- |
| id | string | Pool item ID |
| candidateId | string | Linked candidate |
| roleId | string | Selected role |
| status | string | Pipeline status |
| source | string | Referral, upload, imported sample, or demo dataset |
| owner | string | Recruiter owner |
| nextAction | string | Next follow-up action |
| lastUpdated | string | Demo date label such as Today or Yesterday |
| notes | string | Recruiter notes |

Status values:

- New
- Reviewed
- Contacted
- Shortlisted
- HM Review
- Interviewing
- Offer
- Nurture
- Rejected

Sidebar summary:

```text
43 candidates in your referral pool
```

## Overview report schema

| Field | Type | Description |
| --- | --- | --- |
| roleId | string | Pilot role ID |
| executiveSummary | string | Short market summary |
| marketSnapshot | object | Companies mapped, employees, open roles, median salary, difficulty |
| salaryInsights | string[] | Salary commentary |
| competitorDemand | string[] | Hiring competitor signals |
| sourcingTargets | string[] | Best target company clusters |
| candidatePool | object | Available candidates, match rate, risk indicators |
| recommendedActions | string[] | Recruiter next steps |
| complianceNote | string | Approved sample data/human review note |

## Data consistency rules

- Use one `roleId` across all datasets.
- Do not duplicate role labels manually when an ID can join data.
- Use normalized numeric salary fields for sorting, but display friendly salary ranges.
- Keep candidate fit scores aligned with the score breakdown.
- Keep Dashboard, Market Mapping, Competitor Intel, Candidate Discovery, Talent Pool, and Overview Report in sync when switching roles.
- Keep all data realistic but clearly marked as demo/sample data.
