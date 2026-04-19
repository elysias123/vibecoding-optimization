# Frontend Fundamentals

> Loaded on demand for general frontend questions (CSS, accessibility, performance, TypeScript, build tooling).
> Framework-agnostic — no external skills required.

## CSS / Styling
- Prefer CSS variables (Custom Properties) for themes and design tokens.
- Tailwind CSS: avoid dynamic class concatenation (`bg-${color}-500`); use full class names for build-tool extraction.
- Global `box-sizing: border-box` reset.
- Mobile-first responsive: prefer `min-width` media queries.
- Selector nesting: max 3 levels.

## Accessibility (a11y)
- Semantic HTML first (`<nav>`, `<main>`, `<article>`, `<button>`); minimize `<div>` abuse.
- All interactive elements: keyboard-accessible (focus management, tabindex).
- Images: meaningful `alt` text; decorative images use `alt=""`.
- Color contrast: WCAG AA minimum (4.5:1 body, 3:1 large text).
- Motion: provide `prefers-reduced-motion` fallback.

## Performance
- Core Web Vitals targets: LCP < 2.5s, INP < 200ms, CLS < 0.1.
- Images: modern formats (WebP/AVIF), explicit `width`/`height` to prevent CLS.
- Critical CSS inline; non-critical resources lazy-loaded.
- Third-party scripts: `async`/`defer`; analytics after hydration.
- Route-level code splitting as default.

## TypeScript
- Explicit type interfaces for component props and events.
- No `any`; use `unknown` + type narrowing.
- Runtime validation for API responses (Zod or similar).
- Export public types; keep internal types private.

## Build Tooling
- Vite: recommended general-purpose build tool (React/Vue/Svelte).
- Next.js: Turbopack (dev) / Webpack (prod) built-in.
- Tree shaking: ESM imports, avoid barrel-file side effects.
