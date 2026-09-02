# Frontend Task Router

Use this router only after the main skill is active. Load the smallest matching set of frontend references.

<load-policy>
  <rule>Match the task, then load only the listed sub-file or files; never preload unrelated references.</rule>
  <rule>Do not use this router for generic design discussion or frontend Q&amp;A without implementation work.</rule>
  <rule>When an external skill is unavailable, use the matched file's fallback and state that in the result.</rule>
</load-policy>

## Routes

<routes>
  <route when="React or Next.js project" load="references/frontend/react.md" />
  <route when="Vue project" load="references/frontend/vue.md" />
  <route when="React Native or Expo app" load="references/frontend/react.md" section="React Native" />
  <route when="framework-agnostic UI or visual implementation" load="references/frontend/design.md" />
  <route when="CSS, accessibility, performance, TypeScript, or tooling" load="references/frontend/fundamentals.md" />
  <route when="Svelte, Angular, Solid, or another unsupported framework" load="references/frontend/fundamentals.md" note="Apply general principles." />
  <route when="multiple frontend concerns" load="All matched files in listed order" note="Skip duplicates." />
</routes>

## Stack direction

<stack-alignment>
  <simple-fast>Load only the core skill from the matched reference and skip optional skills.</simple-fast>
  <maintainable>Load the core skill and relevant architecture or pattern skills.</maintainable>
  <high-performance>Load the core skill and its CRITICAL or HIGH performance rules.</high-performance>
</stack-alignment>
