# MVP Scope

## In scope (must ship)
| # | Capability | Repo |
|---|---|---|
| 1 | Simulated users with transaction history & behavior profiles | simulator |
| 2 | Send-money flow (mock wallet, no real money) | frontend |
| 3 | Risk assessment endpoint returning score, level, reasons, recommended action | api |
| 4 | Signals: new recipient, amount deviation, frequency/velocity, time-of-day, device change | api |
| 5 | Plain-language explanation of each reason | api + frontend |
| 6 | Smart questions (3–5) that adjust the score based on answers | api + frontend |
| 7 | Step-up verification (cooldown + re-confirmation + trusted-contact simulation) | both |
| 8 | Scam Simulator panel: one-click scenarios for the live demo | frontend + simulator |
| 9 | Fraud Prevention API docs page (OpenAPI) | api |

## Should have (if time)
- Activity dashboard: transactions with risk tags, prevented-loss counter.
- Recipient "reputation" (simulated community-reported numbers).
- Risk score timeline visual.

## Out of scope (say so in the pitch as roadmap)
- Real MTN MoMo integration or real money movement.
- ML model training on real data (MVP uses transparent rules + weights; ML = roadmap).
- USSD / SMS channel, multi-language, trusted-contact live notifications.
- Consent/regulatory workflows beyond a documented note.

## Demo must-haves
1. Normal payment → passes silently (proves low friction).
2. Scam payment → intercepted with explanation → questions → step-up → user cancels (proves value).
3. API call shown live (curl/Postman/Swagger) → same result (proves infrastructure).
