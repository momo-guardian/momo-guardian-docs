# Solution — MoMo Guardian

A smart security layer that analyzes a pending transaction against the sender's behavior and context,
then responds proportionally.

## How it works (plain language)
1. **Observe** — new recipient? unusual amount? unusual time/frequency? new device? rapid repeat payments?
2. **Score** — combine signals into a 0–100 risk score.
3. **Explain** — show human-readable reasons ("New recipient", "10× your usual amount").
4. **Ask** — a few smart questions to detect manipulation ("Did someone call you claiming to be MTN?").
5. **Respond** — allow / warn / challenge / step-up / hold, based on risk.

## Design principles
- **Protect without blocking:** friction only where risk is real.
- **Explainable:** every decision shows reasons; no black box.
- **User in control:** the user can always proceed after a clear warning at low/medium risk.
- **Privacy-minded:** minimal data, synthetic data in the prototype.
- **Integrable:** same engine powers the app and the API.

## Two surfaces
- **Consumer layer:** in-flow Safety Check before payment confirmation.
- **Fraud Prevention API:** `POST /v1/transactions/assess` for fintechs, banks, merchants, payment platforms.
