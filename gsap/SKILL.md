---
name: gsap
description: >
  Create professional-grade JavaScript animations using GSAP (GreenSock Animation Platform).
  Use when: (1) Animating HTML elements (fade, slide, scale, rotate, color transitions),
  (2) Creating scroll-triggered animations with ScrollTrigger, (3) Building complex
  animation sequences with Timelines, (4) Animating SVG elements (draw, morph, motion path),
  (5) Creating text animations (split text, scramble, typewriter), (6) Building draggable
  and interactive UI elements, (7) Creating page transition effects with Flip, (8) Any
  JavaScript animation task requiring high performance and cross-browser compatibility.
  Trigger on requests about animation, motion design, scroll effects, SVG animation,
  or JavaScript animation libraries.
---

# GSAP Animation Skill

Generate production-ready JavaScript animations using GSAP (GreenSock Animation Platform) — the industry standard for high-performance web animation.

## Tech Stack

- **GSAP v3.15** — framework-agnostic JavaScript animation library
- Works with React, Vue, Svelte, vanilla JS, Webflow, WordPress
- All plugins now free on npm

## Installation

```bash
npm install gsap
```

```js
import { gsap } from "gsap";
import { ScrollTrigger } from "gsap/ScrollTrigger";

gsap.registerPlugin(ScrollTrigger);
```

## Core API

### Tween — Animate a single element

```js
// Animate TO values
gsap.to(".box", { x: 100, opacity: 1, duration: 1, ease: "power2.out" });

// Animate FROM current values
gsap.from(".box", { x: -100, opacity: 0, duration: 1 });

// Set FROM-TO (start and end values)
gsap.fromTo(".box", { x: -100 }, { x: 100, duration: 1 });

// Set instant values (no animation)
gsap.set(".box", { x: 100, opacity: 1 });
```

### Timeline — Sequence multiple animations

```js
const tl = gsap.timeline({ defaults: { duration: 0.5, ease: "power2.out" } });

tl.to(".header", { y: 0, opacity: 1 })
  .to(".content", { y: 0, opacity: 1 }, "-=0.3")  // overlap by 0.3s
  .to(".footer", { y: 0, opacity: 1 }, "-=0.2");

// Control
tl.play();
tl.reverse();
tl.progress(0.5);  // jump to 50%
```

### Keyframes — Multiple states in sequence

```js
gsap.to(".box", {
  keyframes: [
    { x: 100, duration: 0.5 },
    { y: 50, duration: 0.5 },
    { rotation: 360, duration: 1 },
  ],
});
```

## Common Animations

### Fade & Slide

```js
// Fade in
gsap.from(".el", { opacity: 0, duration: 0.6 });

// Slide up
gsap.from(".el", { y: 50, opacity: 0, duration: 0.6 });

// Slide in from left
gsap.from(".el", { x: -100, opacity: 0, duration: 0.6 });
```

### Stagger — Animate multiple elements

```js
gsap.from(".list li", {
  opacity: 0,
  y: 20,
  stagger: 0.1,       // 0.1s between each
  duration: 0.5,
});

// Grid stagger
gsap.from(".grid-item", {
  opacity: 0,
  scale: 0.5,
  stagger: {
    each: 0.05,
    grid: "auto",
    from: "center",
  },
});
```

### Hover Effects

```js
gsap.to(".btn", {
  scale: 1.05,
  duration: 0.3,
  ease: "power2.out",
  paused: true,          // don't auto-play
});

// On hover
document.querySelector(".btn").addEventListener("mouseenter", () => {
  tl.play();
});
document.querySelector(".btn").addEventListener("mouseleave", () => {
  tl.reverse();
});
```

## ScrollTrigger — Scroll-Driven Animations

```js
import { ScrollTrigger } from "gsap/ScrollTrigger";
gsap.registerPlugin(ScrollTrigger);

// Basic scroll animation
gsap.to(".box", {
  scrollTrigger: {
    trigger: ".box",
    start: "top 80%",     // when top of box hits 80% of viewport
    end: "top 20%",
    scrub: true,          // link animation to scroll position
  },
  x: 200,
  rotation: 360,
});

// Pin element during scroll
gsap.to(".panel", {
  scrollTrigger: {
    trigger: ".panel",
    pin: true,            // pin during scroll
    scrub: 1,             // smooth scrub (1s lag)
  },
  x: -1000,
});

// Batch animations
ScrollTrigger.batch(".item", {
  onEnter: (elements) => gsap.to(elements, { opacity: 1, y: 0, stagger: 0.1 }),
  start: "top 85%",
});
```

## Eases

| Ease | Effect |
|------|--------|
| `"none"` | Linear |
| `"power1.out"` | Gentle deceleration |
| `"power2.out"` | Standard deceleration (most common) |
| `"power3.out"` | Strong deceleration |
| `"power4.out"` | Dramatic deceleration |
| `"back.out(1.7)"` | Overshoot then settle |
| `"bounce.out"` | Bounce effect |
| `"elastic.out(1, 0.3)"` | Elastic spring |
| `"expo.out"` | Exponential deceleration |
| `"steps(5)"` | stepped animation |

## Plugins

| Plugin | Purpose |
|--------|---------|
| `ScrollTrigger` | Scroll-driven animations, pinning |
| `ScrollSmoother` | Smooth scrolling (requires ScrollTrigger) |
| `SplitText` | Split text into chars/words/lines for animation |
| `Flip` | Animate between layout states |
| `Draggable` | Drag & drop with physics |
| `Observer` | Normalize scroll/touch/pointer events |
| `DrawSVGPlugin` | Animate SVG stroke drawing |
| `MorphSVGPlugin` | Morph between SVG shapes |
| `MotionPathPlugin` | Animate along an SVG path |
| `TextPlugin` | Typewriter text replacement |
| `ScrambleTextPlugin` | Scrambled text reveal |

## React Integration

```jsx
import { useGSAP } from "@gsap/react";
import { gsap } from "gsap";

function App() {
  useGSAP(() => {
    gsap.to(".box", { x: 100, duration: 1 });
  }, { scope: containerRef }); // cleanup automatic

  return <div ref={containerRef}><div className="box" /></div>;
}
```

## Utility Methods

```js
gsap.utils.toArray(".item");      // Nodelist → Array
gsap.utils.clamp(0, 100, value); // clamp value
gsap.utils.random(-50, 50);      // random number
gsap.utils.snap(10, value);      // snap to grid
gsap.utils.mapRange(0, 1, 0, 100, value); // remap range
```

## Cleanup

```js
// Kill all animations on elements
gsap.killTweensOf(".box");

// Kill everything
gsap.killTweensOf("*");

// Context-based cleanup (React)
const ctx = gsap.context(() => {
  gsap.to(".box", { x: 100 });
}, containerRef);

ctx.revert(); // clean up all animations in this context
```

## Documentation

- Website: https://gsap.com/docs/v3/
- GitHub: https://github.com/greensock/GSAP
- Cheatsheet: https://gsap.com/cheatsheet
- AI Skills: https://github.com/greensock/gsap-skills
