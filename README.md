# simple-agent-skills

Reusable agent skills for simplifying documents and code while keeping scope, meaning, behavior, and verification explicit.

## Skills

| Skill | Use for |
| --- | --- |
| `simple-doc` | Simplify or condense documents into clearer, more direct output without changing confirmed meaning. |
| `simple-code` | Simplify code, reduce complexity, or remove unnecessary abstraction without changing required behavior or contracts. |

## Core Ideas

- Think before changing: understand goal, scope, constraints, and confirmed facts or behavior first.
- Trigger narrowly: use these skills for explicit simplification intent, not broad optimization or general drafting/coding requests.
- Simplicity over cleverness: prefer direct structure and direct code, not abstraction for its own sake.
- Simplification must not override higher-priority requirements, constraints, or established boundaries.
- Default to suggestions first: only modify directly when the user explicitly asks for execution.
- When reliable judgment is not possible, ask a human instead of guessing.
- Preserve confirmed meaning, intended behavior, and current scope where they already exist.
- Keep changes surgical: fix the current problem without turning the task into a broader rewrite.
- Verify the result: if meaning or behavior cannot be verified, state the gap explicitly.

## Install

```text
copy each skill directory under skills/ to ~/.agents/skills/<skill-name>/

example (install one skill):
copy skills/<skill-name>/ to ~/.agents/skills/<skill-name>/

example (install all current skills):
for each directory under skills/, copy it to ~/.agents/skills/<directory-name>/
```

## References

- [Karpathy Guidelines](https://github.com/multica-ai/andrej-karpathy-skills/blob/main/skills/karpathy-guidelines/SKILL.md)
- [Addy Osmani Agent Skills - Code Review and Quality](https://github.com/addyosmani/agent-skills/blob/main/skills/code-review-and-quality/SKILL.md)
- [Addy Osmani Agent Skills - Code Simplification](https://github.com/addyosmani/agent-skills/blob/main/skills/code-simplification/SKILL.md)
- [Anthropic Claude Plugins - Code Simplifier](https://github.com/anthropics/claude-plugins-official/blob/main/plugins/code-simplifier/agents/code-simplifier.md)

## License

MIT. See [LICENSE](./LICENSE).
