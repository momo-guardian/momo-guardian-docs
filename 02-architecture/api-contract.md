# API Contract v1 (draft — change via PR to this file first)

Base URL (dev): `http://localhost:8000` · Prefix: `/v1` · JSON · Auth: header `X-API-Key` (static demo key).
Amounts are in GHS as decimals. Timestamps ISO-8601 UTC. Phone numbers are synthetic, E.164 (`+233…`).

## 1. Assess a transaction
`POST /v1/transactions/assess`

Request
```json
{
  "sender_id": "usr_001",
  "recipient_number": "+233240000999",
  "amount": 2000.00,
  "currency": "GHS",
  "device_id": "dev_new_77",
  "timestamp": "2026-10-01T14:05:00Z",
  "channel": "app"
}
```
Response `200`
```json
{
  "assessment_id": "asm_9f2c",
  "risk_score": 82,
  "risk_level": "critical",
  "recommended_action": "step_up",
  "reasons": [
    {"code": "amount_deviation", "points": 28, "message": "This is 40× your usual amount."},
    {"code": "new_recipient", "points": 22, "message": "You've never sent money to this number before."},
    {"code": "device_change", "points": 14, "message": "This payment is from a new device."}
  ],
  "questions": [
    {"id": "q_know", "text": "Do you know this person in real life?", "options": ["yes","no","not_sure"]},
    {"id": "q_contacted", "text": "Did someone contact you asking you to send this money?", "options": ["yes","no"]}
  ],
  "step_up": {"methods": ["cooldown","reconfirm","recipient_confirm","trusted_contact"], "cooldown_seconds": 60},
  "created_at": "2026-10-01T14:05:00Z"
}
```

## 2. Submit answers
`POST /v1/assessments/{assessment_id}/answers`
```json
{"answers": [{"question_id": "q_know", "value": "no"}, {"question_id": "q_contacted", "value": "yes"}]}
```
Response: same shape as assess, with updated `risk_score`, `reasons` (answer-based reasons added) and `recommended_action`.

## 3. Record outcome
`POST /v1/assessments/{assessment_id}/outcome`
```json
{"outcome": "cancelled"}   // proceeded | cancelled | held
```
Response `200`: `{"assessment_id":"asm_9f2c","outcome":"cancelled","loss_prevented":2000.00}`

## 4. Supporting endpoints (demo)
| Method | Path | Purpose |
|---|---|---|
| GET | `/v1/users/{id}/profile` | Behavior summary (typical amount, known recipients count, usual hours) |
| GET | `/v1/users/{id}/transactions` | History with risk tags (dashboard) |
| GET | `/v1/scenarios` | List scam scenarios (from simulator seeds) |
| POST | `/v1/scenarios/{id}/run` | Load scenario state & return the pending transaction to assess |
| GET | `/v1/stats` | Totals: assessed, flagged, prevented GHS |
| GET | `/health` | Liveness |

## Errors
```json
{"error": {"code": "validation_error", "message": "amount must be > 0", "details": []}}
```
Codes: `validation_error` (422), `unauthorized` (401), `not_found` (404), `internal_error` (500).

## Enums
- `risk_level`: `low | medium | high | critical`
- `recommended_action`: `allow | warn | challenge | step_up | hold`
- `outcome`: `proceeded | cancelled | held`
