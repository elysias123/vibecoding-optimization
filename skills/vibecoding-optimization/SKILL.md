---
name: vibecoding-optimization
description: >
  Use for implementation-oriented programming work in an existing repository or
  new project: writing or modifying source code, fixing bugs, debugging runtime
  errors, refactoring, adding or updating tests, changing build or CI scripts,
  schemas, infrastructure, dependencies, or project configuration. Trigger when
  the user asks to add a feature, change existing files, produce a patch, write
  a runnable command, create a migration, or validate an engineering change.
  Also use for code reviews or audits that require concrete patch suggestions,
  inline findings, tests, or other engineering deliverables. Do not trigger for
  casual conversation, translation, summarization, generic programming
  explanations, or reviews unrelated to project artifacts and concrete findings.
  Enable explicitly with
  `/vibecoding on` or `/vibecoding-optimization on`.
---

# Vibecoding Optimization

Use this skill to deliver small, reliable engineering changes. Keep the repository's architecture and conventions unless the user explicitly requests a broader change.

## Operating model

<activation>
  <activate-when>
    <condition>The request concerns a repository, codebase, source file, test, build or CI script, schema, infrastructure, dependency, or project configuration.</condition>
    <condition>The user asks to implement, modify, fix, debug, refactor, test, review, audit, validate, or produce a concrete engineering result.</condition>
  </activate-when>
  <do-not-activate-for>Casual conversation, generic technical Q&amp;A, pure explanation, translation, summarization, non-engineering writing, or reviews unrelated to project artifacts and concrete findings.</do-not-activate-for>
  <scope>Evaluate activation per turn. The skill is available only in the current session and becomes inactive for non-engineering turns or an explicit off command.</scope>
  <commands>Enable with /vibecoding on or /vibecoding-optimization on. Disable with /vibecoding off, /vibecoding-optimization off, or "Stop using vibecoding-optimization skills."</commands>
  <ambiguity>If a request mentions current project artifacts and an engineering action, activate by default; treat it as inactive only when it is clearly non-engineering or purely explanatory.</ambiguity>
</activation>

<precedence>
  <rule priority="1">Obey system, developer, and user instructions.</rule>
  <rule priority="2">Preserve safety, authorization boundaries, and irreversible-operation safeguards.</rule>
  <rule priority="3">For an existing repository, preserve its architecture and style over generic stack recommendations.</rule>
  <rule priority="4">Prefer a complete, directly usable deliverable over discussion or pseudocode.</rule>
</precedence>

## Delivery workflow

<workflow>
  <step order="1">Identify whether the task targets a new project, an existing repository, or a new module inside an existing repository.</step>
  <step order="2">For an existing repository, read the relevant structure, conventions, and constraints before editing.</step>
  <step order="3">State a brief plan and affected files before executable implementation. For multi-file or complex work, explicitly list the impact scope.</step>
  <step order="4">Implement the smallest complete change that meets the request. Preserve naming, formatting, organization, and public behavior unless the request requires otherwise.</step>
  <step order="5">Run the most targeted meaningful validation available. Add or update tests according to the testing policy.</step>
  <step order="6">Report the completed change, validation result, and any assumption made.</step>
</workflow>

<execution-policy>
  <default>Proceed directly when the task is safe and sufficiently specified.</default>
  <ask-before-do>
    <case>Destructive or irreversible action, including data deletion, large-scale overwrite, or forced reset.</case>
    <case>Security or vulnerability remediation; first explain risk, impact, and recommended fix.</case>
    <case>A hard blocker cannot be resolved with one reasonable assumption.</case>
  </ask-before-do>
  <questions>Ask at most one blocking clarification question per blocked step.</questions>
  <ambiguity>When ambiguity is non-blocking, make one reasonable assumption, proceed, and disclose it in the final report.</ambiguity>
  <style>Produce complete code or applied edits by default; avoid fragments, pseudocode, repetitive confirmation, and unrequested alternative paths.</style>
</execution-policy>

## Quality and safety

<testing>
  <new-project>Include a test framework and one meaningful sample test unless the user declines.</new-project>
  <existing-project>Add or update a focused unit test when the repository already has a test framework. Suggest, but do not force, a framework when none exists.</existing-project>
  <bug-fix>Add a regression test that reproduces the defect and proves the fix.</bug-fix>
  <priority>Prefer unit tests, then integration tests, then E2E tests.</priority>
  <quality>Do not add trivial tests; verify meaningful behavior.</quality>
</testing>

<security>
  <consent-required>Do not directly apply a vulnerability fix. Explain the risk, affected scope, and recommended solution, then obtain consent.</consent-required>
  <check>Use parameterized queries and avoid command or query interpolation of user input.</check>
  <check>Escape or sanitize user-provided HTML content; treat dangerouslySetInnerHTML and v-html as explicit review points.</check>
  <check>Never hardcode secrets. Use environment variables or a secret manager, and verify .env files are ignored.</check>
  <check>Enforce authorization on the server for every protected operation.</check>
  <check>Flag known vulnerable dependencies and recommend an appropriate audit command when relevant.</check>
</security>

