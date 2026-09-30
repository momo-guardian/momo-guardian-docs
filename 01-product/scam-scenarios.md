# Scam Scenarios (for simulator & demo)

Scenarios reflect widely-reported mobile-money scam patterns. **[ASSUMPTION]** Validate & cite local
sources in `06-research/` before presenting as statistics.

| ID | Scenario | How the victim is manipulated | Signals Guardian sees |
|---|---|---|---|
| S1 | **Fake agent / "account blocked"** | Caller claims to be from the provider; demands payment to "unlock" | New recipient, large amount, urgency (answers) |
| S2 | **Wrong-number refund** | "I sent you money by mistake, send it back" | New recipient, round amount, inbound-then-outbound pattern |
| S3 | **Fake job/registration fee** | Pay a fee to secure a job/loan | New recipient, amount ≫ usual, "promised something?" = yes |
| S4 | **Prize/promo scam** | Pay a "processing fee" to claim a prize | New recipient, unusual amount, "promised reward?" = yes |
| S5 | **Family impersonation** | "Hi, it's your son, new number, need money now" | Recipient unknown, urgency, off-hours |
| S6 | **Fake buyer/seller** | Overpay/"advance payment" for goods | New recipient, rapid repeat sends |
| S7 | **Investment / doubling** | "Send 500, get 1,000" | Large amount, new recipient, "asked to keep secret?" = yes |
| S8 | **SIM-swap / new device** | Attacker on new device drains wallet | Device change + large amount + new recipient |

## Demo picks (3)
- **S1** (most recognisable), **S2** (relatable), **S8** (shows device signal & API value).

## Scenario file format (simulator)
Each scenario = user profile + pending transaction + scripted answers + expected outcome. See simulator repo docs.
