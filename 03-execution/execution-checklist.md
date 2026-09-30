# Execution Checklist

Tick as you go. Phase numbers match `execution-plan.md`.

## 0. Before anything (Phase 0)
- [ ] Get official hackathon brief: dates, theme, judging criteria, team size, submission format, tech/data rules
- [ ] Confirm whether MTN provides APIs/sandbox/datasets (update scope if so)
- [ ] Confirm team roster and roles (`team-roles.md`)
- [ ] Choose comms channel + standup time
- [ ] Decide final project name & check availability (GitHub org, domain, social handle)

## 1. GitHub & Repos (Phase 0)
- [ ] Create GitHub organization (e.g., `momo-guardian`)
- [ ] Create org `.github` repo → push `/.github` folder
- [ ] Create repos: `momo-guardian-docs`, `-frontend`, `-api`, `-simulator` → push each folder
- [ ] Enable branch protection on `main` (PR required, 1 approval, CI must pass) and create `dev`
- [ ] Add teammates with correct roles (Write; Admin only for leads)
- [ ] Create labels (see guide) and a GitHub Project board (Backlog/Ready/In progress/Review/Done)
- [ ] Add issue/PR templates (from `.github`) — verify they appear
- [ ] Pin the four repos on the org profile; add profile README

## 2. Documentation (Phase 0–1)
- [ ] All docs in this repo reviewed by the whole team
- [ ] Open questions logged as issues labeled `question`
- [ ] Contract v1 approved & frozen
- [ ] Risk scoring spec approved (weights, thresholds)
- [ ] Demo scenarios chosen (S1, S2, S8) with scripted expected outcomes
- [ ] Research notes populated with cited sources (`06-research/`)

## 3. Branding (Phase 0 → 5)
- [ ] Logo brief approved (`04-brand/logo-plan.md`)
- [ ] 3+ concepts sketched; 1 selected by vote
- [ ] Final logo set exported (primary, icon, mono, favicon, social)
- [ ] Color tokens & fonts added to frontend config
- [ ] Logo placed in every repo README + org profile

## 4. Frontend Repo (Phase 2 → 5)
- [ ] Project initialized per README (Phase 2)
- [ ] CI: lint + typecheck + test
- [ ] Send-money screen
- [ ] Safety Check (warn + challenge) UI
- [ ] Questions UI → answers endpoint
- [ ] Step-up UI (cooldown, re-confirm, recipient confirm, trusted-contact sim)
- [ ] Scam Simulator panel
- [ ] Activity dashboard
- [ ] Mock fallback for offline demo
- [ ] Mobile-first responsive + accessibility pass
- [ ] Deployed demo URL

## 5. API Repo (Phase 2 → 5)
- [ ] Project initialized; `/health` (Phase 2)
- [ ] CI: lint + tests
- [ ] `assess` (hardcoded → real)
- [ ] Signals implemented + unit tests: new_recipient, amount_deviation, velocity, time_anomaly, device_change, recipient_reported, balance_drain, amount_round_high
- [ ] Scoring + interaction bonuses + answer adjustments
- [ ] Explanation builder (top 3 reasons)
- [ ] `answers`, `outcome`, `profile`, `transactions`, `stats`, `scenarios` endpoints
- [ ] Config-driven weights/thresholds
- [ ] OpenAPI docs polished; example requests in README
- [ ] Deployed API URL + API key for demo

## 6. Simulator Repo (Phase 3)
- [ ] Synthetic users (10–20) with realistic behavior profiles
- [ ] Legit + scam transaction generators
- [ ] Scenario files for S1–S8 (3 demo-critical)
- [ ] Seed script loads DB
- [ ] Evaluation script prints FP rate & catch rate

## 7. Quality (Phase 5)
- [ ] Legit demo payment stays Low across all users
- [ ] Each demo scenario yields expected level & actions
- [ ] No secrets committed; only synthetic data
- [ ] README quick-start works on a clean machine (teammate test)
- [ ] Feature freeze declared

## 8. Pitch (Phase 6)
- [ ] Deck complete (`05-pitch/pitch-deck-outline.md`)
- [ ] Demo script rehearsed ≥ 3 times with timer
- [ ] Backup demo video recorded
- [ ] Offline/local fallback verified
- [ ] Q&A prep reviewed (`05-pitch/qna-prep.md`)
- [ ] Submission uploaded early; links verified in a private window
