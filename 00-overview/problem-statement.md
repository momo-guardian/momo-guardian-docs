# Problem Statement

Mobile-money users can be manipulated into **authorizing legitimate transactions** through scams, social
engineering, fake urgency, or unfamiliar payment requests. Existing security measures (PIN, OTP, post-hoc
fraud monitoring) verify *who* is paying, not *why*. The transaction is technically valid, so it passes.

## Why existing controls miss it
| Control | Gap |
|---|---|
| PIN / OTP | Victim enters it willingly |
| Post-transaction fraud detection | Money has already moved; recovery is slow/low-probability |
| Static limits | Blunt; hurt legit users, easy for scammers to work within |
| Generic warning banners | Ignored; no context about *this* user or *this* payment |

## Impact
- Direct financial loss, often for low-income individuals and small businesses.
- Erosion of trust in digital payments, slowing adoption.
- Support, dispute and reputational cost for providers.

## Core insight
The strongest signal of a scam is **context**: a deviation from the user's own normal behavior at the moment of payment.

> Normal: GHS 20–50 to known contacts. Now: GHS 2,000 to a never-seen number. → Interrupt, explain, verify.

## Evidence to gather (see 06-research)
- Ghana/Africa mobile-money fraud statistics and typical scam types (cite sources).
- Industry terminology: *authorized push payment (APP) fraud*, *social engineering fraud*.
