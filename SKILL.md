---
name: ui-layouts
description: >
  Generate creative, animated React components using the UI-Layouts component library.
  Use when: (1) Creating animated UI components (buttons, cards, modals, carousels, accordions),
  (2) Adding visual effects (blobs, sparkles, gradients, ripple effects, noise),
  (3) Building motion-rich layouts (scroll animations, sticky scroll, horizontal scroll, marquee),
  (4) Creating form components (sliders, tags input, file upload, color picker, password input),
  (5) Building overlay components (dialogs, modals, drawers), (6) Working with 3D/visual components
  (globe, mesh gradients, image reveal), (7) Building code display components, or (8) Adding
  any creative animation or visual effect to a React/Next.js project. Trigger on requests about
  creative UI, animated components, visual effects, motion design, or React component libraries.
---

# UI-Layouts Component Skill

Generate production-ready React components from the UI-Layouts library — a creative component collection for React/Next.js with Tailwind CSS and Framer Motion.

## Tech Stack

- **React 19** + TypeScript
- **Tailwind CSS** (required for all components)
- **Framer Motion** (`motion` package) for animations
- **clsx** + **tailwind-merge** for class utilities
- **pnpm** monorepo with Turborepo

## Setup

```bash
npm install motion clsx tailwind-merge
```

```tsx
// utils.ts
import { type ClassValue, clsx } from 'clsx'
import { twMerge } from 'tailwind-merge'

export function cn(...inputs: ClassValue[]) {
  return twMerge(clsx(inputs))
}
```

```tsx
// hooks/use-media-query.ts
import { useEffect, useState } from 'react'

export function useMediaQuery(query: string) {
  const [value, setValue] = useState(false)
  useEffect(() => {
    function onChange(event: MediaQueryListEvent) { setValue(event.matches) }
    const result = matchMedia(query)
    result.addEventListener('change', onChange)
    setValue(result.matches)
    return () => result.removeEventListener('change', onChange)
  }, [query])
  return value
}
```

## Component Catalog

See `references/components.md` for the full categorized list of 80+ components with URLs and usage patterns.

## Key Patterns

### Copy-paste integration
Each component is self-contained. Copy the component file into your project, install dependencies, and use it. No CLI installer needed.

### Animation approach
- Use `motion` (Framer Motion) for enter/exit animations, hover effects, scroll-linked animations
- Use CSS for simple transitions (hover states, color changes)
- Use `useMediaQuery` hook for responsive behavior

### Styling approach
- Tailwind CSS utility classes for all styling
- CSS variables for theming (light/dark mode via `.dark` class)
- `cn()` utility for conditional class merging

## Customization

All components accept standard React props plus style props. Customize via:
- Tailwind classes (className prop)
- CSS variables defined in `:root` / `.dark`
- Component-specific props (see component docs)

## Documentation

- Website: https://www.ui-layouts.com/components
- GitHub: https://github.com/ui-layouts/uilayouts
- Each component page has copyable source code and live preview
