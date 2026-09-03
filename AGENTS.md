# Bingo Mixer Agent Guide

## Project Shape

- Vite + React 19 + TypeScript app for an in-person social bingo game.
- `src/App.tsx` selects the start/game flow and controls the bingo modal.
- `src/hooks/useBingoGame.ts` owns game state, actions, localStorage persistence, and restoration.
- `src/utils/bingoLogic.ts` owns board generation, immutable square updates, and win detection.
- `src/data/questions.ts` owns the question pool and free-space label.
- `src/components/` contains presentational UI: screens, board, squares, and modal.
- `src/types/` contains shared domain types.

Keep these boundaries intact: rendering belongs in components, state orchestration in the hook, and game rules in utilities. Prefer existing typed props and named function component exports.

## Commands

```bash
npm install
npm run dev
npm run lint
npm test
npm run build
```

Run the narrowest relevant check after a change, then run the full relevant validation before finishing. Tests use Vitest with jsdom; current coverage is concentrated in `src/utils/bingoLogic.test.ts`.

## Implementation Rules

- Use strict TypeScript and `import type` for type-only imports.
- Preserve immutability when changing boards or square objects; tests rely on reference preservation.
- Keep the 5x5 board contract and the center free space intact unless the feature explicitly changes the game rules.
- Changes to persisted `GameState` or `BingoLine` data must preserve or deliberately migrate the versioned localStorage format in `useBingoGame.ts`.
- When adding a new win condition, update win detection, winning-square calculation, persisted-data validation, and focused tests together.
- Treat localStorage as untrusted input: retain validation and graceful recovery for malformed or stale data.
- For UI changes, preserve accessible button semantics such as `aria-pressed`, disabled free space behavior, and touch-friendly board controls.
- Use Tailwind CSS v4 conventions from [.github/instructions/tailwind-4.instructions.md](.github/instructions/tailwind-4.instructions.md); do not add a `tailwind.config.js` unless the architecture changes.

## Documentation and Workflows

- Setup, scripts, and deployment: [README.md](README.md)
- Contribution process: [CONTRIBUTING.md](CONTRIBUTING.md)
- Full lab workflow: [workshop/GUIDE.md](workshop/GUIDE.md)
- Design workflow: [workshop/02-design.md](workshop/02-design.md)
- TDD and multi-agent workflow: [workshop/04-multi-agent.md](workshop/04-multi-agent.md)
- Existing custom agents and skills: [.github/agents/](.github/agents/) and [.github/skills/](.github/skills/)

GitHub Pages builds use `VITE_REPO_NAME` to calculate the base path. Keep the app and workshop-doc deployment layout in [.github/workflows/deploy.yml](.github/workflows/deploy.yml) compatible when changing build or public paths.
