---
name: react-bits
description: >
  Add animated React components using the react-bits library — 130+ free, customizable
  animations for text, backgrounds, and UI. Use when: (1) Creating text animation effects
  (blur text, split text, wave text, glitch text), (2) Adding animated backgrounds (gradients,
  particles, waves, noise), (3) Building animated UI components (cards, buttons, modals),
  (4) Creating visual effects for landing pages or portfolios, (5) Adding motion to any React
  project with minimal dependencies. Trigger on requests about React animations, animated
  components, text effects, background animations, or creative UI elements.
---

# react-bits Animation Skill

Generate animated React components using react-bits — the largest library of creative React animations (130+ components).

## Tech Stack

- **React 16+** / Next.js
- **CSS** or **Tailwind CSS** (4 variants per component)
- **TypeScript** supported (JS/TS variants)

## Installation

```bash
# Via shadcn (recommended)
npx shadcn@latest add @react-bits/BlurText-TS-TW

# Via jsrepo
npx jsrepo add reactbits/text-animations/BlurText
```

Or copy-paste directly from the docs: https://reactbits.dev

## Component Variants

Each component comes in 4 variants:

| Variant | Style | Language |
|---------|-------|----------|
| JS-CSS | Plain CSS | JavaScript |
| JS-TW | Tailwind | JavaScript |
| TS-CSS | Plain CSS | TypeScript |
| TS-TW | Tailwind | TypeScript |

## Component Categories

### Text Animations

| Component | Description |
|-----------|-------------|
| BlurText | Text appears with blur effect |
| SplitText | Characters animate individually |
| WaveText | Wave motion across text |
| GlitchText | Glitch distortion effect |
| ScrollRevealText | Reveal on scroll |
| EncryptedText | Decryption animation |
| RotatingText | Rotating word display |
| GradientText | Animated gradient on text |
| LetterSwap | Swap letters animation |
| FadingText | Fade in/out effect |

### Backgrounds

| Component | Description |
|-----------|-------------|
| GradientAnimation | Animated gradient background |
| ParticlesBg | Floating particles |
| WavesBg | Animated wave patterns |
| NoiseBg | Animated noise texture |
| MeshGradient | Smooth mesh gradient |
| AnimatedGrid | Moving grid pattern |
| BokehBg | Bokeh light effect |
| BubbleBg | Floating bubbles |
| HeatMap | Animated heat map |
| LavaLamp | Lava lamp effect |

### Animations

| Component | Description |
|-----------|-------------|
| AnimatedCard | Card with hover animation |
| FloatingElement | Floating motion effect |
| MorphingShape | Shape morphing animation |
| ParallaxLayer | Parallax scrolling |
| ElasticButton | Button with elastic effect |
| RippleEffect | Click ripple animation |
| PulseAnimation | Pulsing glow effect |
| RotateOnHover | Rotate on mouse hover |
| ScaleOnHover | Scale on hover |
| SlideIn | Slide in animation |

### Components

| Component | Description |
|-----------|-------------|
| AnimatedModal | Modal with animations |
| Accordion | Animated expand/collapse |
| Tabs | Animated tab switching |
| Toast | Animated notifications |
| Tooltip | Animated tooltips |
| Dropdown | Animated dropdown menu |
| Carousel | Animated carousel |
| Stepper | Step progress indicator |
| Toggle | Animated toggle switch |
| ProgressBar | Animated progress bar |

## Usage Examples

### Text Animation

```tsx
import { BlurText } from "react-bits";

function Hero() {
  return (
    <BlurText
      text="Welcome to My Site"
      delay={100}
      className="text-4xl font-bold"
    />
  );
}
```

### Background Animation

```tsx
import { GradientAnimation } from "react-bits";

function HeroSection() {
  return (
    <div className="relative h-screen">
      <GradientAnimation className="absolute inset-0" />
      <div className="relative z-10">
        <h1>Content here</h1>
      </div>
    </div>
  );
}
```

### Scroll Animation

```tsx
import { ScrollRevealText } from "react-bits";

function Section() {
  return (
    <ScrollRevealText
      text="Scroll to reveal this text"
      className="text-2xl"
    />
  );
}
```

## Creative Tools

react-bits also provides free online tools:

| Tool | URL | Description |
|------|-----|-------------|
| Background Studio | https://reactbits.dev/tools | Create & export animated backgrounds |
| Shape Magic | https://reactbits.dev/tools | Create inner rounded corners |
| Texture Lab | https://reactbits.dev/tools | Apply effects to images/videos |

## Documentation

- Website: https://reactbits.dev
- GitHub: https://github.com/DavidHDev/react-bits
- Vue version: https://vue-bits.dev
- Svelte version: https://sveltebits.xyz
