# Portfolio UI Design Spec (Space + Galaxy)

## 1) Visual Direction
A cinematic night-sky identity with layered stars, nebula bloom, and moving galaxy haze.
Mood keywords: atmospheric, artistic, futuristic, intimate.

## 2) Typography System
Display face: DM Serif Display
Body/UI face: Sora

Type scale:
- Display XL: clamp(2.2rem, 6vw, 5rem), line-height 0.95, weight 400
- Heading L: 2rem, line-height 1.1, weight 400
- Heading M: 1.2rem to 1.4rem, line-height 1.2, weight 600
- Body: 1rem, line-height 1.7, weight 400
- Small UI: 0.82rem to 0.9rem, uppercase optional for labels

Usage:
- Hero title uses display scale.
- Section titles use Heading L.
- Navigation and chips use small UI scale.

## 3) Color Palette (Design Tokens)
Core tokens in CSS :root:
- --bg: #04030a
- --bg-soft: #100a1f
- --text: #f2ebff
- --muted: #b9a8d6
- --accent-magenta: #cf82ff
- --accent-cyan: #66e1ff
- --accent-peach: #ffb899
- --card: #130d24
- --line: #332457

Semantic usage:
- Primary action gradient: magenta -> peach
- Accent links/kickers: cyan
- Borders/dividers: line
- Panel/card surface: card

## 4) Spacing Scale
Tokens:
- --space-1: 0.25rem
- --space-2: 0.5rem
- --space-3: 0.75rem
- --space-4: 1rem
- --space-5: 1.5rem
- --space-6: 2rem
- --space-7: 3rem
- --space-8: 4rem

Layout rhythm:
- Section to section spacing: 2.5rem+
- Card internal padding: 1rem to 1.4rem
- Hero top spacing: 4rem desktop, 2rem mobile

## 5) Radius + Elevation
Radius tokens:
- --radius-sm: 10px
- --radius-md: 16px
- --radius-lg: 20px

Elevation token:
- --shadow: 0 18px 40px rgba(0, 0, 0, 0.38)

## 6) Reusable Components
Buttons:
- .btn base with pill radius and transition
- .btn.primary for CTA gradient
- .btn.ghost for secondary action

Panels:
- .panel for grouped sections
- .panel-head for heading + action link

Cards:
- .track-card with kicker, title, body copy, metadata chips

Media tiles:
- .photo with gradient overlays and label placement

## 7) Background Effects System
Layer stack:
1. Base sky gradient on body
2. .cosmos container
3. .stars-a / .stars-b / .stars-c for depth parallax
4. .nebula-1 / .nebula-2 for drifting cloud glow
5. .galaxy-band for milky-way style haze
6. .meteor-a / .meteor-b for periodic streaks
7. .grain for subtle film texture

Motion:
- Stars drift at three speeds
- Nebula shifts slowly in opposite directions
- Galaxy band glides continuously
- Meteors trigger intermittently
- Pointer parallax updates --parallax-x and --parallax-y

## 8) Accessibility + Performance
- Supports reduced motion with prefers-reduced-motion.
- All decorative layers are pointer-events none and aria-hidden.
- Keep heavy blur layers to two clouds to avoid mobile jank.

## 9) Implementation Map
Current files:
- public/index.html: background layer structure + content sections
- public/styles.css: tokens, components, animations, responsive rules
- public/main.js: reveal animation + pointer parallax token updates

## 10) Next Component Additions (Optional)
- Reusable audio player card with waveform preview.
- Full-screen lightbox for photography.
- Sticky section timeline for releases.
