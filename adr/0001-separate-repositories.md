# ADR-0001: Separate repositories per concern
**Status:** Accepted
**Decision:** Separate repos for frontend, API, simulator, and docs, plus org `.github`.
**Why:** Independent ownership and CI; clear boundaries; API can be shown/productized alone; docs stay central.
**Consequences:** Contract must be versioned in docs (`api-contract.md`); cross-repo changes need coordinated PRs.
**Mitigation:** Contract-first rule in CONTRIBUTING; each code repo also has a local `docs/` that links to the hub.
