---
name: ponytail
description: Makes AI agents write less code by enforcing YAGNI principles. Injects rules that force agents to check if code already exists before writing new code, use stdlib when possible, and write minimal solutions. Use when: (1) Agent is over-engineering solutions, (2) Code duplication is a concern, (3) Want to reduce token usage and cost, (4) Need faster AI coding sessions. Trigger on requests about code minimalism, YAGNI, reducing AI output, or optimizing agent performance.
---

# Ponytail

## Overview

Injects "write less code" rules into AI agents. Before writing code, agents must ask:
1. Does this need to exist? → No: skip it (YAGNI)
2. Already in codebase? → Reuse, don't rewrite
3. Stdlib does it? → Use it
4. One line? → One line

Based on [DietrichGebert/ponytail](https://github.com/DietrichGebert/ponytail) (60k+ stars).

## Quick Start

Copy `AGENTS.md` from the ponytail repo to your project root, or tell your agent:
"Use ponytail rules to write minimal code."

## Benefits

- ~54% less code (up to 94%)
- ~20% cheaper
- ~27% faster
- 100% safe (no validation/security shortcuts)

## Supported Platforms

Claude Code, Codex, Cursor, Windsurf, Cline, GitHub Copilot, Aider, Kiro, Zed, Gemini CLI, Agenty, Hermes Agent, OpenCode, Swival (16+ agents).

## Installation

### Claude Code
```
/plugin marketplace add DietrichGebert/ponytail
/plugin install ponytail@ponytail
```

### Codex
```bash
codex plugin marketplace add DietrichGebert/ponytail
codex
```

### Other Agents
Copy the rules from the ponytail repo's `AGENTS.md` or `.cursor/rules/` directory into your agent's config.

## Commands

- `/ponytail` - Set intensity (lite/full/ultra/off)
- `/ponytail-review` - Review diff for over-engineering
- `/ponytail-gain` - Show impact scoreboard

## References

- [GitHub](https://github.com/DietrichGebert/ponytail)
- [Website](https://ponytail.dev)
- License: MIT
