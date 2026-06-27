# react-bits Component Reference

## Text Animations (10+)

| Component | Variant | Description |
|-----------|---------|-------------|
| BlurText | Text | Text appears with blur-to-focus effect |
| SplitText | Text | Each character animates independently |
| WaveText | Text | Wave motion across characters |
| GlitchText | Text | Glitch/distortion effect |
| ScrollRevealText | Text | Reveal text on scroll position |
| EncryptedText | Text | Decryption/scramble reveal |
| RotatingText | Text | Rotating word carousel |
| GradientText | Text | Animated color gradient |
| LetterSwap | Text | Letter swap transition |
| FadingText | Text | Fade in/out effect |

## Backgrounds (10+)

| Component | Variant | Description |
|-----------|---------|-------------|
| GradientAnimation | Background | Smooth animated gradient |
| ParticlesBg | Background | Floating particle system |
| WavesBg | Background | Animated wave patterns |
| NoiseBg | Background | Animated noise/grain texture |
| MeshGradient | Background | CSS mesh gradient |
| AnimatedGrid | Background | Moving grid lines |
| BokehBg | Background | Bokeh light orbs |
| BubbleBg | Background | Floating bubbles |
| HeatMap | Background | Animated heat map |
| LavaLamp | Background | Lava lamp blobs |

## Animations (10+)

| Component | Variant | Description |
|-----------|---------|-------------|
| AnimatedCard | Animation | Card with entrance animation |
| FloatingElement | Animation | Continuous float motion |
| MorphingShape | Animation | Shape morphing transition |
| ParallaxLayer | Animation | Parallax scroll effect |
| ElasticButton | Button | Elastic bounce on click |
| RippleEffect | Interaction | Material-style ripple |
| PulseAnimation | Effect | Pulsing glow/heartbeat |
| RotateOnHover | Interaction | 3D rotate on hover |
| ScaleOnHover | Interaction | Scale transform on hover |
| SlideIn | Animation | Slide in from direction |

## Components (10+)

| Component | Variant | Description |
|-----------|---------|-------------|
| AnimatedModal | UI | Modal with enter/exit animation |
| Accordion | UI | Expand/collapse with animation |
| Tabs | UI | Animated tab switching |
| Toast | UI | Animated notification popup |
| Tooltip | UI | Animated tooltip |
| Dropdown | UI | Animated dropdown menu |
| Carousel | UI | Animated image carousel |
| Stepper | UI | Step progress with animation |
| Toggle | UI | Animated toggle switch |
| ProgressBar | UI | Animated progress indicator |

## Installation Commands

```bash
# shadcn
npx shadcn@latest add @react-bits/<Component>-<Variant>

# Examples
npx shadcn@latest add @react-bits/BlurText-TS-TW
npx shadcn@latest add @react-bits/GradientAnimation-JS-CSS

# jsrepo
npx jsrepo add reactbits/text-animations/BlurText
npx jsrepo add reactbits/backgrounds/GradientAnimation
```

## Props Common to All Components

| Prop | Type | Description |
|------|------|-------------|
| className | string | Custom CSS classes |
| style | object | Inline styles |
| children | ReactNode | Child elements |
