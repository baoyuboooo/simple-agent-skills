# simple-agent-skills

Two small reusable agent skills for keeping documents and code simple, scoped, and verifiable.

## Skills

- `simple-doc`: review, design, or rewrite documents into clearer, more final-state output without changing confirmed meaning
- `simple-code`: review, simplify, or refactor existing code without changing behavior or adding unsupported abstractions

## Core Ideas

- Think before changing: understand goal, scope, constraints, and confirmed facts or behavior first.
- Simplicity over cleverness: prefer direct structure and direct code, not abstraction for its own sake.
- Preserve what is already confirmed: do not silently change meaning, behavior, contracts, or scope.
- Keep changes surgical: fix the current problem without turning the task into a broader rewrite.
- Verify the result: if meaning or behavior cannot be verified, state the gap explicitly.

## Install

```text
copy skills/simple-doc/ to ~/.agents/skills/simple-doc/
copy skills/simple-code/ to ~/.agents/skills/simple-code/
```

## Notes

- These are plain Markdown skills.
- They are intentionally lightweight, not full project workflows or framework-specific rulebooks.
- `simple-code` is for existing code with behavior to preserve.

## References

- [Karpathy Guidelines](https://github.com/multica-ai/andrej-karpathy-skills/blob/main/skills/karpathy-guidelines/SKILL.md)
- [Addy Osmani Agent Skills - Code Review and Quality](https://github.com/addyosmani/agent-skills/blob/main/skills/code-review-and-quality/SKILL.md)
- [Addy Osmani Agent Skills - Code Simplification](https://github.com/addyosmani/agent-skills/blob/main/skills/code-simplification/SKILL.md)
- [Anthropic Claude Plugins - Code Simplifier](https://github.com/anthropics/claude-plugins-official/blob/main/plugins/code-simplifier/agents/code-simplifier.md)

## License

MIT. See [LICENSE](./LICENSE).
