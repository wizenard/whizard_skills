# GSAP Plugin Reference

## Core

| Plugin | CDN | Description |
|--------|-----|-------------|
| GSAP Core | Yes | Tween, Timeline, CSS, Easing |
| ScrollTrigger | Yes | Scroll-driven animations, pinning |
| ScrollSmoother | Yes | Smooth scrolling (requires ScrollTrigger) |
| ScrollTo | Yes | Smooth scroll to position |

## Text

| Plugin | CDN | Description |
|--------|-----|-------------|
| SplitText | Yes | Split text into chars/words/lines |
| ScrambleText | Yes | Scrambled text reveal effect |
| TextPlugin | Yes | Typewriter text replacement |

## SVG

| Plugin | CDN | Description |
|--------|-----|-------------|
| DrawSVG | Yes | Animate SVG stroke drawing |
| MorphSVG | Yes | Morph between SVG shapes |
| MotionPath | Yes | Animate along SVG path |
| MotionPathHelper | Yes | Visual MotionPath editor |

## UI

| Plugin | CDN | Description |
|--------|-----|-------------|
| Flip | Yes | Animate between layout states |
| Draggable | Yes | Drag & drop with physics |
| Inertia | Yes | Momentum-based throwing |
| Observer | Yes | Normalize scroll/touch/pointer events |

## Physics

| Plugin | CDN | Description |
|--------|-----|-------------|
| Physics2D | Yes | Velocity, angle, friction |
| PhysicsProps | Yes | Physics-based property animation |

## Eases

| Ease | Description |
|------|-------------|
| none | Linear |
| power1 | Gentle |
| power2 | Standard (most common) |
| power3 | Strong |
| power4 | Dramatic |
| back | Overshoot |
| bounce | Bounce effect |
| circ | Circular |
| elastic | Spring |
| expo | Exponential |
| sine | Sinusoidal |
| steps(n) | Stepped |

## Frameworks

| Framework | Package | Notes |
|-----------|---------|-------|
| React | `@gsap/react` | useGSAP() hook with auto-cleanup |
| Vue | `gsap` | Use in mounted/mounting hooks |
| Svelte | `gsap` | Use in onMount |
| Vanilla JS | `gsap` | Direct usage |
| Webflow | GSAP via CDN | Webflow-specific setup |
