# Execution Plan (A → Z)

> Dates are **relative** because the official hackathon timeline isn't in our docs yet.
> **First action:** get the real dates, then map phases onto them (see `execution-checklist.md` §0).

## Phase overview
| Phase | Name | Outcome |
|---|---|---|
| 0 | Kickoff & Foundations | Team aligned, GitHub org + repos live, stack confirmed |
| 1 | Specs Frozen | Contract, scoring spec, scenarios, data model approved |
| 2 | Walking Skeleton | End-to-end dumb flow: UI → API → hardcoded score → UI |
| 3 | Core Engine | Real signals, scoring, explanations, profiles, simulator data |
| 4 | Guardian Experience | Safety Check UI, questions, step-up, scam simulator panel |
| 5 | Polish & Proof | Dashboard, metrics, API docs page, brand applied, bug bash |
| 6 | Pitch & Demo Lock | Deck, script, rehearsals, fallback recording, submission |

## Phase 0 — Kickoff & Foundations
- Confirm hackathon rules, dates, judging criteria, submission format (→ `05-pitch/judging-criteria-alignment.md`).
- Assign roles (`team-roles.md`). Agree on working hours & comms channel.
- Create GitHub org, repos, branch protection, labels, project board (`github-setup-guide.md`).
- Confirm tech stack (ADR-0002). Everyone can run hello-world locally.
- Name/brand check + logo brief kickoff (`04-brand/logo-plan.md`).

## Phase 1 — Specs Frozen
- Review & approve: `mvp-scope`, `api-contract`, `risk-scoring-spec`, `scam-scenarios`, `data-model`.
- Freeze contract v1 (changes only via PR with both owners).
- Pick the 3 demo scenarios and script expected outcomes.

## Phase 2 — Walking Skeleton
- API: `/health`, `/v1/transactions/assess` returning a **hardcoded** response matching the contract.
- Frontend: Send-money screen calls API, renders score + reasons.
- CI running in all code repos. Deploy hello-world to demo hosting.
- **Exit:** a teammate can click through end-to-end on the deployed URL.

## Phase 3 — Core Engine
- Simulator: generate 10–20 users, histories, reported numbers, scenario files; seed DB.
- Engine: implement signals one by one (each with unit tests) → scoring → explanation builder.
- Profiles: compute median/p95/hours/known recipients.
- Calibrate with simulator (FP/catch rates).
- **Exit:** scenarios S1, S2, S8 produce expected levels; legit payments stay Low.

## Phase 4 — Guardian Experience
- Safety Check (warn + challenge) UI, reasons list, risk meter.
- Smart questions → `/answers` → updated score.
- Step-up: cooldown, re-confirm, recipient confirm, trusted-contact simulation.
- Scam Simulator panel (one-click scenarios).
- **Exit:** full Flow A, B, C demoable without engineer intervention.

## Phase 5 — Polish & Proof
- Activity dashboard + prevented-loss stat.
- OpenAPI/Swagger polish + example curl in README; "Fraud Prevention API" page.
- Apply brand (logo, colors, favicon), empty/error states, mobile responsiveness.
- Bug bash; accessibility pass (contrast, tap targets); performance check.
- **Feature freeze** at the start of the last third of remaining time.

## Phase 6 — Pitch & Demo Lock
- Deck, demo script, Q&A prep; 3+ full rehearsals with a timer.
- Record a **backup demo video**; prepare offline/local fallback.
- Submission package (repo links, README, video, deck) submitted *early*, not at the deadline.

## Cadence
- Daily 15-min standup (yesterday/today/blockers). Board is the truth.
- Merge to `main` only when demo-ready. Tag checkpoints: `v0.1-skeleton`, `v0.2-engine`, `v0.3-experience`, `v1.0-demo`.

## Critical path
Contract freeze → skeleton → signals+scoring → Safety Check UI → scenario demo → pitch. Anything else is optional.
