# Vue Skill References

Load for Vue 2 or 3, Nuxt, or Vue ecosystem work. Match the first applicable route and load additional skills only when the task explicitly spans multiple concerns.

## Skill selector

<skill-selector>
  <route when="new Vue 3 project or general best practices" skill="vue-best-practices" priority="CRITICAL" />
  <route when="performance optimization" skill="vue-best-practices" scope="performance section" priority="CRITICAL" />
  <route when="Options API project using data() or methods" skill="vue-options-api-best-practices" priority="HIGH" />
  <route when="Vue Router 4 routing" skill="vue-router-best-practices" priority="MEDIUM" />
  <route when="Pinia state management" skill="vue-pinia-best-practices" priority="MEDIUM" />
  <route when="component or E2E testing" skill="vue-testing-best-practices" priority="MEDIUM" />
  <route when="Vue JSX" skill="vue-jsx-best-practices" priority="LOW" />
  <route when="Vue 3 runtime debugging" skill="vue-debug-guides" priority="HIGH" />
  <route when="reusable composables" skill="create-adaptable-composable" priority="MEDIUM" />
</skill-selector>

## External skills

<external-skills>
  <skill name="vue-best-practices" url="https://github.com/vuejs-ai/skills/blob/main/skills/vue-best-practices/SKILL.md"><summary>Default to Vue 3, Composition API, and script setup with TypeScript. Confirm architecture, apply fundamentals, add optional features on demand, optimize performance, then self-check.</summary></skill>
  <skill name="vue-options-api-best-practices" url="https://github.com/vuejs-ai/skills/blob/main/skills/vue-options-api-best-practices/SKILL.md"><summary>Use for explicit Options API projects; cover this binding, lifecycle timing, and TypeScript.</summary></skill>
  <skill name="vue-router-best-practices" url="https://github.com/vuejs-ai/skills/blob/main/skills/vue-router-best-practices/SKILL.md"><summary>Cover guards, reactive params and query, route lifecycle, and nested routes.</summary></skill>
  <skill name="vue-pinia-best-practices" url="https://github.com/vuejs-ai/skills/blob/main/skills/vue-pinia-best-practices/SKILL.md"><summary>Cover Setup versus Options stores, reactivity pitfalls, cross-store interaction, and SSR isolation.</summary></skill>
  <skill name="vue-testing-best-practices" url="https://github.com/vuejs-ai/skills/blob/main/skills/vue-testing-best-practices/SKILL.md"><summary>Use Vitest, Vue Test Utils, Playwright E2E, and async component or Suspense testing.</summary></skill>
  <skill name="vue-jsx-best-practices" url="https://github.com/vuejs-ai/skills/blob/main/skills/vue-jsx-best-practices/SKILL.md"><summary>Cover Vue and React JSX differences: v-model, slots, event modifiers, and template compilation.</summary></skill>
  <skill name="vue-debug-guides" url="https://github.com/vuejs-ai/skills/blob/main/skills/vue-debug-guides/SKILL.md"><summary>Diagnose reactivity, computed values, watchers, components, props, templates, forms, events, lifecycle, slots, provide/inject, SSR, and performance.</summary></skill>
  <skill name="create-adaptable-composable" url="https://github.com/vuejs-ai/skills/blob/main/skills/create-adaptable-composable/SKILL.md"><summary>Use MaybeRefOrGetter for read-only input and MaybeRef for writable input; use toRef for watcher sources and toValue for plain values. Require Vue 3+ or Nuxt 3+, and do not use MaybeRefOrGetter for function-valued inputs.</summary></skill>
</external-skills>

## Built-in fallback

<fallback-rules>
  <rule>Default to Composition API and script setup with TypeScript.</rule>
  <rule>Keep reactive source state minimal in ref or reactive and derive state with computed.</rule>
  <rule>Maintain props-down and events-up data flow.</rule>
  <rule>Split components when three or more independent UI regions, repeated templates, or mixed orchestration and presentation appear.</rule>
  <rule>Use useXxx composables for reusable logic and side effects.</rule>
  <rule>Order SFC sections as script, template, then style.</rule>
</fallback-rules>
