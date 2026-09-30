# Risk Scoring Specification (MVP: transparent rules + weights)

## Formula
```
base_score = Σ (weight_i × signal_i) × 100        # weights sum to 1.0, signals 0..1
adjusted   = base_score + interaction_bonus + answer_adjustment
score      = clamp(round(adjusted), 0, 100)
```

## Initial weights (tune with simulator data)
| Signal | Weight |
|---|---|
| new_recipient | 0.22 |
| amount_deviation | 0.26 |
| velocity | 0.10 |
| time_anomaly | 0.06 |
| device_change | 0.14 |
| recipient_reported | 0.12 |
| balance_drain | 0.06 |
| amount_round_high | 0.04 |

## Interaction bonuses (context combos are more telling than single signals)
- `new_recipient` ∧ `amount_deviation ≥ 0.7` → +15
- `device_change` ∧ `new_recipient` ∧ high amount → +15
- `inbound_then_out` ∧ `new_recipient` → +10

## Answer adjustments
| Answer | Adjustment |
|---|---|
| Don't know recipient (and amount high) | +20 |
| Contacted by someone asking for money | +15 |
| Being rushed | +15 |
| Promised reward/job/loan | +20 |
| Told to keep secret | +20 |
| Claimed official | +15 |
| All "safe" answers + known contact | −10 (never below 0; never lowers a `recipient_reported` case below Medium) |

## Levels & actions
| Score | Level | Action |
|---|---|---|
| 0–29 | Low | `allow` — silent ✓ badge |
| 30–59 | Medium | `warn` — reasons + confirm |
| 60–79 | High | `challenge` — questions, then `step_up` if still ≥ 60 |
| 80–100 | Critical | `step_up` + `hold` option (cooldown/trusted contact) |

## Explainability contract
Every response returns the **top 3 contributing signals** sorted by points contributed, each with a
reason string and `points`. The UI must render reasons exactly as returned (no hidden scoring).

## Calibration plan
1. Use simulator to generate ≥ 500 legitimate and ≥ 100 scam transactions.
2. Track false-positive rate (legit flagged ≥ Medium) — target < 5%; scam catch rate (≥ High) — target > 85%.
3. Report these numbers in the pitch (labelled as synthetic-data results).

## Roadmap beyond MVP
Replace/augment weights with a trained model (e.g., gradient boosting) while keeping the explanation layer (SHAP-style contributions).
