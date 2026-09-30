# Project Brief

**Name:** MoMo Guardian
**Event:** MTN FinTech Hackathon
**One-liner:** A security layer that helps protect mobile-money users *before* they send money.
**Pitch line:** "We don't want to replace mobile money. We want to make every mobile-money transaction safer."

## What we are
- A behavioral risk layer around digital payments (consumer experience + Fraud Prevention API).

## What we are NOT
- Not a new wallet. Not a payments processor. Not a replacement for MoMo.
- Not a blocker by default — we warn, ask, and step up only when risk justifies it.

## Prototype promise (hackathon)
A working end-to-end demo that can:
1. Simulate users and transactions.
2. Learn a user's normal behavior (profile).
3. Calculate a **risk score** for a pending transaction.
4. **Explain** in plain language why it looks suspicious.
5. Ask **smart questions** to detect manipulation.
6. Trigger **step-up verification** when risk is high.
7. Show the same engine exposed as a **Fraud Prevention API**.

## Success criteria
- A judge understands the problem in 30 seconds and the solution in 2 minutes.
- Live demo runs a legitimate payment (frictionless) and a scam payment (intercepted) back-to-back.
- Clear story for how this scales from app → API → infrastructure.
