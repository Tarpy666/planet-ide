# Planet IDE

Browser IDE kernel: file tree, tab lifecycle, command palette, terminal buffer with ANSI parsing.

Part of the Counted fleet (planet-ide), stack class `frontend`, generated
from `seeds/seeds.yaml`.

## Architecture (docs/REPO_STANDARD.md)

- `src/lib/modules.ts` — module registry: FileTree, TabManager, CommandPalette, AnsiTerminal
- `src/lib/rng.ts` — deterministic seeded PRNG (mulberry32)
- `src/index.ts` — public API (`SPEC`, `MODULES`, Registry)
- `src/ui/` — frontend surfaces (reserved; this repo ships a headless kernel)
- `assets/<kind>/` — media by kind (see assets policy READMEs)
- `docs/STRUCTURE.md` — this repo's stack declaration + layout map
- `tests/index.test.ts` — deterministic behavior suite

## Usage

```bash
npm install
npm run typecheck   # strict TS, zero errors
npm test            # deterministic, seeded
npm run build
```

## Determinism

All outputs are seeded; identical inputs produce identical results on any runtime.
