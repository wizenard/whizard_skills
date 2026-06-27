---
name: rtk
description: CLI proxy that reduces LLM token consumption by 60-90% on common dev commands. Single Rust binary, zero dependencies. Use when: (1) AI agent sessions are consuming too many tokens, (2) Command output is verbose and wasteful, (3) Want to reduce coding costs, (4) Need faster AI coding sessions. Trigger on requests about token optimization, cost reduction, or command output compression.
---

# RTK (Rust Token Killer)

## Overview

High-performance CLI proxy that rewrites Bash commands to compact equivalents before they reach your LLM context. Single Rust binary, zero dependencies, <10ms overhead.

Based on [rtk-ai/rtk](https://github.com/rtk-ai/rtk) (66k+ stars).

## Quick Start

```bash
# Install
brew install rtk

# Initialize for your AI tool
rtk init -g              # Claude Code / Copilot (default)
rtk init -g --gemini     # Gemini CLI
rtk init -g --codex      # Codex (OpenAI)
```

Restart your AI tool, then test with `git status`.

## Token Savings (30-min Claude Code Session)

| Operation | Frequency | Standard | RTK | Savings |
|-----------|-----------|----------|-----|---------|
| `ls` / `tree` | 10x | 2,000 | 400 | -80% |
| `cat` / `read` | 20x | 40,000 | 12,000 | -70% |
| `git status` | 10x | 3,000 | 600 | -80% |
| `git diff` | 5x | 10,000 | 2,500 | -75% |
| **Total** | | **~118,000** | **~23,900** | **-80%** |

## Four Optimization Strategies

1. **Smart Filtering** - Remove noise (comments, whitespace, boilerplate)
2. **Grouping** - Aggregate similar items (files by directory, errors by type)
3. **Truncation** - Keep relevant context, cut redundancy
4. **Deduplication** - Collapse repeated log lines with counts

## Supported AI Tools

| Tool | Install | Method |
|------|---------|--------|
| **Claude Code** | `rtk init -g` | PreToolUse hook (bash) |
| **GitHub Copilot (VS Code)** | `rtk init -g --copilot` | PreToolUse hook - transparent rewrite |
| **GitHub Copilot CLI** | `rtk init -g --copilot` | PreToolUse deny-with-suggestion (CLI limitation) |
| **Cursor** | `rtk init -g --agent cursor` | preToolUse hook (hooks.json) |
| **Gemini CLI** | `rtk init -g --gemini` | BeforeTool hook |
| **Codex** | `rtk init -g --codex` | AGENTS.md + RTK.md instructions |
| **Windsurf** | `rtk init -g --agent windsurf` | .windsurfrules (project-scoped) |
| **Cline / Roo Code** | `rtk init --agent cline` | .clinerules (project-scoped) |
| **OpenCode** | `rtk init -g --opencode` | Plugin TS (tool.execute.before) |
| **OpenClaw** | `openclaw plugins install ./openclaw` | Plugin TS (before_tool_call) |
| **Pi** | `rtk init -g --agent pipi` (global) | TypeScript extension (tool_call) |
| **Hermes** | `rtk init --agent hermes` | Python plugin adapter (terminal command mutation via `rtk rewrite`) |
| **Kilo Code** | `rtk init --agent kilocode` | .kilocode/rules/rtk-rules.md (project-scoped) |
| **Google Antigravity** | `rtk init --agent antigravity` | .agents/rules/antigravity-rtk-rules.md (project-scoped) |

## Meta Commands

- `rtk gain` - Show token savings stats
- `rtk discover` - Find commands not yet optimized
- `rtk session` - Show RTK adaptation across recent sessions
- `rtk proxy <cmd>` - Raw passthrough + tracing
- `rtk verify` - Verify installation

## Global Flags

```bash
-u, --ultra-compact    # ASCII icons, inline format (extra token savings)
-v, --verbose          # Increase verbosity (-v, -vv, -vvv)
```

## Configuration

`~/.config/rtk/config.toml`:

```toml
[hooks]
exclude_commands = ["curl", "playwright"]  # skip rewrite for these

[tee]
enabled = true       # save raw output on failure (default: true)
mode = "failures"    # "failures", "always", or "never"
```

## Privacy & Telemetry

- **Telemetry disabled by default** and requires explicit opt-in
- Collects anonymous, aggregated usage metrics (command counts, token savings)
- No source code, file paths, command arguments, secrets, or personal data
- Manage via `rtk telemetry status/enable/disable/forget`

## Uninstall

```bash
rtk init -g --uninstall    # Remove hook, RTK.md, settings.json entry
cargo uninstall rtk        # Remove binary
brew uninstall rtk         # If installed via Homebrew
```

## References

- [GitHub](https://github.com/rtk-ai/rtk)
- [Website](https://www.rtk-ai.app)
- [Guide](https://www.rtk-ai.app/guide)
- License: Apache 2.0
