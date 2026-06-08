---
name: simple-code
description: Use when reviewing, writing, simplifying, or refactoring code that should stay direct, readable, testable, and free of unsupported abstractions.
---

# Simple Code

Make code easier to read, test, debug, and maintain. Do not make it clever, shorter, or more abstract for its own sake.

Simplification must not override user-stated goals, scope, and constraints, or required behavior, contracts, rules, or established boundaries.

If reliable judgment is not possible, ask a human instead of guessing.

## 1. Think Before Coding

Understand the requirement, behavior, and boundaries before writing or changing code.

- Identify the current requirement and expected behavior.
- Check nearby code, call sites, tests, and project conventions when available.
- Identify public contracts, data meaning, exception semantics, and system boundaries before changing code.
- Identify whether the task is review, implementation, simplification, refactoring, or final cleanup.
- If the task is new code, identify the narrowest design that satisfies the current requirement.
- Do not simplify or extend code whose behavior or responsibility is unclear.

## 2. Preserve Behavior Where Behavior Exists

For existing code, behavior preservation is the first rule.

- Do not change public contracts.
- Do not change data meaning.
- Do not change exception semantics.
- Do not change persistence, transaction, concurrency, or external integration semantics unless explicitly requested.
- Respect existing project structure and conventions by default, unless the task clearly calls for changing them.
- If behavior cannot be verified, say so.

For new code, preserve the intended requirement rather than inventing extra behavior or scope.

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
- For new modules or architecture work, choose the smallest design that is clear now instead of building speculative extension points.

Simple means easier to understand, test, debug, and change, not fewer lines.

Use design principles only when they reduce current complexity. Do not add abstractions just to satisfy a named principle.

Keep responsibilities clear, but do not split code into extra classes unless the split makes current behavior or current design easier to understand, test, or change.

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
- Prefer small, reviewable changes.
- Leave a note when a larger cleanup is useful but out of scope.
- If behavior, contract, or structure constraints are unclear, default to the smallest safe local change.

## Self-Repair

When code issues are found, fix them directly when the task allows editing.

- Do not stop at suggestions if a safe scoped change can be applied.
- Apply the smallest change that reduces complexity while still satisfying the current requirement.
- Re-check the updated code as a whole, not just the edited lines: behavior, contracts, abstraction, scope, placement, surrounding fit, and verification.
- Repeat until the code satisfies this skill or a human decision is required.
- Ask for human input when behavior, contracts, data meaning, acceptance criteria, verification requirements, or the correct behavior, contract, or structural decision cannot be determined reliably from the available context.
- Do not present the change as safe when the intended behavior cannot be verified.

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
- behavior or requirement preservation
- verification
- remaining concerns

Verification must state how behavior or requirements were protected. If verification is not possible, state the gap clearly.

## Final Verification

- [ ] Existing behavior, public contracts, data meaning, and exception semantics are preserved where applicable.
- [ ] New code satisfies the current requirement without unnecessary extra scope.
- [ ] The implementation is more direct, clearer, and easier to test or debug without breaking required behavior, contracts, or boundaries.
- [ ] No unsupported abstraction, layer, pattern, dependency, or speculative extension point was added.
- [ ] Changes are scoped to the current task.
- [ ] Verification is stated, or the verification gap is explicit.
