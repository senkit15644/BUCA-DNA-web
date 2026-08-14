# Software Architecture Document

## D Codescape of BUCA

**Document status:** Proposed Architecture v0.1\
**Architecture principle:** Production-oriented, maintainable,
GitHub-friendly, VS Code-friendly, Vercel-compatible

------------------------------------------------------------------------

## 1. Architecture Decision

### Recommended Stack

### Frontend

-   Next.js
-   React
-   TypeScript
-   Tailwind CSS
-   Framer Motion

### Backend

-   Python
-   FastAPI

### Database

-   PostgreSQL-compatible database

### Repository

-   GitHub

### Development IDE

-   VS Code

### Deployment

-   Vercel

### Analytics

-   GA4
-   Microsoft Clarity

------------------------------------------------------------------------

## 2. Why This Architecture

ผู้ใช้ต้องการ Python และ Vercel พร้อม Workflow ผ่าน VS Code/GitHub

จึงแยกหน้าที่:

``` text
Browser
   |
   v
Next.js / React / TypeScript
   |
   | HTTPS API
   v
FastAPI / Python
   |
   v
PostgreSQL
```

Next.js เหมาะกับ UX/UI และ browser-side interaction

Python ใช้เป็น backend/API สำหรับ: - scoring - quiz state validation -
result generation - analytics events ที่จำเป็น - database access

ไม่ใช้ Python เป็นภาษาหลักในการสร้าง UI ใน browser

Vercel รองรับ FastAPI/Python deployment และ Git-based deployment
จึงสอดคล้องกับข้อกำหนด Vercel + GitHub

------------------------------------------------------------------------

## 3. Repository Structure

Proposed:

``` text
d-codescape-buca/
│
├── app/
│   ├── page.tsx
│   ├── start/
│   ├── quiz/
│   ├── loading/
│   ├── result/
│   ├── career/
│   ├── role/
│   ├── about/
│   └── contact/
│
├── components/
│   ├── ui/
│   ├── quiz/
│   ├── result/
│   ├── navigation/
│   └── mascot/
│
├── public/
│   ├── characters/
│   ├── icons/
│   └── assets/
│
├── lib/
│   ├── api/
│   ├── analytics/
│   └── validation/
│
├── types/
│
├── styles/
│
├── api/
│   └── main.py
│
├── backend/
│   ├── scoring/
│   ├── models/
│   ├── schemas/
│   ├── services/
│   └── repositories/
│
├── tests/
│   ├── frontend/
│   └── backend/
│
├── docs/
│
├── package.json
├── pyproject.toml
├── .env.example
└── README.md
```

**Note:** Folder naming is an engineering proposal, not a user-provided
requirement.

------------------------------------------------------------------------

## 4. Frontend Responsibilities

Frontend handles: - rendering - navigation - quiz UI - answer state -
progress - animations - result visualization - download UI - responsive
layout - accessibility - analytics client events

Frontend MUST NOT own the authoritative scoring algorithm.

------------------------------------------------------------------------

## 5. Backend Responsibilities

FastAPI handles: - scoring - validating submitted answers - retrieving
quiz configuration - generating result payload - persisting test
sessions - aggregating anonymous usage data - validating role result -
future administrative endpoints

------------------------------------------------------------------------

## 6. Assessment Engine

Input:

``` text
10 answers
```

Processing:

``` text
RIASEC component = 80%
Big Five component = 20%
             |
             v
     Role Mapping
             |
             v
4 Role Scores
             |
             v
Ranking
```

Important: The exact mathematical formula is **NOT defined yet**.

Do not implement a formula until: - item matrix exists - answer scale
exists - weights exist - role mapping is approved

------------------------------------------------------------------------

## 7. Proposed Data Model

### quiz_sessions

-   id
-   anonymous_user_id
-   started_at
-   completed_at
-   status

### quiz_answers

-   session_id
-   question_id
-   answer_value
-   answered_at

### quiz_results

-   session_id
-   role_communicator
-   role_planner
-   role_designer
-   role_producer
-   primary_role
-   result_version
-   created_at

### analytics_summary

-   date
-   starts
-   completions
-   completion_rate
-   role_distribution

### question_config

-   question_id
-   order_index
-   active
-   version

Exact fields remain subject to implementation review.

------------------------------------------------------------------------

## 8. Guest Identity

Because Login = Guest:

Recommended engineering pattern: - generate anonymous identifier - store
no unnecessary identity - use server-side session reference - separate
analytics identity from assessment identity where possible

