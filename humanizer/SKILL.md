---
name: humanizer
description: Remove signs of AI-generated writing from text to make it sound more natural and human. Use when: (1) Rewriting AI-generated content to remove obvious AI patterns, (2) Editing text that sounds robotic or formulaic, (3) Matching a specific writing voice from sample text, (4) Cleaning up ChatGPT/Claude output for publication. Trigger on requests about humanizing text, removing AI tone, making writing sound natural, or voice calibration.
---

# Humanizer

## Overview

Rewrite AI-generated text to remove 33 known AI writing patterns and produce natural, human-sounding prose. Based on Wikipedia's "Signs of AI writing" guide.

## Quick Start

```
Please humanize this text:
[your AI-generated text here]
```

## Voice Calibration

Provide 2-3 paragraphs of your own writing first, then the text to humanize:

```
Here's a sample of my writing for voice matching:
[your writing sample]

Now humanize this text:
[AI text to humanize]
```

## 33 Patterns to Remove

### Content Patterns (1-6)

1. **Significance inflation** - "marking a pivotal moment" → state facts directly
2. **Notability name-dropping** - "cited in NYT, BBC" → use specific context
3. **Superficial -ing analyses** - "symbolizing... reflecting..." → remove or add sources
4. **Promotional language** - "nestled within the breathtaking" → plain description
5. **Vague attributions** - "Experts believe" → cite specific sources
6. **Formulaic challenges** - "Despite challenges... continues to thrive" → specific facts

### Language Patterns (7-13)

7. **AI vocabulary** - "actually, additionally, testament, landscape, showcasing" → simpler words
8. **Copula avoidance** - "serves as, features, boasts" → "is, has"
9. **Negative parallelisms** - "It's not just X, it's Y" → state the point directly
10. **Rule of three** - "innovation, inspiration, and insights" → natural count
11. **Synonym cycling** - "protagonist... main character... central figure" → pick one
12. **False ranges** - "from the Big Bang to dark matter" → list directly
13. **Passive voice** - "No configuration file needed" → name the actor

### Style Patterns (14-19, 26-33)

14. **Em/en dashes** - Cut: use periods, commas, colons, or parentheses
15. **Boldface overuse** - "**OKRs**, **KPIs**" → "OKRs, KPIs"
16. **Inline-header lists** - "**Performance:** Performance improved" → prose
17. **Title Case Headings** - "Strategic Negotiations" → "Strategic negotiations"
18. **Emojis** - Remove all emojis
19. **Curly quotes** - Use straight quotes
26. **Hyphenated word pairs** - "cross-functional, data-driven" → drop hyphens
27. **Persuasive authority tropes** - "At its core, what matters is..." → state directly
28. **Signposting announcements** - "Let's dive in" → start with content
29. **Fragmented headers** - "## Performance" + "Speed matters." → let heading work
30. **Diff-anchored writing** - "This function was added to replace..." → describe what it does
31. **Manufactured punchlines** - "It had no preference. No prior." → varied sentences
32. **Aphorism formulas** - "Symmetry is the language of trust" → actual claim
33. **Conversational rhetorical openers** - "Honestly? It depends..." → remove setup

### Communication Patterns (20-22)

20. **Chatbot artifacts** - "I hope this helps! Let me know if..." → remove
21. **Cutoff disclaimers** - "While details are limited..." → find sources or remove
22. **Sycophantic tone** - "Great question! You're absolutely right!" → respond directly

### Filler and Hedging (23-25)

23. **Filler phrases** - "In order to" → "To"; "Due to the fact that" → "Because"
24. **Excessive hedging** - "could potentially possibly" → "may"
25. **Generic conclusions** - "The future looks bright" → specific plans or facts

## Workflow

1. Scan text for all 33 patterns
2. Rewrite to remove identified patterns
3. Run final "obviously AI generated" audit
4. Second rewrite pass to catch lingering AI-isms

## References

- [Wikipedia: Signs of AI writing](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing)
- [WikiProject AI Cleanup](https://en.wikipedia.org/wiki/Wikipedia:WikiProject_AI_Cleanup)
