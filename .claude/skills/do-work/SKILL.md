---
name: do-work
description: "Execute a unit of work end-to-end: plan, implement, validate with typecheck and tests, then commit. Use when user wants to do work, build a feature, fix a bug, or implement a phase from a plan."
---

# Do Work

Execute a complete unit of work: plan it, build it, validate it, commit it.

## Workflow

### 1. Understand the task

Read any referenced plan or PRD. Explore the codebase to understand the relevant files, patterns, and conventions. If the task is ambiguous, ask the user to clarify scope before proceeding.

### 2. Plan the implementation (optional)

If the task has not already been planned, create a plan for it.

### 3. Implement

Work through the plan step by step.

For **backend code**, use red-green-refactor, ONE test at a time in tracer bullet style:

1. Write one test targeting a thin vertical slice of behavior:
   - one API endpoint returning one shape of data, or
   - one service method handling one case
2. Run the test — confirm it fails (red)
3. Write the minimum production code to make it pass (green)
4. Move to the next test
5. Refactor if needed, keeping tests green

Do not write multiple tests upfront. Do not implement code without a failing test first.

This does **not** apply to frontend code.

### 4. Validate

Run the feedback loops and fix any issues. Repeat until both pass cleanly.

```
pnpm run typecheck
pnpm run test
```

### 5. Commit

Once typecheck and tests pass, commit the work using conventional commits.
