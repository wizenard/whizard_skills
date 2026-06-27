---
name: matt-pocock-engineering
description: Summary of Matt Pocock's engineering skills for AI agents. Covers the core principles, skill categories (Engineering, Productivity, Misc), invocation types (User-invoked vs Model-invoked), and key skills like /grill-me, /tdd, /diagnosing-bugs, /improve-codebase-architecture. Use when: (1) Understanding professional AI-assisted engineering workflows, (2) Learning how to align with agents before coding, (3) Building domain models and shared language, (4) Applying TDD and debugging disciplines. Trigger on requests about engineering best practices, agent alignment, domain modeling, or codebase architecture.
---

# Matt Pocock Engineering Skills

## Overview

A collection of agent skills from [mattpocock/skills](https://github.com/mattpocock/skills) (148k+ stars) designed for professional engineering — not vibe coding. Skills are small, composable, and model-agnostic, based on decades of engineering experience.

## Core Philosophy

Solve four common failure modes in AI-assisted development:

| Problem | Solution | Key Skills |
|---------|----------|------------|
| Agent didn't do what you want | Deep alignment sessions | `/grill-me`, `/grill-with-docs` |
| Agent is too verbose | Shared domain language | `CONTEXT.md`, `/domain-modeling` |
| Code doesn't work | Feedback loops | `/tdd`, `/diagnosing-bugs` |
| Built a ball of mud | Code design discipline | `/improve-codebase-architecture`, `/codebase-design` |

## Skill Categories

### Engineering (Daily Code Work)

**User-invoked** (you type the command):

| Skill | Purpose |
|-------|---------|
| `/ask-matt` | Router — asks which skill fits your situation |
| `/grill-with-docs` | Alignment + domain model building + ADR updates |
| `/triage` | Issue state machine (needs-triage → ready-for-afk) |
| `/improve-codebase-architecture` | Scan codebase for deepening opportunities, HTML report |
| `/setup-matt-pocock-skills` | First-time config (issue tracker, labels, docs location) |
| `/to-issues` | Break plans into vertical-slice issues |
| `/to-prd` | Synthesize conversation into a PRD |
| `/prototype` | Build throwaway prototypes for design exploration |

**Model-invoked** (agent can auto-select):

| Skill | Purpose |
|-------|---------|
| `/tdd` | Red-green-refactor loop, one vertical slice at a time |
| `/diagnosing-bugs` | Reproduce → minimize → hypothesize → fix → regression-test |
| `/domain-modeling` | Build and sharpen project domain model |
| `/codebase-design` | Deep module design: lots of behavior behind small interface |

### Productivity (General Workflow)

**User-invoked**:

| Skill | Purpose |
|-------|---------|
| `/grill-me` | Relentless interview until all decision branches resolved |
| `/handoff` | Compact conversation into handoff document |
| `/teach` | Multi-session teaching with stateful workspace |
| `/writing-great-skills` | Reference for writing/editing skills well |

**Model-invoked**:

| Skill | Purpose |
|-------|---------|
| `/grilling` | Reusable interview loop behind grill-me and grill-with-docs |

### Misc (Rarely Used)

- `/git-guardrails-claude-code` — Block dangerous git commands
- `/setup-pre-commit` — Husky + lint-staged + Prettier
- `/scaffold-exercises` — Create exercise directory structures
- `/migrate-to-shoehorn` — Test type assertion migration

## Invocation Rules

- **User-invoked**: Only triggered when you type the command; exists to orchestrate
- **Model-invoked**: Can be triggered by you OR automatically by the agent when task fits
- A user-invoked skill may invoke model-invoked skills, but **never another user-invoked skill**

## Key Concepts

### 1. Alignment Before Coding

Before any change, run `/grill-me` or `/grill-with-docs` to ensure you and the agent are aligned. This is the single most important practice.

### 2. Shared Domain Language (CONTEXT.md)

Create a `CONTEXT.md` in your project root with domain-specific terminology. This:
- Reduces verbosity (20 words → 1)
- Improves variable/function/file naming consistency
- Saves tokens on thinking

Example:
- **BEFORE**: "There's a problem when a lesson inside a section of a course is made 'real'"
- **AFTER**: "There's a problem with the materialization cascade"

### 3. Red-Green-Refactor (TDD)

Always write a failing test first, then make it pass. This gives the agent consistent feedback and produces better code.

### 4. Code Design Discipline

Run `/improve-codebase-architecture` every few days. Focus on:
- Deep modules (lots of behavior, small interface)
- Clean seams for placement
- Testability through the interface

## Installation

```bash
# Via skills.sh installer
npx skills@latest add mattpocock/skills

# Or clone directly
git clone https://github.com/mattpocock/skills.git /tmp/mattpocock-skills
cp -r /tmp/mattpocock-skills/skills/* ~/.codex/skills/
```

## Quick Reference

```
# Before any change
/grill-with-docs    → Align + build domain model

# During implementation
/tdd                → Write tests first
/diagnosing-bugs    → When code breaks

# Maintenance
/improve-codebase-architecture  → Every few days
/domain-modeling    → Sharpen terminology
```

## References

- **Repository**: [github.com/mattpocock/skills](https://github.com/mattpocock/skills)
- **Newsletter**: [aihero.dev](https://www.aihero.dev/s/skills-newsletter) (~60k subscribers)
- **Skills installer**: [skills.sh](https://skills.sh/mattpocock/skills)
- **Total TypeScript**: Matt Pocock's main project
