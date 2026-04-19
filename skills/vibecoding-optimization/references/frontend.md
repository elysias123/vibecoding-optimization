# Frontend Task Router

> **This file is the entry point for frontend tasks.** It contains ONLY a routing table and loading rules.
> Detailed skill references and fallback best practices are in sub-files under `references/frontend/`.
> **Do NOT load sub-files unless the routing table below directs you to.**

## Rules

1. Match the user's task to a row in the **Routing Table** below.
2. Load **only** the sub-file(s) indicated by the matched row. Do NOT preload other sub-files.
3. If an external skill (referenced inside a sub-file) is not installed and cannot be fetched from its URL, skip it and continue.
4. If no external skills can be obtained at all, each sub-file contains its own fallback section — use that and note it in output.

## Routing Table

| Task signal | Load file |
|-------------|-----------|
| React / Next.js project (new or existing) | `references/frontend/react.md` |
| Vue project (new or existing) | `references/frontend/vue.md` |
| React Native / Expo mobile app | `references/frontend/react.md` (React Native section) |
| Pure UI/visual design (framework-agnostic) | `references/frontend/design.md` |
| General frontend question (CSS, a11y, perf, TS, tooling) | `references/frontend/fundamentals.md` |
| Other frameworks (Svelte, Angular, Solid, etc.) | `references/frontend/fundamentals.md` (apply general principles; no framework-specific skill available) |
| Task spans multiple areas (e.g., new React project with design focus) | Load matched files in order above, skip duplicates |

## Stack-Direction Alignment

When the main SKILL.md suggests a tech-stack direction, apply it **after** loading the relevant sub-file:
- **Simple & Fast**: use only the core skill from the sub-file; skip advanced/optional skills.
- **Maintainable**: load core + architecture/patterns skills.
- **High Performance**: load core + performance-focused rules (CRITICAL/HIGH priority items).
