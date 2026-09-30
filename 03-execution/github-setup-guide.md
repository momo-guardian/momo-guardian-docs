# GitHub Setup Guide

## 1. Organization
1. GitHub → **New organization** → Free plan → name `momo-guardian` (or closest available).
2. Set org profile: description, logo (when ready), website (demo URL later).
3. Settings → Member privileges: base permission **Read**; repo creation limited to owners.

## 2. Repositories
Create these (public, or private until submission — check hackathon rules):

| Repo | Local folder | Description |
|---|---|---|
| `.github` | `.github/` (workspace root) | Org profile, templates, contributing |
| `momo-guardian-docs` | `momo-guardian-docs/` | Docs hub |
| `momo-guardian-frontend` | `momo-guardian-frontend/` | Demo app |
| `momo-guardian-api` | `momo-guardian-api/` | Fraud Prevention API |
| `momo-guardian-simulator` | `momo-guardian-simulator/` | Synthetic data & scenarios |

### Push each folder as its own repo
```bash
cd momo-guardian-docs            # repeat for each folder
git init -b main
git add .
git commit -m "chore: initial scaffold"
git remote add origin git@github.com:momo-guardian/momo-guardian-docs.git
git push -u origin main
git switch -c dev && git push -u origin dev
```
For the org-level profile repo, run the same inside the workspace's `.github/` folder, but **only** that folder's contents (`profile/`, templates, etc.) should be in that repo.

## 3. Branch protection (Settings → Branches → Add rule)
Applied to `main` (and `dev` with lighter rules):
- Require pull request before merging (1 approval)
- Require status checks (CI) to pass
- Require branches up to date
- Block force pushes & deletions

## 4. Labels (create in each repo)
`feat`, `fix`, `docs`, `chore`, `question`, `blocked`, `priority:high`, `priority:low`,
`area:risk-engine`, `area:ui`, `area:api`, `area:data`, `area:brand`, `area:pitch`, `phase:0`…`phase:6`.

## 5. Project board (Org → Projects)
Board "MoMo Guardian Execution" with columns: **Backlog · Ready · In progress · In review · Done**.
Custom fields: Phase (0–6), Owner, Size (S/M/L). Seed it from `execution-checklist.md`; link issues from all repos.

## 6. Milestones (per repo, mirror phases)
`M1 Skeleton`, `M2 Engine`, `M3 Experience`, `M4 Polish`, `M5 Demo lock`.

## 7. Security & hygiene
- Enable secret scanning & Dependabot alerts.
- `.gitignore` already in each repo; never commit `.env` (use `.env.example`).
- 2FA required for all members.

## 8. Releases/tags
Tag at checkpoints (`v0.1-skeleton` … `v1.0-demo`) in every repo the same day so versions line up.
