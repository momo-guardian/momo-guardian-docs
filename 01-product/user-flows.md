# User Flows

## Flow A — Low risk (frictionless)
Enter recipient & amount → Guardian scores (<30) → small "✓ Looks normal" badge → confirm → success.

## Flow B — Medium risk (warn)
Enter details → score 30–59 → **Safety Check card** with reasons → user taps *Continue* or *Cancel* →
optional quick questions → confirm.

## Flow C — High risk (challenge + step-up)
Enter details → score ≥ 60 → full-screen **Safety Check**:
1. "This transaction looks unusual." + reasons list.
2. Smart questions (yes/no/unsure).
3. Score recalculated with answers.
4. If still high → **Step-up**: 60-second cooldown, re-enter amount + recipient number, optional trusted-contact approval.
5. Outcomes: cancel (prevented) / proceed after verification / hold for review.

## Flow D — API integration
Partner calls `POST /v1/transactions/assess` → receives score, reasons, recommended action → partner decides UX.

## Screens (frontend)
1. Home / balance (mock)
2. Send money
3. Safety Check (warn / challenge)
4. Step-up verification
5. Result (sent / cancelled / held)
6. Activity dashboard
7. Scam Simulator (demo control panel)
