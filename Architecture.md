# Architecture

## MVP architecture

HyIntel AI is a local-first React/Vite web application using mock seed data only.

## Layers

- UI layer: React pages and reusable dashboard components
- State layer: selected role, country, industry, filters, candidate status
- Data layer: local TypeScript/JSON seed data
- Logic layer: deterministic scoring, filtering, sorting, report generation
- No backend for MVP
- No external APIs
- No scraping

## Data flow

1. User selects role.
2. App loads matching local seed data.
3. Pages render role-specific dashboard metrics, market data, competitors, candidates, and report content.
4. Candidate score breakdown is calculated or loaded from local evidence fields.
5. Talent Pool status changes are stored locally in component state or browser storage.

## Role switching

Changing role must update:

- Dashboard
- Market Mapping
- Competitor Intel
- Candidate Discovery
- Talent Pool
- Overview Report

## Non-goals

- Production backend
- Authentication
- Live scraping
- Real LinkedIn, JobStreet, Indeed, or external recruitment integration
