# System Architecture

```
┌──────────────────────┐        ┌───────────────────────────┐
│ momo-guardian-       │  REST  │ momo-guardian-api         │
│ frontend (demo app)  │───────▶│  ├─ api/v1 routes         │
│  - Send money        │◀───────│  ├─ services (profiles,   │
│  - Safety Check      │  JSON  │  │   transactions)        │
│  - Step-up           │        │  └─ risk_engine           │
│  - Scam Simulator    │        │      signals → scoring →  │
└──────────────────────┘        │      explain → questions →│
                                │      stepup/policies      │
┌──────────────────────┐        └──────────┬────────────────┘
│ Partner systems      │  REST (same API)  │
│ (fintech/bank/       │───────────────────┤
│  merchant) — future  │                   ▼
└──────────────────────┘        ┌───────────────────────────┐
                                │ DB (SQLite → Postgres)    │
┌──────────────────────┐ seeds  │ users, contacts, txns,    │
│ momo-guardian-       │───────▶│ devices, reported_numbers │
│ simulator            │        └───────────────────────────┘
└──────────────────────┘
```

## Components
- **Frontend** — presentation only. Holds no risk logic. Calls API.
- **API** — stateless HTTP layer + risk engine. All scoring logic lives here.
- **Risk engine** — pure, unit-testable functions: `signals/` → `scoring/` → `explain/`; plus `questions/`, `stepup/`, `policies/` (thresholds & weights in config).
- **Simulator** — generates/loads synthetic users, histories, scam scenarios; can replay scenarios against the API.
- **DB** — SQLite for the hackathon (zero setup); schema compatible with Postgres.

## Request lifecycle (assess)
1. Client → `POST /v1/transactions/assess` with sender, recipient, amount, device, timestamp.
2. API loads sender profile (history aggregates, known recipients, devices).
3. Engine computes signals → score → level → reasons → recommended action (+ questions if needed).
4. API returns assessment; stores it.
5. If questions were needed: client → `POST /v1/assessments/{id}/answers` → recalculated result.
6. Client → `POST /v1/assessments/{id}/outcome` (proceeded / cancelled / held).

## Non-functional targets
- Assess latency < 300 ms (local).
- Deterministic: same input → same score (important for demo reliability).
- Config-driven weights/thresholds (no redeploy to tune).
- Demo resilience: frontend has a `mocks/` fallback if the API is unreachable.
