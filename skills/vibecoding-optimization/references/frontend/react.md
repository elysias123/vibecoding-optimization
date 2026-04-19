# React / React Native Skill References

> Loaded on demand when the task involves React, Next.js, or React Native.

## Skill Selector

Match the task to the **first applicable row**, then load only that skill. Load additional skills only if the task explicitly spans multiple concerns.

| Task signal | Skill to load | Priority |
|-------------|---------------|----------|
| New React/Next.js project | react-best-practices | CRITICAL |
| Performance optimization | react-best-practices (CRITICAL/HIGH rules only) | CRITICAL |
| Component API design / refactor | composition-patterns | HIGH |
| Page/route transition animations | react-view-transitions | MEDIUM |
| React Native / Expo mobile app | react-native-skills | CRITICAL |

---

## react-best-practices
- **URL**: https://github.com/vercel-labs/agent-skills/blob/main/skills/react-best-practices/SKILL.md
- **Source**: Vercel engineering
- **Summary**: 70 rules, 8 priority groups by impact:
  1. Eliminate async waterfalls [CRITICAL]
  2. Bundle size optimization [CRITICAL]
  3. Server performance [HIGH]
  4. Client data fetching [MEDIUM-HIGH]
  5. Rerender optimization [MEDIUM]
  6. Render performance [MEDIUM]
  7. JS performance [LOW-MEDIUM]
  8. Advanced patterns [LOW]

## composition-patterns
- **URL**: https://github.com/vercel-labs/agent-skills/blob/main/skills/composition-patterns/SKILL.md
- **Summary**: Scalable component APIs — 4 categories:
  1. Component architecture [HIGH] — avoid boolean props, compound-component structure
  2. State management [MEDIUM] — provider decoupling, Context API design
  3. Implementation patterns [MEDIUM] — explicit variants, children over renderX
  4. React 19 APIs [MEDIUM] — no forwardRef needed, use() replaces useContext()

## react-view-transitions
- **URL**: https://github.com/vercel-labs/agent-skills/blob/main/skills/react-view-transitions/SKILL.md
- **Summary**: View Transition API — `<ViewTransition>` component, animation triggers (enter/exit/update/share), addTransitionType for directional navigation, shared-element morph. Only startTransition/useDeferredValue/Suspense trigger animations. Next.js built-in support.

## react-native-skills
- **URL**: https://github.com/vercel-labs/agent-skills/blob/main/skills/react-native-skills/SKILL.md
- **Summary**: 8 categories:
  1. List performance [CRITICAL] — FlashList, memoize, callback stability
  2. Animation [HIGH] — GPU properties, useDerivedValue
  3. Navigation [HIGH] — native stack/tabs
  4. UI patterns [HIGH] — expo-image, Pressable, SafeArea
  5. State management [MEDIUM]
  6. Rendering [MEDIUM]
  7. Monorepo [MEDIUM]
  8. Configuration [LOW]

---

## Fallback: React Core Best Practices

> Use when all external skills above are unavailable. Note in output: "External skill references unavailable; using built-in React best practices."

- Single-responsibility components; split at ~200 lines.
- `useMemo`/`useCallback` for expensive computation and callback stability — do not over-memoize.
- Data fetching: SWR or TanStack Query. Avoid raw `useEffect` + `fetch`.
- State management progression: component-local → Context → Zustand/Jotai → Redux.
- Next.js: prefer Server Components; add `'use client'` only for interactivity.
- Parallelize independent async with `Promise.all()` to avoid waterfalls.
