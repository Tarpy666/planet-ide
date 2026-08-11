# Planet IDE

Browser IDE kernel: file tree, tab lifecycle, command palette, terminal buffer with ANSI parsing.

Part of the Counted fleet (planet-ide), generated from `seeds/seeds.yaml`.

## Architecture

- `src/modules.ts` — FileTree, TabManager, CommandPalette, AnsiTerminal
- `src/index.ts` — public API (`SPEC`, `MODULES`, Registry)
- `src/rng.ts` — deterministic seeded PRNG (mulberry32)
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
