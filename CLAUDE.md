# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project

Arcade Vault: online platform to play games and compete for highest score. Early stage — only the create-next-app scaffold exists (`app/page.tsx`, `app/layout.tsx`, `app/globals.css`). README says project follows spec-driven development via `/spec` and `/spec-impl` skills, installed with `npx skills@latest add Klerith/fernando-skills`.

## Stack and gotchas

- Next.js 16.4.4, React 19.3, Tailwind v4, TypeScript strict, App Router (`app/`). Path alias `@/*` maps to repo root.
- Next version has breaking changes vs. training data. Per `AGENTS.md`, read relevant guide in `node_modules/next/dist/docs/` (`01-app`, `02-pages`, `03-architecture`, `04-community`) before writing Next code.
- `next.config.ts` enables `cacheComponents`, `partialPrefetching`, and `experimental.agentFeedback`. `cacheComponents` changes caching/dynamic rendering semantics — check docs before using data fetching or dynamic APIs.
- Tailwind wired through Turbopack rule (`@tailwindcss/turbopack` loader for `*.css`), not PostCSS. Styles entry: `app/globals.css` (`@import "tailwindcss"`, theme tokens via `@theme inline`, dark mode via `prefers-color-scheme`).
- `app/layout.tsx` types props with the global `LayoutProps<"/">` helper (generated route types), not hand-written props. Fonts: Geist / Geist Mono via `next/font/google`.

## Skills

Usa siempre /frontend-design para diseñar la interfaz de usuario.