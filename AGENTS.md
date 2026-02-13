# AGENTS.md

Guidance for AI coding agents working in this repository.

## Scope
This file applies to the entire repository (`/workspace/little-legends-tales`).

## Project snapshot
- Stack: Vite + React + TypeScript + Tailwind + shadcn-ui.
- Backend logic is in Supabase Edge Functions under `supabase/functions/`.
- Main UI code lives in `src/components/` with reusable primitives in `src/components/ui/`.

## Local setup and common commands
- Install deps: `npm i`
- Dev server: `npm run dev`
- Build: `npm run build`
- Lint: `npm run lint`

Before finishing a task, run lint and (when relevant) a production build.

## Coding conventions
- Use TypeScript and React functional components.
- Prefer existing UI primitives from `src/components/ui` before adding new patterns.
- Keep Tailwind utility usage consistent with nearby files.
- Avoid broad refactors unless the task explicitly requests them.
- Keep changes minimal and scoped to the request.

## Supabase function guidance
- Edge functions live at `supabase/functions/<function-name>/index.ts`.
- Keep secrets/config out of source; use environment variables.
- If changing function contracts, update any related frontend call sites.

## Validation checklist for agents
When code changes are made, aim to run:
1. `npm run lint`
2. `npm run build` (if build-impacting changes were introduced)

If a command cannot be run due to environment constraints, note that clearly in your final message.

## Commit and PR guidance
- Use clear, imperative commit messages (e.g., `docs: add repo AGENTS.md guidance`).
- Summaries should explain what changed and why.
- Reference exact files touched in your final response.
