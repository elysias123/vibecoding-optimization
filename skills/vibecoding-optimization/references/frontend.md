# Frontend Task Router

> Entry point for frontend programming tasks. It contains only routing and loading rules.
> Load sub-files only when the main skill is active for the current turn and the routing table below matches.

## Rules

1. Use this router only after the main skill is activated for the current turn.
2. Match the task to the routing table and load only the listed sub-file(s); do not preload others.
3. Do not use this router for generic design discussion or general frontend Q&A outside programming work.
4. If an external skill is unavailable, skip it and continue; if none are available, use the matched sub-file's fallback and note it in output.

## Routing Table

| Task signal | Load file |
|-------------|-----------|
| React / Next.js project (new or existing) | `references/frontend/react.md` |
| Vue project (new or existing) | `references/frontend/vue.md` |
| React Native / Expo mobile app | `references/frontend/react.md` (React Native section) |
| UI/visual design task that results in frontend implementation artifacts (framework-agnostic) | `references/frontend/design.md` |
| General frontend implementation question (CSS, a11y, perf, TS, tooling) | `references/frontend/fundamentals.md` |
| Other frameworks (Svelte, Angular, Solid, etc.) | `references/frontend/fundamentals.md` (apply general principles; no framework-specific skill available) |
| Task spans multiple areas (e.g., new React project with design focus) | Load matched files in order above, skip duplicates |

## Stack-Direction Alignment

When the main SKILL.md suggests a tech-stack direction, apply it **after** loading the relevant sub-file:
- **Simple & Fast**: use only the core skill from the sub-file; skip advanced/optional skills.
- **Maintainable**: load core + architecture/patterns skills.
- **High Performance**: load core + performance-focused rules (CRITICAL/HIGH priority items).
