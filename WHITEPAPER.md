# Planet IDE — Whitepaper

**Fleet designation:** `planet-ide` · Part of the Counted fleet.

## Abstract

Browser IDE kernel: file tree, tab lifecycle, command palette, terminal buffer with ANSI parsing. This repository ships a self-contained, deterministic implementation:
strict TypeScript, zero runtime dependencies, seeded and tested by construction.

## Architecture

Stack class: `frontend` (docs/REPO_STANDARD.md; agrees across seeds/seeds.yaml,
package.json, registry/fleet.json).

- `src/lib/` — core logic, one file per seed module (`modules.ts`, `rng.ts`)
- `src/ui/` / `src/server/` — reserved surfaces per stack class (frontend/backend)
- `src/index.ts` — public API surface (`SPEC`, `MODULES`, core classes)
- `assets/<kind>/` — media by kind, never inside `src/`
- `tests/index.test.ts` — deterministic behavior suite

## Determinism & Verification

Every output is seeded; identical inputs produce identical results on any
runtime. The green gate is: `npm run typecheck` (strict, zero errors) and
`npm test` (deterministic, seeded) must pass before release.

## Governance

This repository is managed by the Counted fleet tooling (`src/repo/*`,
`scripts/repo-factory.mjs`, `scripts/whitepaper-fleet.mjs`). The fleet-wide
manifest of truth lives at `registry/fleet.json`; workstream definitions in
`workstreams/*.yaml` are data, not code.

## License

MIT.
