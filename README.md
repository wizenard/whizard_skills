# Whizard Skills

A collection of skills for AI coding agents (Codex, Claude Code, OpenCode).

## Skills

### [awesome-design-md](./awesome-design-md/)

Leverage DESIGN.md files from the [VoltAgent/awesome-design-md](https://github.com/VoltAgent/awesome-design-md) collection to generate consistent, brand-aligned UI with AI coding agents.

- 73+ brand design systems (Stripe, Apple, Tesla, Spotify, etc.)
- Browse by category: AI/LLM, Developer Tools, Fintech, E-commerce, Automotive, Media
- Browse by style: Dark UI, Minimal, Bold, Cinematic
- Includes full collection catalog with URLs and style keywords

```
Use $awesome-design-md to help me build a landing page like Stripe
```

### [humanizer](./humanizer/)

Remove signs of AI-generated writing from text. Based on Wikipedia's "Signs of AI writing" guide.

- 33 detected patterns (content, language, style, communication, filler)
- Voice calibration: match your personal writing style from samples
- Before/after examples for each pattern
- Two-pass rewrite with final audit

```
Use $humanizer to rewrite this AI-generated text to sound more natural
```

## Installation

Clone into your skills directory:

```bash
# Codex / Claude Code
git clone https://github.com/wizenard/whizard_skills.git ~/.codex/skills

# Or copy specific skills
git clone https://github.com/wizenard/whizard_skills.git /tmp/whizard_skills
cp -r /tmp/whizard_skills/awesome-design-md ~/.codex/skills/
cp -r /tmp/whizard_skills/humanizer ~/.codex/skills/
```

## License

MIT
