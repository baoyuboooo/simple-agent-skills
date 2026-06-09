---
name: simple-doc
description: Use when simplifying or condensing documents that should become clearer, more direct, and easier to follow without changing confirmed meaning.
---

# Simple Doc

Make documents easier to understand, maintain, and execute through simplification. Do not merely make them shorter.

Simplification must not override user-stated goals, scope, and constraints, or required templates, rules, or fixed structure.

If reliable judgment is not possible, ask a human instead of guessing.

## Trigger Boundary

Auto-trigger this skill only when the request shows explicit simplification intent.

Examples of valid intent:

- simplify
- condense
- reduce redundancy
- make this more direct
- make this shorter by removing unnecessary content

Do not auto-trigger this skill on broad requests such as:

- optimize
- adjust
- review
- rewrite
- design
- organize

`optimize` only counts when paired with explicit simplification intent.

Explicit direct invocation such as `$simple-doc` remains valid even when the request does not include auto-trigger wording.

Explicit invocation does not widen this skill into general drafting, document design, or general rewrite work. The request must still be a simplification task.

## Default Action

Default to suggestions only.

Do not directly modify the document unless the user explicitly asks for execution with wording such as:

- auto-simplify
- apply the suggestions
- directly modify

These are representative examples, not a closed whitelist.

Explicit execution wording only enables modification within a simplification task. It does not convert this skill into a general authoring or drafting skill.

## Mixed-Intent Requests

If a request mixes simplification with non-simplification work, keep this skill scoped to the simplification portion only.

- If the request can be split cleanly, simplify the relevant part and leave the non-simplification part to another workflow or human decision.
- If the request cannot be split safely, ask the human to separate the simplification task from the rest.
- If explicit invocation is used for a non-simplification task such as drafting a new document from scratch, do not treat that as valid just because the skill name was invoked.

## 1. Think Before Editing

Understand the document goal before changing structure or wording.

- Identify the document type, audience, and intended use.
- Identify the simplification goal and what should become clearer, shorter, or more direct.
- Identify confirmed facts, rules, scope, constraints, templates, paths, and acceptance criteria.
- Identify unclear or unconfirmed content before changing wording or structure.
- Do not rewrite unclear content as if it were confirmed.
- If the task has a required template or explicitly required structure, preserve that structure before simplifying anything else.

## 2. Outline First

Inspect the document structure before editing sentences.

- Check whether the outline has a clear top-down shape.
- Keep heading levels shallow.
- Prefer fewer clear sections over deep nesting.
- Merge duplicated sections.
- Split sections that mix background, rules, workflow, checklist, or examples.
- Keep entry documents lightweight; point to deeper documents instead of copying full details.
- Do not expand the document scope to make it feel complete.
- Do not delete required sections or rewrite fixed structure merely to make the document feel simpler.

## 3. Top-Down Structure

Every document and section should reveal the point before the details.

- Put conclusions before explanations.
- Put stable rules before examples.
- Put required actions before optional notes.
- Put open questions in a dedicated place instead of scattering uncertainty through the body.
- Avoid long setup paragraphs before the actual rule, decision, or action.

## 4. Final-State Content Only

Formal documents should contain final decisions, not the path used to reach them.

For formal specs, runbooks, policies, and published guidance, prefer final-state content only.

When some inputs are still unresolved, improve structure and wording only within confirmed boundaries, and keep unresolved items explicit as open questions instead of inventing final answers.

Remove or rewrite:

- brainstorming residue
- abandoned alternatives
- "we can consider" language
- excessive rationale
- repeated explanations
- vague goals with no executable meaning

Keep only:

- confirmed conclusions
- confirmed rules
- confirmed workflow
- confirmed scope
- confirmed actions
- necessary open questions

## 5. Goal-Driven Surgical Editing

Edit only what improves the document for its real purpose.

- Every change must support the document goal.
- Do not rewrite stable sections without a reason.
- Do not introduce new facts, rules, or scope.
- Do not silently change confirmed meaning.
- Prefer small structural fixes before broad rewording.
- Keep terminology consistent with the source material.
- If structure constraints are unclear, avoid irreversible structural changes until the requirement is clearer, but still make safe local improvements where useful.

## Suggestions-First Rule

When document issues are found, provide simplification suggestions by default rather than editing immediately.

- Keep the suggestions scoped to the current document goal.
- Apply edits only when the user explicitly requests modification.
- When editing is explicitly requested, apply the smallest change that improves clarity without changing confirmed meaning.
- Re-check the updated document as a whole, not just the edited passage: outline, section responsibility, placement, surrounding fit, final-state wording, and open questions.
- Ask for human input when facts, scope, templates, acceptance criteria, confirmed meaning, or the correct structural or content decision cannot be determined reliably from the available context.
- Do not present the document as final when unresolved decisions remain.

## Output Contract

Return only the relevant sections.

For suggestion mode, use:

* `## 📌 Main Verdict`
* `## 🟥 High-Priority Suggestions`
* `## 🟨 Medium-Priority Suggestions`
* `## 🟩 Low-Priority Suggestions`
* `## 🛡 Meaning-Preservation Notes`
* `## ❓ Open Questions`

For auto-modification mode, use:

* `## 📌 Main Verdict`
* `## 🛠 Changes Made`
* `## 🛡 Preservation Notes`
* `## 🟨 Remaining Concerns`
* `## 🧪 Verification`
* `## ❓ Open Questions`

Rules:

* Use simple ordered lists for output items: `1. 2. 3.`
* Do not include empty sections.
* Do not include reasoning-process narration.
* Keep output scoped to simplification only.
* Use `## 🧪 Verification` to state what was checked and whether meaning, scope, confirmed facts, required structure, and constraints were preserved.
* Use `## ❓ Open Questions` for unresolved decisions, missing inputs, or unverified content that still needs human confirmation.



## Final Verification

- [ ] The structure is clearer, or required structure was preserved correctly when present.
- [ ] The document uses top-down structure.
- [ ] Reasoning residue, repeated content, and vague wording are removed.
- [ ] Confirmed facts, rules, scope, paths, templates, and acceptance criteria are preserved.
- [ ] New content does not invent unsupported facts, rules, or scope.
- [ ] Unclear inputs and unconfirmed content are listed under `## ❓ Open Questions`.
