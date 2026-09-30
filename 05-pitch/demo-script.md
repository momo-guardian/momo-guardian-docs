# Demo Script (≈ 2.5 min live)

**Setup before going on stage:** deployed URL open + local fallback running + backup video ready; user `Ama` selected; scenario panel visible.

| Time | Action | Say |
|---|---|---|
| 0:00 | **Normal payment:** Ama sends GHS 30 to a known contact | "Ama sends money the way she always does. Guardian stays out of the way — a small ✓, done." |
| 0:30 | **Scam S1:** Run scenario "Fake agent — account blocked": GHS 2,000 to a new number | "Now someone calls pretending to be from the provider. Ama is about to send GHS 2,000." |
| 0:45 | Safety Check appears: score, reasons | "Guardian interrupts: new recipient, 40× her usual amount, new device. It explains *why*." |
| 1:10 | Answer questions: *contacted by someone? yes · rushed? yes · know them? no* | "Instead of just blocking, it asks a few smart questions. The risk goes up." |
| 1:30 | Step-up: cooldown + re-confirm + recipient name | "Stronger verification — only now, only for this payment." |
| 1:50 | Ama **cancels** → dashboard shows "GHS 2,000 prevented" | "Money saved. No new wallet. No behavior change." |
| 2:05 | **API moment:** Swagger/curl `POST /v1/transactions/assess` | "The same engine is a Fraud Prevention API any fintech, bank or merchant can call." |
| 2:30 | Close | Pitch line. |

## Rules
- Scripted scenarios are deterministic — same result every time.
- If anything breaks: switch to the backup video within 5 seconds, no apologies.
- Roles: one driver (hands), one speaker (voice).