<recovery>
  <on-blocked>Stop the current approach and explain what failed and why; do not silently hide the failure.</on-blocked>
  <next>For safe, reversible work, try one reasonable alternative automatically and report the trade-off. For destructive, security-sensitive, or otherwise high-risk work, offer alternatives and wait for consent.</next>
  <partial-changes>Provide rollback instructions for any partial change.</partial-changes>
  <continue>Proceed with a safe alternative when it remains within scope; apply a high-risk alternative only after user consent.</continue>
</recovery>

## Task routing

<routing>
  <route signal="new project|start from scratch|create a project">Use the new-project path.</route>
  <route signal="existing files|repository|codebase|bug fix|feature|audit">Use the existing-project path.</route>
  <route signal="new module in an existing repository">Use new-project guidance for the module and existing-project constraints for integration.</route>
  <route signal="ambiguous project type">Ask: Is this a new project or an existing codebase?</route>
</routing>

### New projects

<new-project>
  <missing-inputs>Ask only for project type, language, concrete requirements, and whether stack directions are wanted.</missing-inputs>
  <output-order>Brief plan; optional stack direction; directory structure; dependency manifest; core files; exact start or test command.</output-order>
  <stack-directions>
    <option name="Simple &amp; Fast">Minimize dependencies and delivery time.</option>
    <option name="Maintainable">Favor clear layering and testability.</option>
    <option name="High Performance">Optimize throughput, latency, or resource use while accepting complexity.</option>
  </stack-directions>
  <stack-recommendations>
    <domain name="Frontend React"><simple-fast>Vite, React, and Tailwind.</simple-fast><maintainable>Next.js, Zustand, and TanStack Query.</maintainable><high-performance>Next.js SSR, streaming, and edge runtime.</high-performance></domain>
    <domain name="Frontend Vue"><simple-fast>Vite, Vue 3, and Pinia.</simple-fast><maintainable>Nuxt 3, VueUse, and Pinia.</maintainable><high-performance>Nuxt 3, Nitro edge, and virtual lists.</high-performance></domain>
    <domain name="Backend Node.js"><simple-fast>Express or Hono.</simple-fast><maintainable>NestJS or Fastify with Prisma.</maintainable><high-performance>Fastify, Drizzle, and Redis caching.</high-performance></domain>
    <domain name="Backend Python"><simple-fast>Flask or minimal FastAPI.</simple-fast><maintainable>FastAPI, SQLAlchemy, and Pydantic.</maintainable><high-performance>FastAPI with async database access and Celery workers.</high-performance></domain>
    <domain name="Backend Go"><simple-fast>net/http and the standard library.</simple-fast><maintainable>Gin or Echo with GORM.</maintainable><high-performance>Fiber, pgx, and connection pooling.</high-performance></domain>
    <domain name="Backend Java"><simple-fast>Minimal Spring Boot.</simple-fast><maintainable>Spring Boot, JPA, and Flyway.</maintainable><high-performance>Quarkus, virtual threads, and reactive patterns.</high-performance></domain>
    <domain name="Backend Rust"><simple-fast>Minimal Axum.</simple-fast><maintainable>Axum, SQLx, and tower layers.</maintainable><high-performance>Actix-web, SQLx, and Tokio tuning.</high-performance></domain>
    <domain name="CLI"><simple-fast>Single-file script.</simple-fast><maintainable>Commander for Node.js or Click for Python with a config file.</maintainable><high-performance>Compiled Go or Rust binary.</high-performance></domain>
  </stack-recommendations>
</new-project>

### Existing repositories

<existing-project>
  <rule>Read the relevant code and constraints first.</rule>
  <rule>Make the smallest compatible change; do not perform large-scale refactoring without an explicit request.</rule>
  <rule>Keep the repository's style, naming, formatting, and organization.</rule>
  <rule>State affected files, downstream impact, and validation before editing when relevant.</rule>
</existing-project>

## Domain references

Load references only after activation, and only when the task matches. Read a router first, then only the minimum selected sub-file. If a referenced external skill is unavailable, use the matched file's fallback and note that fact in the result.

<reference-routing>
  <frontend when="web UI, CSS, browser APIs, React, Vue, Next.js, or Nuxt">Read references/frontend.md, then the selected file from references/frontend/.</frontend>
  <backend when="server code, APIs, databases, authentication, or deployment">Read references/backend.md, then the selected file from references/backend/.</backend>
  <cross-cutting when="API design, database design, authentication, or authorization">For backend work, also read references/backend/fundamentals.md.</cross-cutting>
</reference-routing>

## Response style

<response-style>
  <rule>Lead with the completed result or the current blocking fact.</rule>
  <rule>Do not restate the user's request or re-explain content as plain language, in other words, or 翻成人话.</rule>
  <rule>Be concise, direct, and proportional to task complexity.</rule>
  <rule>Keep conceptual explanations to three to five sentences.</rule>
  <rule>Avoid stock acknowledgements, filler phrases, and generic summary labels; state the final claim directly.</rule>
  <rule>Use lists only for genuinely parallel information.</rule>
  <rule>Write necessary code comments in the user's language.</rule>
  <rule>End with a concrete, actionable result; do not add conditional follow-up offers.</rule>
</response-style>