This is a proposed technical approach and must be aligned with
privacy/consent requirements before production.

------------------------------------------------------------------------

## 9. Analytics Architecture

GA4: - page_view - quiz_start - question_answer - quiz_back -
quiz_complete - result_view - result_download - share_click -
career_view - role_view

Clarity: - session recording - heatmap - rage click analysis

Do not send: - raw sensitive user data - unnecessary answer text -
personal identifiers

------------------------------------------------------------------------

## 10. API Boundary

Proposed endpoints:

``` text
GET  /api/quiz
POST /api/quiz/session
PUT  /api/quiz/session/{id}/answer
POST /api/quiz/session/{id}/complete
GET  /api/result/{id}
GET  /api/career
GET  /api/role/{role_id}
POST /api/analytics/event
```

These are proposals only.

------------------------------------------------------------------------

## 11. Download Result Architecture

Preferred initial implementation: - render a deterministic result
template - populate result data - generate downloadable image - ensure
fonts/assets are available - test Thai/English rendering - test mobile
and desktop

Exact library is NOT selected yet.

------------------------------------------------------------------------

## 12. Performance Strategy

Target traffic context: **\>2,000 users/day**

Do not dimension infrastructure from daily users alone.

Measure: - concurrent users - requests/second - response time - database
latency - function duration - asset size - image generation cost - error
rate

Baseline testing: 1. local functional test 2. preview deployment test 3.
load test 4. stress test 5. result-download test 6. mobile network test

Then tune: - caching - DB indexes - payload size - image assets - API
execution - client bundle - animation cost

------------------------------------------------------------------------

## 13. GitHub Workflow

Branches:

``` text
main
develop
feature/*
fix/*
```

Example:

``` text
feature/quiz-navigation
feature/result-download
fix/mobile-result
```

Commit convention:

``` text
feat:
fix:
refactor:
style:
docs:
test:
chore:
```

Pull Request must include: - summary - files changed - test result -
screenshots when UI changed - known issues

------------------------------------------------------------------------

## 14. VS Code Workflow

``` text
Claude
  ↓
Review requirement
  ↓
Generate limited code
  ↓
VS Code
  ↓
Run locally
  ↓
Test
  ↓
Read error
  ↓
Claude analyzes
  ↓
Fix
  ↓
Test again
  ↓
Git commit
  ↓
GitHub
```

Claude MUST NOT overwrite unrelated files.

------------------------------------------------------------------------

## 15. Environment Variables

Never commit secrets.

Use:

``` text
.env.local
```

Examples of secret/config categories: - database URL - analytics IDs
where applicable - API secrets - deployment secrets

Commit only:

``` text
.env.example
```

with placeholder values.

------------------------------------------------------------------------

## 16. Testing Layers

### Unit

Scoring functions Validation Utility functions

### Integration

API + database Quiz submission Result generation

### E2E

Landing → Start → 10 Questions → Result → Download

### Accessibility

Keyboard Focus Semantic structure

### Performance

Mobile Slow network Concurrent load

------------------------------------------------------------------------

## 17. Security

Minimum: - validate all input - server-side scoring - rate limiting
strategy - no secrets in client bundle - parameterized DB access - safe
file generation - sanitize share/download inputs - analytics privacy
controls

------------------------------------------------------------------------

## 18. Architecture Risks

### Risk 1

10 questions may not provide enough measurement depth for a robust
psychometric assessment.

Mitigation: Position as a guideline and validate items before claiming
accuracy.

### Risk 2

Custom 4-role mapping can accidentally be presented as if RIASEC/Big
Five directly defines BUCA roles.

Mitigation: Keep scoring model and BUCA career mapping as separate
layers.

### Risk 3

Guest tracking can conflict with privacy expectations.

Mitigation: Define consent, retention, anonymous identity, and deletion
policy before production.

### Risk 4

Result image generation can become expensive if done synchronously for
every request.

Mitigation: Benchmark first; cache deterministic outputs where safe.

------------------------------------------------------------------------

## 19. Architecture Open Questions

1.  Which PostgreSQL provider?
2.  Is Supabase permitted?
3.  Should scoring configuration be stored in DB or version-controlled
    JSON?
4.  Is there an admin panel?
5.  Who can edit questions?
6.  Who can publish a new assessment version?
7.  Should result URLs be shareable?
8.  Should results be persisted indefinitely?
9.  Exact download format?
10. Required concurrent-user target for load testing?
