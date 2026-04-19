# Vue Skill References

> Loaded on demand when the task involves Vue 2/3, Nuxt, or Vue ecosystem libraries.

## Skill Selector

Match the task to the **first applicable row**, then load only that skill. Load additional skills only if the task explicitly spans multiple concerns.

| Task signal | Skill to load | Priority |
|-------------|---------------|----------|
| New Vue 3 project / general best practices | vue-best-practices | CRITICAL |
| Performance optimization | vue-best-practices (performance section) | CRITICAL |
| Options API project (`data()`, `methods`) | vue-options-api-best-practices | HIGH |
| Routing (Vue Router 4) | vue-router-best-practices | MEDIUM |
| State management (Pinia) | vue-pinia-best-practices | MEDIUM |
| Component/E2E testing | vue-testing-best-practices | MEDIUM |
| JSX in Vue | vue-jsx-best-practices | LOW |
| Debugging Vue 3 runtime issues | vue-debug-guides | HIGH |
| Creating reusable composables | create-adaptable-composable | MEDIUM |

---

## vue-best-practices
- **URL**: https://github.com/vuejs-ai/skills/blob/main/skills/vue-best-practices/SKILL.md
- **Summary**: Default stack: Vue 3 + Composition API + `<script setup lang="ts">`. 5-step workflow:
  1. Confirm architecture (reactivity/sfc/data-flow/composables)
  2. Apply fundamentals (minimal reactive state, SFC structure, component-splitting, data-flow contracts)
  3. Optional features (Slots/KeepAlive/Teleport/Suspense/Transition — on demand)
  4. Performance optimization (virtual lists, v-once/v-memo, avoid over-abstraction)
  5. Self-checklist

## vue-options-api-best-practices
- **URL**: https://github.com/vuejs-ai/skills/blob/main/skills/vue-options-api-best-practices/SKILL.md
- **Summary**: `this` binding, lifecycle-hook timing, TypeScript + Options API. Load only for explicit Options API projects.

## vue-router-best-practices
- **URL**: https://github.com/vuejs-ai/skills/blob/main/skills/vue-router-best-practices/SKILL.md
- **Summary**: Navigation guards (beforeEach/beforeRouteEnter), reactive route params/query, route-level lifecycle, nested routes.

## vue-pinia-best-practices
- **URL**: https://github.com/vuejs-ai/skills/blob/main/skills/vue-pinia-best-practices/SKILL.md
- **Summary**: Setup Store vs Options Store, reactivity pitfalls, cross-store interaction, SSR state isolation.

## vue-testing-best-practices
- **URL**: https://github.com/vuejs-ai/skills/blob/main/skills/vue-testing-best-practices/SKILL.md
- **Summary**: Vitest unit tests, Vue Test Utils, Playwright E2E, async component/Suspense testing.

## vue-jsx-best-practices
- **URL**: https://github.com/vuejs-ai/skills/blob/main/skills/vue-jsx-best-practices/SKILL.md
- **Summary**: Vue JSX vs React JSX differences (v-model, slots, event modifiers), template-compilation behavior.

## vue-debug-guides
- **URL**: https://github.com/vuejs-ai/skills/blob/main/skills/vue-debug-guides/SKILL.md
- **Summary**: 20+ topic groups — reactivity (ref unwrapping, proxy identity, batching), computed (no side effects, readonly, conditional deps), watcher (async cleanup, flush timing), plus component/props/template/forms/events/lifecycle/slots/provide-inject/SSR/performance diagnostics.

## create-adaptable-composable
- **URL**: https://github.com/vuejs-ai/skills/blob/main/skills/create-adaptable-composable/SKILL.md
- **Summary**: `MaybeRefOrGetter<T>` (read-only input) and `MaybeRef<T>` (writable input). Use `toRef()` for watcher sources, `toValue()` for plain values. Do not use MaybeRefOrGetter for function-value params. Requires Vue 3+ / Nuxt 3+.

---

## Fallback: Vue Core Best Practices

> Use when all external skills above are unavailable. Note in output: "External skill references unavailable; using built-in Vue best practices."

- Default to Composition API + `<script setup lang="ts">`.
- Minimal reactive state: source in `ref`/`reactive`, derive everything via `computed`.
- Props down, Events up — the core data-flow contract.
- Split components at 3+ independent UI regions, repeated templates, or mixed orchestration/presentation.
- Composables (`useXxx()`) for reusable logic and side effects.
- SFC order: `<script>` → `<template>` → `<style>`.
