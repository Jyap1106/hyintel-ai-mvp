# Candidate Scoring Model

## Purpose

The score helps recruiters prioritize candidates. It does not make hiring decisions.

## Weighted model

| Factor | Weight |
|---|---:|
| Must-have skill match | 35% |
| Relevant experience | 25% |
| Industry/domain match | 15% |
| Seniority match | 10% |
| Location/language fit | 10% |
| Compensation/availability signal | 5% |

## Trust rule

If evidence is missing, display:

`Not evidenced`

Do not infer unsupported claims.

## Example score

Candidate: Chen Wei Ming  
Role: DevOps Engineer  
Final score: 92%

| Factor | Weight | Score | Evidence |
|---|---:|---:|---|
| Must-have skill match | 35 | 33 | AWS, Kubernetes, Docker, Terraform, CI/CD, Linux evidenced |
| Relevant experience | 25 | 23 | 7 years DevOps/platform experience |
| Industry/domain match | 15 | 14 | FinTech/payments experience evidenced |
| Seniority match | 10 | 9 | Senior IC scope matches role |
| Location/language fit | 10 | 9 | Malaysia-based, Mandarin evidenced |
| Compensation/availability signal | 5 | 4 | Expected salary slightly above midpoint |

## UI requirements

Every candidate detail view must show:

- Final fit score
- Six scoring factors
- Weight per factor
- Evidence per factor
- Missing evidence labels
- Human review required label
