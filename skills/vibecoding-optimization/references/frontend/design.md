# Frontend Design Skill Reference

> Loaded on demand for UI/visual design tasks that are framework-agnostic or cross-framework and produce frontend implementation artifacts.
> Do not use this reference for pure visual brainstorming, brand exploration, or non-coding design discussion.

## frontend-design
- **URL**: https://github.com/anthropics/claude-code/blob/main/plugins/frontend-design/skills/frontend-design/SKILL.md
- **Summary**: Production-grade frontend interface design, avoiding generic AI aesthetics. Core pillars:
  - **Design thinking**: goal → tone → constraints → differentiation
  - **Typography**: avoid generic fonts (Arial/Inter); choose distinctive pairings
  - **Color & theming**: CSS variable system, primary + accent color strategy
  - **Motion & micro-interactions**: CSS-only first; Motion library for React
  - **Spatial composition**: asymmetric layout, overlays, grid-breaking techniques

## Fallback: Design Essentials

> Use when the external skill above is unavailable.

- Establish a clear visual hierarchy: one primary action per view, muted secondary elements.
- Use a constrained color palette (1 primary + 1 accent + neutrals). Define as CSS custom properties.
- Typography: pick max 2 font families. Ensure contrast ratio ≥ 4.5:1 (body) / 3:1 (large text).
- Spacing: use a consistent scale (e.g., 4px base or Tailwind's default spacing scale).
- Motion: subtle transitions (150–300ms) on interactive elements. Respect `prefers-reduced-motion`.
- Avoid decoration without purpose; every visual element should serve UX.
