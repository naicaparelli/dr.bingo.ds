---
name: dr-bingo-bet-design
description: Use this skill to generate well-branded interfaces and assets for Dr. Bingo Bet (Brazilian online casino / bingo platform), either for production or throwaway prototypes/mocks/slides. Contains design guidelines, color tokens, typography, spacing, effects, and reference components in the dark neon-violet night-arcade style.
user-invocable: true
---

Read the `README.md` file within this skill, and explore the other available files:

- `colors_and_type.css` — all CSS variables (colors, gradients, type, spacing, radius, shadow, glow, blur, motion) plus semantic type classes
- `preview/` — 23 design-system cards showing the full foundation visually
- `assets/` — brand reference: cover vectors, product screenshot

If creating visual artifacts (slides, mocks, throwaway prototypes, landing pages, ads), link or copy `colors_and_type.css` and build against the tokens. The aesthetic is **dark-first, violet-and-magenta with neon glow**. Keep it festive, rounded, and high-contrast.

Key rules:
- One glow per screen. Accent gradients are semantic (magenta=action, gold=money, lime=win).
- Luckiest Guy for display only; Inter everything else; mono for digits that matter.
- Pills over squares. Protection gradients over any text-on-image.
- Portuguese-Brasil copy; ALL-CAPS imperative CTAs.

If the user invokes this skill without other guidance, ask what they want to build (marketing page, in-app screen, promo banner, slide deck), ask a few scoping questions, and then act as an expert designer producing HTML artifacts or production code. Always reference the preview cards before inventing new styles.
