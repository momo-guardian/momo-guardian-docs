# Q&A Prep

**Is this just a rule-based system?** For the MVP yes — deliberately: explainable, deterministic, no real labeled data. The explanation layer is model-agnostic; ML is the roadmap once we have real data.

**Where did your data come from?** Synthetic, generated from realistic behavior profiles and known scam patterns. We report false-positive and catch rates on it and are upfront about that limitation.

**Won't this annoy legitimate users?** Friction is proportional: Low-risk payments see nothing more than a ✓. Target false-positive rate < 5% (measured on synthetic data).

**What if the scammer coaches the victim to answer "no"?** Questions are one signal among many; the behavioral signals alone can still trigger step-up. Step-up includes cooldown and trusted-contact approval that break the scammer's urgency.

**How would this integrate with MoMo?** Via API call before payment confirmation (pre-authorization hook) — one request, sub-second response, partner controls the UX.

**Privacy?** Minimal data (amounts, timestamps, recipient identifiers, device IDs); processing in partner's environment possible; compliance with Ghana data protection law to be validated **[ASSUMPTION]**.

**Business model?** Per-assessment API pricing / SaaS tier for fintechs & merchants; value = fraud losses avoided + reduced support/dispute costs.

**What's the moat?** UX + speed to integrate + explainability; long-term, shared scam intelligence across platforms.

**Why not just block large payments?** Blunt limits harm legit users and scammers adapt; context-aware scoring protects without blanket friction.

**What would you do with more time?** Real-data pilot, trained model with explanations, USSD/SMS channel, local languages, trusted-contact notifications, consortium scam-number sharing.
