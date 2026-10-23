# AGENTS.md

## 1. Think Before Coding

**Don't assume. Don't hide confusion. Surface tradeoffs.**

Before implementing:

- State your assumptions explicitly. If uncertain, ask.
- If multiple interpretations exist, present them. Do not pick silently.
- If a simpler approach exists, say so. Push back when warranted.
- If something is unclear, stop. Name what's confusing. Ask.

## 2. Simplicity First

**Minimum code that solves the problem. Nothing speculative.**

- No features beyond what was asked.
- No abstractions for single-use code.
- No "flexibility" or "configurability" that was not requested.
- No error handling for impossible scenarios.
- If you write 200 lines and it could be 50, rewrite it.

Before finalizing, ask yourself:

> Would a senior engineer say this is overcomplicated?

If yes, simplify.

## 3. Surgical Changes

**Touch only what you must. Clean up only your own mess.**

When editing existing code:

- Do not "improve" adjacent code, comments, or formatting.
- Do not refactor things that are not broken.
- Match existing style, even if you would do it differently.
- If you notice unrelated dead code, mention it. Do not delete it.

When your changes create orphans:

- Remove imports, variables, functions, or files that your changes made unused.
- Do not remove pre-existing dead code unless explicitly asked.

Test:

> Every changed line should trace directly to the user's request.

## 4. Goal-Driven Execution

**Define success criteria. Loop until verified.**

Transform tasks into verifiable goals:

- "Add validation" → "Write tests for invalid inputs, then make them pass."
- "Fix the bug" → "Write a test that reproduces it, then make it pass."
- "Refactor X" → "Ensure tests pass before and after."

For multi-step tasks, state a brief plan before editing:

```text
1. [Step] → verify: [check]
2. [Step] → verify: [check]
3. [Step] → verify: [check]
```

Strong success criteria allow independent iteration. Weak criteria such as "make it work" require clarification.

## Working Rules

- Prefer the smallest correct change.
- Prefer readable code over clever code.
- Do not introduce new dependencies unless explicitly requested or clearly justified.
- Do not change public APIs, data contracts, database schemas, or architecture without calling it out first.
- Run the most relevant verification available: tests, typecheck, lint, build, or targeted manual check.
- If verification cannot be run, explain why and describe what should be run.
- Summarize only the meaningful changes at the end.
