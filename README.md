# Whizard Skills

A collection of skills for AI coding agents (Codex, Claude Code, OpenCode).

## Skills

### [awesome-design-md](./awesome-design-md/)

Leverage DESIGN.md files from the [VoltAgent/awesome-design-md](https://github.com/VoltAgent/awesome-design-md) collection to generate consistent, brand-aligned UI with AI coding agents.

#### What It Does

Each DESIGN.md is a plain-text design system document that AI agents read to understand visual style, tokens, and component patterns. This skill helps you select, integrate, and use these files to generate high-quality UI.

#### Features

- **73+ Brand Design Systems**: Stripe, Apple, Tesla, Spotify, Linear, Vercel, and more
- **Category Browsing**: AI/LLM, Developer Tools, Fintech, E-commerce, Automotive, Media
- **Style Browsing**: Dark UI, Minimal, Bold, Cinematic, Playful
- **Full Collection Catalog**: URLs and style keywords for quick lookup
- **Integration Workflow**: Step-by-step guide for adding DESIGN.md to projects

#### Included Files

| File | Purpose |
|------|---------|
| `SKILL.md` | Main instructions, brand selection guide, workflow |
| `references/collection-catalog.md` | Complete catalog of 73 brands with URLs |

#### Use Cases

```
# Build a landing page matching a specific brand
Use $awesome-design-md to help me build a landing page like Stripe

# Generate UI components with brand styling
Use $awesome-design-md to create a pricing page using the DESIGN.md design system

# Browse available design systems
Use $awesome-design-md to show me all available dark UI design systems
```

---

### [humanizer](./humanizer/)

Remove signs of AI-generated writing from text, making it sound more natural and human. Based on Wikipedia's "Signs of AI writing" guide.

#### What It Does

Scans text for 33 known AI writing patterns and rewrites them to produce natural, human-sounding prose. Includes voice calibration to match your personal writing style.

#### Features

- **33 Detected Patterns**: Content, language, style, communication, and filler patterns
- **Voice Calibration**: Provide your writing sample to match your personal style
- **Before/After Examples**: Clear examples for each pattern
- **Two-Pass Rewrite**: Initial rewrite + final audit to catch lingering AI-isms

#### Included Files

| File | Purpose |
|------|---------|
| `SKILL.md` | Main instructions, 33 patterns, workflow |
| `references/pattern-examples.md` | Detailed examples for all 33 patterns |

#### Detected Patterns

| Category | Count | Examples |
|----------|-------|----------|
| Content | 6 | Significance inflation, vague attributions, formulaic challenges |
| Language | 7 | AI vocabulary, copula avoidance, passive voice, rule of three |
| Style | 12 | Em dash overuse, boldface, emojis, title case, fragmented headers |
| Communication | 3 | Chatbot artifacts, sycophantic tone, cutoff disclaimers |
| Filler | 5 | Filler phrases, excessive hedging, generic conclusions |

#### Use Cases

```
# Basic humanization
Use $humanizer to rewrite this AI-generated text to sound more natural

# Voice calibration
Use $humanizer to match my writing style from this sample: [sample]

# Clean up ChatGPT output
Use $humanizer to remove AI patterns from this article: [text]
```

---

## Installation

Clone into your skills directory:

```bash
# Codex / Claude Code
git clone https://github.com/wizenard/whizard_skills.git ~/.codex/skills

# OpenCode
git clone https://github.com/wizenard/whizard_skills.git ~/.config/opencode/skills

# Or copy specific skills
git clone https://github.com/wizenard/whizard_skills.git /tmp/whizard_skills
cp -r /tmp/whizard_skills/awesome-design-md ~/.codex/skills/
cp -r /tmp/whizard_skills/humanizer ~/.codex/skills/
```

## License

MIT
