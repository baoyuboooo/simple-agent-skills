---
name: simple-code
description: Use when reviewing, simplifying, or refactoring existing code that should stay behavior-preserving, direct, readable, and free of unsupported abstractions.
---

# Simple Code

Make code easier to read, test, debug, and maintain. Do not make it clever, shorter, or more abstract for its own sake.

## 1. Think Before Changing

Understand the intended behavior before simplifying code.

- Identify the current requirement and expected behavior.
- Check nearby code, call sites, tests, and project conventions when available.
- Identify public contracts, data meaning, and exception semantics before changing code.
- Identify whether the task is review, simplification, refactoring, or final cleanup.
- Do not simplify code whose behavior or responsibility is unclear.

## 2. Preserve Behavior

Behavior preservation is the first rule for existing code.

- Do not change public contracts.
- Do not change data meaning.
- Do not change exception semantics.
- Do not add or remove features.
- Do not change persistence, transaction, concurrency, or external integration semantics unless explicitly requested.
- If behavior cannot be verified, say so.

## 3. Simplest Direct Design

Prefer the simplest design that satisfies the current requirement.

- Use direct control flow before patterns.
- Use concrete code before generic frameworks.
- Use existing functions before new utilities.
- Prefer the standard library, existing project utilities, and existing dependencies before adding a new dependency.
- Use framework features in the simplest conventional way.
- Use one clear method before multiple artificial layers.
- Follow existing project conventions before this skill's preferences.
- Do not optimize for hypothetical future requirements.

Simple means easier to understand, test, debug, and change, not fewer lines.

Use design principles only when they reduce current complexity. Do not add abstractions just to satisfy a named principle.

Keep responsibilities clear, but do not split code into extra classes unless the split makes current behavior easier to understand, test, or change.

This skill is primarily for existing code with behavior to preserve. For greenfield feature design, use the project's normal implementation workflow first, then apply this skill to keep the result direct and readable.

## 4. No Unsupported Abstractions

Reject abstractions without real responsibility.

Question:

- single-use interfaces
- single-implementation strategies
- unnecessary factories
- vague managers
- generic helpers
- converters that only rename fields
- layers that hide simple logic
- extension points without a current second use case

Keep an abstraction only when it has a clear current use, reduces real duplication, protects a real boundary, or matches existing project conventions.

Do not remove an abstraction until its responsibility, callers, and variation points are understood.

Do not over-simplify by inlining useful names, merging unrelated logic, or removing abstractions that improve testability, boundary protection, or understanding.

## 5. Goal-Driven Surgical Changes

Keep the change scoped and tied to the current task.

- Every change must trace back to the current task.
- Modify only code related to the task.
- Do not refactor unrelated modules.
- Do not mix simplification with new feature work.
- Prefer small, reviewable changes.
- Leave a note when a larger cleanup is useful but out of scope.

## Self-Repair

When code issues are found, fix them directly when the task allows editing.

- Do not stop at suggestions if a safe scoped change can be applied.
- Apply the smallest change that reduces complexity without changing behavior.
- Re-check behavior, contracts, abstraction, scope, and verification.
- Repeat until the code satisfies this skill or a human decision is required.
- Ask for human input only when behavior, contracts, data meaning, acceptance criteria, or verification requirements are unclear.
- Do not present the change as safe when behavior cannot be verified.

## Output Contract

Return only what the task needs.

For review, return only relevant items:

- main verdict
- complexity problems
- behavior risks
- fixes applied
- verification

For modification, return only relevant items:

- changes made
- simplifications
- behavior preservation
- verification
- remaining concerns

Verification must state how behavior was protected. If verification is not possible, state the gap clearly.

## Final Verification

- [ ] Behavior, public contracts, data meaning, and exception semantics are preserved.
- [ ] The implementation is simpler, more direct, and easier to test or debug.
- [ ] No unsupported abstraction, layer, pattern, dependency, or future extension point was added.
- [ ] Changes are scoped to the current task.
- [ ] Verification is stated, or the verification gap is explicit.
