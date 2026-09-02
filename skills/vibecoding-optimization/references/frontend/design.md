# Frontend Design Reference

Load for framework-agnostic or cross-framework UI implementation. Do not load for pure visual brainstorming, brand exploration, or non-coding design discussion.

## External skill

<external-skills>
  <skill name="frontend-design" url="https://github.com/anthropics/claude-code/blob/main/plugins/frontend-design/skills/frontend-design/SKILL.md">
    <summary>Use production-grade interface design: derive tone and constraints from goals, choose distinctive typography, define a CSS-variable color system, prefer CSS-first motion, and use deliberate spatial composition.</summary>
  </skill>
</external-skills>

## Built-in fallback

<fallback-rules>
  <rule>Establish a clear hierarchy with one primary action per view and muted secondary elements.</rule>
  <rule>Use one primary color, one accent color, and neutrals through CSS custom properties.</rule>
  <rule>Use at most two font families and maintain 4.5:1 body or 3:1 large-text contrast.</rule>
  <rule>Use a consistent spacing scale, such as a 4px base or Tailwind defaults.</rule>
  <rule>Use subtle 150 to 300ms interaction transitions and honor prefers-reduced-motion.</rule>
  <rule>Avoid decorative elements without a user-experience purpose.</rule>
</fallback-rules>
