---
name: simple-code
description: Use when simplifying code that should become more direct, easier to follow, and lower in unnecessary complexity or abstraction without changing required behavior or contracts.
---

# Simple Code

Make code easier to read, test, debug, and maintain. Do not make it clever, shorter, or more abstract for its own sake.

Simplification must not override user-stated goals, scope, and constraints, or required behavior, contracts, rules, or established boundaries.

If reliable judgment is not possible, ask a human instead of guessing.

## Trigger Boundary

Auto-trigger this skill only when the request shows explicit simplification intent.

Examples of valid intent:

- simplify
- reduce complexity
- remove redundancy
- reduce abstraction
- make this more direct

Do not auto-trigger this skill on broad requests such as:

- optimize
- adjust
- review
- rewrite
- design
- organize

`optimize` only counts when paired with explicit simplification intent.

Explicit direct invocation such as `$simple-code` remains valid even when the request does not include auto-trigger wording.

Explicit invocation does not widen this skill into general implementation, feature work, or open-ended refactoring. The request must still be a simplification task.

## Default Action

Default to suggestions only.

Do not directly modify the code unless the user explicitly asks for execution with wording such as:

- auto-simplify
- apply the suggestions
- directly modify

These are representative examples, not a closed whitelist.

Explicit execution wording only enables modification within a simplification task. It does not convert this skill into a general coding or implementation skill.

## Mixed-Intent Requests

If a request mixes simplification with non-simplification work, keep this skill scoped to the simplification portion only.

- If the request can be split cleanly, simplify the relevant part and leave the non-simplification part to another workflow or human decision.
- If the request cannot be split safely, ask the human to separate the simplification task from the rest.
- If explicit invocation is used for non-simplification work such as implementing a new feature, do not treat that as valid just because the skill name was invoked.

## 1. Think Before Coding

Understand the requirement, behavior, and boundaries before simplifying code.

- Identify the current requirement and expected behavior.
- Check nearby code, call sites, tests, and project conventions when available.
- Identify public contracts, data meaning, exception semantics, and system boundaries before changing code.
- Identify the simplification goal and what should become more direct or less complex.
- Do not simplify code whose behavior or responsibility is unclear.

## 2. Preserve Behavior Where Behavior Exists

For existing code, behavior preservation is the first rule.

- Do not change public contracts.
- Do not change data meaning.
- Do not change exception semantics.
- Do not change persistence, transaction, concurrency, or external integration semantics unless explicitly requested.
- Respect existing project structure and conventions by default, unless the task clearly calls for changing them.
- If behavior cannot be verified, say so.

## 3. Simplest Direct Design

Prefer the simplest simplification path that makes the current code easier to follow without expanding scope.

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

## Suggestions-First Rule

When code issues are found, provide simplification suggestions by default rather than editing immediately.

- Keep the suggestions scoped to the current requirement.
- Apply edits only when the user explicitly requests modification.
- When editing is explicitly requested, apply the smallest change that reduces complexity while still satisfying the current requirement.
- Re-check the updated code as a whole, not just the edited lines: behavior, contracts, abstraction, scope, placement, surrounding fit, and verification.
- Ask for human input when behavior, contracts, data meaning, acceptance criteria, verification requirements, or the correct behavior, contract, or structural decision cannot be determined reliably from the available context.
- Do not present the change as safe when the intended behavior cannot be verified.

## Output Contract

Return only what the task needs.

In suggestion mode, return only relevant items:

- main verdict
- 🟥 high-priority suggestions
- 🟨 medium-priority suggestions
- 🟩 low-priority suggestions
- behavior risks
- verification gap

`main verdict` remains unadorned. The priority sections use emoji for scanability.

In auto-modification mode, return only relevant items:

- main verdict
- 🛠 changes made
- 🛡 preservation notes
- 🟨 remaining concerns
- 🧪 verification or 🧪 verification gap

Verification must state how behavior or requirements were protected. If verification is not possible, state the gap clearly.

## Final Verification

- [ ] Existing behavior, public contracts, data meaning, and exception semantics are preserved where applicable.
- [ ] The simplified code still satisfies the current requirement without unnecessary extra scope.
- [ ] The implementation is more direct, clearer, and easier to test or debug without breaking required behavior, contracts, or boundaries.
- [ ] No unsupported abstraction, layer, pattern, dependency, or speculative extension point was added.
- [ ] Changes are scoped to the current task.
- [ ] Verification is stated, or the verification gap is explicit.
