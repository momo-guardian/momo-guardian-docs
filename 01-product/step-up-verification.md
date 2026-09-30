# Step-up Verification

Triggered when level ≥ High (after questions). Methods are **additive** by risk.

| Method | Risk | Description | Prototype behavior |
|---|---|---|---|
| Cooldown | High | 60-second pause with a "Talk to someone you trust first" message | Countdown timer |
| Re-confirm details | High | Re-type recipient number & amount (defeats copy-paste-under-pressure) | Validated input |
| Recipient confirmation | High | Show recipient's registered name (simulated name lookup) and ask "Is this who you mean?" | Mock name lookup |
| Trusted-contact approval | Critical | Notify a pre-set trusted contact who must approve | Simulated approve/deny button |
| Hold for review | Critical | Payment queued 30 min with cancel option | Simulated queue |

## Principles
- Never a dead end: user can cancel at any time.
- Language is calm and non-accusatory. Example: "Let's take a moment to double-check this payment."
- Log outcomes (proceeded/cancelled/held) for the dashboard's "prevented" metric.
