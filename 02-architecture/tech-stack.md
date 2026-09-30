# Tech Stack (proposed defaults — confirm at kickoff, record in ADR-0002)

| Layer | Choice | Why |
|---|---|---|
| Frontend | React + TypeScript + Vite + Tailwind CSS | Fast dev, common skill, easy demo deploy |
| Frontend state/data | Zustand (or Context) + TanStack Query | Light, simple |
| API | Python 3.11 + FastAPI + Pydantic | Fast to build, auto OpenAPI/Swagger docs (great for the "API" pitch), data-science friendly |
| Risk engine | Pure Python modules, config in YAML | Testable, transparent, tunable |
| DB | SQLite (SQLAlchemy) → Postgres later | Zero setup |
| Simulator | Python (Faker, numpy, pandas) | Reuses API models |
| Tests | pytest (api/sim), Vitest + Playwright (frontend) | |
| CI | GitHub Actions | Lint + test on PR |
| Hosting (demo) | Frontend: Vercel/Netlify · API: Render/Railway/Fly | Free tiers; have a local fallback |

**If the team is stronger in JS:** swap API to Node + Fastify/NestJS + Zod; the contract and risk spec stay identical.
Decide once, record in an ADR, don't revisit.
