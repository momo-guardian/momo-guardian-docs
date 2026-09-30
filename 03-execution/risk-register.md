# Project Risk Register

| # | Risk | Likelihood | Impact | Mitigation | Owner |
|---|---|---|---|---|---|
| 1 | Scope creep (building a wallet, ML, USSD) | High | High | MVP scope doc; feature freeze; "roadmap" slide for extras | Lead |
| 2 | Frontend/API contract drift | Med | High | Contract-first PRs; mocks; integration smoke test | Leads |
| 3 | Live demo fails | Med | Critical | Backup video; local fallback; `mocks/`; rehearse | QA |
| 4 | Risk scoring produces weird results | Med | High | Unit tests per signal; calibration script; deterministic seeds | Data |
| 5 | Judges question realism of data | High | Med | Be upfront: synthetic data; show methodology & metrics; roadmap to real data partnership | Pitch |
| 6 | Team availability gaps | Med | Med | Clear ownership; backups per role; docs over memory | Lead |
| 7 | Hosting/free-tier outage | Low | High | Deploy early; local Docker fallback | QA |
| 8 | Name/trademark confusion with MTN MoMo | Med | Med | Distinct visual identity; "independent security layer" wording; check hackathon branding rules | Brand |
| 9 | Late submission / format mismatch | Low | Critical | Submit early; checklist §8 | Pitch |
