# simple-agent-skills

Two reusable agent skills for keeping documents and code simple, scoped, and verifiable.

## Skills

| Skill | Use for |
| --- | --- |
| `simple-doc` | Review, draft, design, or rewrite documents into clearer, more final-state output without changing confirmed meaning. |
| `simple-code` | Review, write, simplify, or refactor code without unnecessary abstraction or avoidable complexity. |

## Core Ideas

- Think before changing: understand goal, scope, constraints, and confirmed facts or behavior first.
- Simplicity over cleverness: prefer direct structure and direct code, not abstraction for its own sake.
- Preserve confirmed meaning, intended behavior, and current scope where they already exist.
- Keep changes surgical: fix the current problem without turning the task into a broader rewrite.
- Verify the result: if meaning or behavior cannot be verified, state the gap explicitly.

## Install

```text
copy skills/simple-doc/ to ~/.agents/skills/simple-doc/
copy skills/simple-code/ to ~/.agents/skills/simple-code/
```

## References

- [Karpathy Guidelines](https://github.com/multica-ai/andrej-karpathy-skills/blob/main/skills/karpathy-guidelines/SKILL.md)
- [Addy Osmani Agent Skills - Code Review and Quality](https://github.com/addyosmani/agent-skills/blob/main/skills/code-review-and-quality/SKILL.md)
- [Addy Osmani Agent Skills - Code Simplification](https://github.com/addyosmani/agent-skills/blob/main/skills/code-simplification/SKILL.md)
- [Anthropic Claude Plugins - Code Simplifier](https://github.com/anthropics/claude-plugins-official/blob/main/plugins/code-simplifier/agents/code-simplifier.md)

## License

MIT. See [LICENSE](./LICENSE).
