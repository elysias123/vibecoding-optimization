# Frontend Fundamentals

Load for framework-agnostic implementation work involving CSS, accessibility, performance, TypeScript, or build tooling.

## Styling

<styling-rules>
  <rule>Use CSS custom properties for themes and design tokens.</rule>
  <rule>With Tailwind, avoid dynamic class concatenation such as bg-${color}-500; use complete class names for extraction.</rule>
  <rule>Apply a global box-sizing: border-box reset, mobile-first min-width media queries, and no more than three selector nesting levels.</rule>
</styling-rules>

## Accessibility

<accessibility-rules>
  <rule>Prefer semantic HTML such as nav, main, article, and button over div-only structures.</rule>
  <rule>Make every interactive element keyboard-accessible with appropriate focus management.</rule>
  <rule>Provide meaningful image alt text; use empty alt for decorative images.</rule>
  <rule>Meet WCAG AA contrast: 4.5:1 for body text and 3:1 for large text.</rule>
  <rule>Provide a prefers-reduced-motion fallback.</rule>
</accessibility-rules>

## Performance

<performance-rules>
  <rule>Target LCP below 2.5s, INP below 200ms, and CLS below 0.1.</rule>
  <rule>Use WebP or AVIF images with explicit dimensions.</rule>
  <rule>Inline critical CSS and lazy-load non-critical resources.</rule>
  <rule>Use async or defer for third-party scripts and load analytics after hydration.</rule>
  <rule>Use route-level code splitting by default.</rule>
</performance-rules>

## TypeScript and tooling

<tooling-rules>
  <rule>Define explicit types for component props and events; avoid any in favor of unknown with narrowing.</rule>
  <rule>Validate API responses at runtime with Zod or an equivalent.</rule>
  <rule>Export public types and keep internal types private.</rule>
  <rule>Use Vite as the general-purpose React, Vue, or Svelte toolchain; use Next.js built-ins for Next.js.</rule>
  <rule>Use ESM imports and avoid barrel-file side effects to preserve tree shaking.</rule>
</tooling-rules>
