---
name: vibecoding-optimization
description: 'A coding optimization skill for engineering tasks. It is not always on by default: activate via `/vibecoding-optimization on` or `/vibecoding on`, or when the current turn clearly meets the Activation Gate. It is valid only within the current conversation, can be paused/disabled for non-engineering turns or explicit off commands, and can be reactivated when activation conditions are met again. It enforces concise, reliable implementation guidance, stack direction options, and existing-architecture-first changes.'
---

# vibecoding-optimization
This is a skill focused on programming tasks, designed to improve the vibecoding development experience and enhance code reliability, readability, and maintainability.

## Applicable Scenarios
This skill is **not always-on by default**. It should be activated only when one of the following conditions is met:
1. The user explicitly enables it with `"/vibecoding-optimization on"` or `"/vibecoding on"`.
2. The request clearly has implementation intent (for example: modify code, fix errors, implement features, refactor code, write tests, or update project configuration).

Do not activate this skill for casual chat, greetings, generic Q&A, plain translation, or non-engineering writing tasks.

## Continuous Effect
Once activated, this skill is valid only for the current conversation session.

Session-scope behavior:
1. The skill state does not persist across new conversations.
2. If context is compressed/summarized and activation state is uncertain, treat the skill as inactive by default.
3. In ambiguous state, reactivate only when the user explicitly enables it again (`"/vibecoding-optimization on"` or `"/vibecoding on"`) or the current turn clearly meets the Activation Gate.

Auto-disable conditions (within this conversation):
1. The user switches to document/chat/translation/general discussion tasks.
2. The user explicitly disables it: `"Stop using vibecoding-optimization skills."`, `"/vibecoding-optimization off"`, or `"/vibecoding off"`.

Reactivation rule:
- After being stopped or auto-disabled, this skill may be reactivated in the same conversation whenever activation conditions are met again (explicit `on` command or current turn satisfies the Activation Gate).

## Rules
1. In trial scenarios, strictly follow the rules below to ensure consistency and high quality.
2. The rules include: programming task handling rules, output content rules, technology stack recommendation rules, security and vulnerability handling rules, and task routing guidelines.
3. These rules apply only after activation conditions are met, and must be paused/disabled when auto-disable conditions are met.
4. Output should be concise, clear, and readable.

### Activation Gate
- Activate only when **both** are true:
	1. The task is code-execution-oriented (implementing, modifying, debugging, testing, or architecture-level engineering decision).
	2. The expected output includes engineering artifacts (code changes, patches, runnable commands, or configuration updates).
- Do **not** activate for: casual conversation, greetings, broad conceptual discussion without implementation, pure translation, pure summarization, or non-engineering writing.
- Borderline case: if the user only asks for explanation without implementation, keep this skill inactive by default.

## Programming Task Handling Rules
- Generated code must follow best practices and style conventions of mainstream programming languages.
- During implementation, prioritize readability and maintainability.
- Technology stack recommendations must be based on the user’s specific needs and project type.
- New projects and existing project modifications must be handled differently and follow their respective guidelines.
- Without explicit instruction, implementation must respect the constraints of “no large-scale architectural changes” and “no changes to existing code style.”
- If a requirement cannot be fulfilled, clearly explain why, provide alternatives, and only proceed after obtaining user consent.
- Do not output follow-up prompts like “Do you need xx?”; iterate directly to a complete and executable result.
- Comments must be clear, accurate, and only include necessary information; avoid over-commenting or unrelated content, and write comments in the user’s language.

## Technology Stack Recommendation Rules
Before implementation, provide optional directions (choose one based on the task, or present multiple in parallel):
- **Simple & Fast**: minimal dependencies, shortest delivery path.
- **Maintainable**: clear layering, easy to test, suitable for medium- to long-term iteration.
- **High Performance**: focused on throughput/latency/resource usage, with acceptance of higher implementation complexity.
- Recommend appropriate technology stack directions based on user requirements and project type, and explain the reasons.

## Security and Vulnerability Handling Rules
- Do not directly modify code when vulnerabilities are found.
- First explain the risk, impact scope, and recommended solution.
- Apply fixes only after obtaining user consent.

## Task Routing

## New Project Handling Guidelines
Ask first, and ask only the following questions:
1. What kind of project do you want to build?
2. Which programming language would you like to use?
3. What are your specific requirements?
4. Would you like me to provide optional technology stack directions first (Simple & Fast / Maintainable / High Performance)?

After receiving answers, provide stack options first, then output implementation content.

## Existing Project Modification Guidelines
1. Read and understand the current code structure and constraints first.
2. Implement within the existing architecture; no large-scale refactoring.
3. Without explicit requirements, do not change the existing code style (keep naming, formatting, and organization consistent).
4. Output changes should be concise, readable, and compatible with the existing structure.
