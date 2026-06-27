---
name: awesome-design-md
description: Use when users need to work with DESIGN.md files for AI-driven UI generation. Covers: (1) Selecting appropriate DESIGN.md from the VoltAgent/awesome-design-md collection for a brand/style, (2) Integrating DESIGN.md into projects for AI agents to generate consistent UI, (3) Understanding DESIGN.md structure and tokens, (4) Creating custom DESIGN.md files following the Stitch specification. Trigger on requests about design systems, UI consistency, vibe coding, or brand-specific UI generation.
---

# Awesome Design MD

## Overview

Leverage DESIGN.md files from the [VoltAgent/awesome-design-md](https://github.com/VoltAgent/awesome-design-md) collection to generate consistent, brand-aligned UI with AI coding agents. Each DESIGN.md is a plain-text design system document that AI agents read to understand visual style, tokens, and component patterns.

## Quick Start

1. Browse the collection at [getdesign.md](https://getdesign.md) or the GitHub repo
2. Copy the desired `DESIGN.md` into your project root
3. Tell your AI agent: "Use the DESIGN.md to build [your page/component]"

## Selecting a DESIGN.md

### By Category

| Category | Brands | Style Keywords |
|----------|--------|----------------|
| AI/LLM | Claude, Ollama, Mistral, Replicate | Warm editorial, terminal-first, minimalism |
| Developer Tools | Cursor, Vercel, Linear, Supabase | Dark theme, precision, code-forward |
| Fintech | Stripe, Coinbase, Revolut, Wise | Purple gradients, trust-focused, clean |
| E-commerce | Apple, Nike, Shopify, Airbnb | Premium whitespace, photography-driven |
| Automotive | Tesla, Ferrari, BMW, Lamborghini | Cinematic, stark, luxury surfaces |
| Media | Spotify, Pinterest, The Verge | Vibrant accents, image-first |

### By Style

- **Dark UI**: Ollama, Cursor, ElevenLabs, Supabase, Resend
- **Minimal/White**: Apple, Vercel, Cal.com, IBM
- **Bold/Colorful**: Figma, Miro, Zapier, Airbnb
- **Cinematic**: Tesla, SpaceX, Ferrari, Bugatti

## DESIGN.md Structure

Each file follows the [Stitch DESIGN.md specification](https://stitch.withgoogle.com/docs/design-md/specification/):

| Section | Purpose |
|---------|---------|
| Visual Theme & Atmosphere | Mood, density, philosophy |
| Color Palette & Roles | Semantic names + hex + function |
| Typography Rules | Font families, hierarchy table |
| Component Stylings | Buttons, cards, inputs with states |
| Layout Principles | Spacing scale, grid, whitespace |
| Depth & Elevation | Shadow system, surfaces |
| Do's and Don'ts | Guardrails and anti-patterns |
| Responsive Behavior | Breakpoints, touch targets |
| Agent Prompt Guide | Quick reference for prompts |

## Integration Workflow

### Step 1: Choose a Brand

```
User: "Build me a landing page like Stripe"
→ Fetch DESIGN.md from getdesign.md/stripe/design-md
→ Copy to project root
```

### Step 2: Configure AI Agent

Add to your project's `AGENTS.md` or agent config:

```markdown
## Design System

Read DESIGN.md in the project root for all UI generation.
Apply design tokens, colors, typography, and component styles from it.
```

### Step 3: Generate UI

Prompt examples:

```markdown
# Basic
"Build a pricing page using the DESIGN.md design system"

# Specific component
"Create a hero section following the DESIGN.md color palette and typography"

# Full page
"Generate a complete landing page with nav, hero, features, and footer
using the design tokens from DESIGN.md"
```

## Custom DESIGN.md

To create your own DESIGN.md for a brand not in the collection:

1. Analyze the target website's CSS (colors, fonts, spacing)
2. Follow the [Stitch specification](https://stitch.withgoogle.com/docs/design-md/specification/)
3. Include all 9 sections from the structure table above
4. Test by having an AI agent generate UI from it

## Requesting New Designs

Submit requests at [getdesign.md/request](https://getdesign.md/request) for websites not yet in the collection.

## References

- [Stitch DESIGN.md Spec](https://stitch.withgoogle.com/docs/design-md/specification/)
- [VoltAgent/awesome-design-md](https://github.com/VoltAgent/awesome-design-md)
- [getdesign.md](https://getdesign.md)
