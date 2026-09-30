# Data Model (MVP)

| Table | Key fields |
|---|---|
| `users` | id, name, phone, balance, created_at |
| `user_profiles` | user_id, median_amount, p95_amount, typical_hours (json), avg_daily_txn_count, updated_at |
| `contacts` (known recipients) | user_id, recipient_number, first_paid_at, txn_count |
| `devices` | id, user_id, first_seen_at, last_seen_at, trusted (bool) |
| `transactions` | id, sender_id, recipient_number, amount, status, device_id, created_at, is_scam_label (sim only) |
| `assessments` | id, transaction_ref, risk_score, risk_level, recommended_action, reasons (json), answers (json), outcome, loss_prevented, created_at |
| `reported_numbers` | number, report_count, last_reported_at, category |
| `scenarios` | id, name, description, user_id, pending_txn (json), scripted_answers (json), expected_outcome |

Notes: `is_scam_label` exists **only** in simulator data for evaluation; never read by the scoring engine.
Profiles are derived from `transactions`; recompute on seed.
