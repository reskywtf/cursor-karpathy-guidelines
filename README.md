# Karpathy Guidelines for Cursor

A Cursor Agent skill based on [Andrej Karpathy's observations](https://x.com/karpathy/status/2015883857489522876) on LLM coding pitfalls. This skill helps AI coding agents avoid common mistakes by focusing on simplicity, surgical changes, and goal-driven execution.

## Overview

This skill provides behavioral guidelines for Cursor's AI agent to reduce common LLM coding mistakes. It addresses issues like wrong assumptions, overcomplication, bloated abstractions, and unnecessary code changes.

## The Four Principles

### 1. Think Before Coding
**Don't assume. Don't hide confusion. Surface tradeoffs.**

- State assumptions explicitly
- Present multiple interpretations when ambiguous
- Push back when a simpler approach exists
- Stop and ask when something is unclear

### 2. Simplicity First
**Minimum code that solves the problem. Nothing speculative.**

- No features beyond what was asked
- No abstractions for single-use code
- No unnecessary "flexibility" or "configurability"
- Rewrite if 200 lines could be 50

### 3. Surgical Changes
**Touch only what you must. Clean up only your own mess.**

- Don't "improve" adjacent code
- Match existing style
- Remove only what YOUR changes made unused
- Every changed line traces to the user's request

### 4. Goal-Driven Execution
**Define success criteria. Loop until verified.**

Transform tasks into verifiable goals:
- "Add validation" → "Write tests for invalid inputs, then make them pass"
- "Fix the bug" → "Write a test that reproduces it, then make it pass"
- "Refactor X" → "Ensure tests pass before and after"

## Installation

### For Cursor IDE

**Option 1: Personal Skills (all projects)**

Copy the skill to your personal skills directory:

```bash
mkdir -p ~/.cursor/skills/karpathy-guidelines
curl -o ~/.cursor/skills/karpathy-guidelines/SKILL.md \
  https://raw.githubusercontent.com/reskywtf/cursor-karpathy-guidelines/main/.cursor/skills/karpathy-guidelines/SKILL.md
```

**Option 2: Project-Specific**

Copy the `.cursor` directory to your project:

```bash
cd your-project
mkdir -p .cursor/skills/karpathy-guidelines
curl -o .cursor/skills/karpathy-guidelines/SKILL.md \
  https://raw.githubusercontent.com/reskywtf/cursor-karpathy-guidelines/main/.cursor/skills/karpathy-guidelines/SKILL.md
```

## When It's Applied

The Cursor agent will automatically apply these guidelines when:
- Writing new code
- Reviewing code changes
- Refactoring existing code
- You mention code quality, simplicity, or best practices

## How to Know It's Working

These guidelines are working when you see:
- Fewer unnecessary changes in diffs
- Simpler code on first attempt
- Clarifying questions before implementation
- Clean, minimal changes

## Tradeoff Note

These guidelines bias toward **caution over speed**. For trivial tasks (typo fixes, obvious one-liners), the agent will use judgment.

The goal is reducing costly mistakes on non-trivial work, not slowing down simple tasks.

## Attribution

This skill is based on the [Karpathy Guidelines](https://github.com/forrestchang/andrej-karpathy-skills) by [@forrestchang](https://github.com/forrestchang), which was derived from [Andrej Karpathy's observations](https://x.com/karpathy/status/2015883857489522876) on LLM coding pitfalls.

The original work focused on Claude Code. This adaptation makes the guidelines available as a Cursor Agent skill.

## License

MIT License - See [LICENSE](LICENSE) file for details.

Original work Copyright (c) forrestchang
Cursor adaptation Copyright (c) 2026

## Contributing

Contributions are welcome! Feel free to:
- Report issues
- Suggest improvements
- Submit pull requests

## Related Projects

- [andrej-karpathy-skills](https://github.com/forrestchang/andrej-karpathy-skills) - Original Claude Code version
- [Cursor Documentation](https://docs.cursor.com/) - Official Cursor docs
