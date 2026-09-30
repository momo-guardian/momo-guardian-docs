# Risk Signals

Each signal returns a value 0.0–1.0 (strength) and a human-readable reason.

| Signal | Definition | Example reason shown to user |
|---|---|---|
| `new_recipient` | Recipient never paid by this user (or first seen < N days) | "You've never sent money to this number before." |
| `amount_deviation` | Amount vs user's median/95th percentile (z-score or ratio) | "This is 40× your usual amount." |
| `amount_round_high` | Round, high-value amount (e.g., 500, 1000, 2000) | "Scammers often ask for round amounts." |
| `velocity` | Count/value of sends in last 1h/24h vs norm | "3 payments in 10 minutes is unusual." |
| `time_anomaly` | Outside user's typical hours | "You don't usually send money at this hour." |
| `device_change` | New/unrecognized device or recent SIM/device change | "This payment is from a new device." |
| `recipient_reported` | Recipient flagged in (simulated) scam-report list | "This number has been reported by others." |
| `balance_drain` | Amount is large % of balance | "This would empty 90% of your wallet." |
| `inbound_then_out` | Recently received funds then immediate send to a stranger | "Funds arrived minutes ago and are being sent on." |
| `answer_*` | Answers to smart questions (see below) | "You said someone is pressuring you." |

## Smart questions (bank of 6; show 3–5 by context)
1. Do you know this person in real life? (Yes / No / Not sure)
2. Did someone contact you (call/SMS/WhatsApp) asking you to send this money? (Y/N)
3. Are you being rushed or told to act immediately? (Y/N)
4. Were you promised money, a prize, a job or a loan in return? (Y/N)
5. Were you told to keep this payment secret or not tell family? (Y/N)
6. Did anyone claim to be from MTN, a bank, or an official office? (Y/N)

Answer effects: risk-increasing answers add points; "No" to *know this person* on a high-amount payment adds a big bump.
