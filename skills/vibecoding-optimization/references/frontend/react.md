# React and React Native Skill References

Load for React, Next.js, or React Native work. Match the first applicable route and load additional skills only when the task explicitly spans multiple concerns.

## Skill selector

<skill-selector>
  <route when="new React or Next.js project" skill="react-best-practices" priority="CRITICAL" />
  <route when="React performance optimization" skill="react-best-practices" scope="CRITICAL and HIGH rules only" priority="CRITICAL" />
  <route when="component API design or refactor" skill="composition-patterns" priority="HIGH" />
  <route when="page or route transition animation" skill="react-view-transitions" priority="MEDIUM" />
  <route when="React Native or Expo app" skill="react-native-skills" priority="CRITICAL" />
</skill-selector>

## External skills

<external-skills>
  <skill name="react-best-practices" source="Vercel engineering" url="https://github.com/vercel-labs/agent-skills/blob/main/skills/react-best-practices/SKILL.md">
    <summary>Priorities: eliminate async waterfalls and optimize bundle size (CRITICAL); server performance (HIGH); client fetching, rerenders, rendering, JavaScript performance, and advanced patterns.</summary>
  </skill>
  <skill name="composition-patterns" url="https://github.com/vercel-labs/agent-skills/blob/main/skills/composition-patterns/SKILL.md">
    <summary>Build scalable component APIs: avoid boolean-prop proliferation, use compound components and clear variants, decouple state with providers, and apply React 19 APIs appropriately.</summary>
  </skill>
  <skill name="react-view-transitions" url="https://github.com/vercel-labs/agent-skills/blob/main/skills/react-view-transitions/SKILL.md">
    <summary>Use the View Transition API for enter, exit, update, directional navigation, and shared-element animation. Trigger transitions through supported React scheduling APIs.</summary>
  </skill>
  <skill name="react-native-skills" url="https://github.com/vercel-labs/agent-skills/blob/main/skills/react-native-skills/SKILL.md">
    <summary>Prioritize list performance, GPU-friendly animation, native navigation, UI patterns, state, rendering, monorepos, and configuration.</summary>
  </skill>
</external-skills>

## Built-in fallback

<fallback-rules>
  <rule>Use single-responsibility components and split around 200 lines when responsibilities diverge.</rule>
  <rule>Use useMemo and useCallback for expensive work or callback stability; do not over-memoize.</rule>
  <rule>Use SWR or TanStack Query for fetching instead of raw useEffect plus fetch.</rule>
  <rule>Scale state from component-local to Context to Zustand or Jotai to Redux only as needed.</rule>
  <rule>In Next.js, prefer Server Components and add use client only for interactivity.</rule>
  <rule>Parallelize independent async work with Promise.all to prevent waterfalls.</rule>
</fallback-rules>
