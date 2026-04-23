# Dr. Bingo Bet — Design System

> Visual foundation, tokens, and UI components for **Dr. Bingo Bet**, a Brazilian online casino / bingo platform featuring the smiling "Dr. Bingo" host mascot.

Night-arcade palette (deep violet → electric magenta), festive display type (Luckiest Guy) paired with Inter for UI. The vibe is **vibrant, celebratory, rewarding** — lots of gradient, neon glow, and generous rounded corners.

---

## Sources consulted

| Source | Where | Notes |
|---|---|---|
| Figma file | `canvas.fig` (mounted VFS) | 2 pages: `/Text` (13 text-style frames) and `/Cover` (1 hero frame). Contains text styles, fill colors, and the cover composition (wordmark + violet gradient hero). |
| Product screenshot | `assets/product-home-screenshot.jpeg` | Desktop home: top bar, filter tabs, game carousel, "Mais Jogados" & "Favoritos" rails, sticky bottom task-bar (Missão Diária, Torneios, Promoções, Club VIP, Coletar). |

No codebase was attached. Components below are recreated from the Figma text styles + color tokens, with the product screenshot as visual reference for high-level elements not in Figma.

---

## Index — what's in this project

```
colors_and_type.css       All CSS variables + semantic type classes
README.md                 (you are here)
SKILL.md                  Agent-skill manifest for reuse
assets/
  cover-vector-1.svg      copied from /Cover
  cover-vector-2.svg      copied from /Cover
  product-home-screenshot.jpeg
preview/                  Design-system cards (registered for the DS tab)
  brand-logo.html
  iconography.html
  color-violet.html · color-neutrals.html · color-accents.html
  color-semantic.html · gradients.html
  type-display.html · type-headings.html · type-body.html
  type-labels-mono.html · type-weights.html
  spacing-scale.html · radius.html
  effects-glow.html · effects-shadows.html · stroke-opacity.html
  components-buttons.html · components-tags.html
  components-inputs.html · components-tiles.html
  components-navigation.html · components-hero.html
```

---

## Content Fundamentals

**Language:** Portuguese (Brasil). Primary market is Brazil.

**Tone:** Energetic, celebratory, direct. Short imperative CTAs in ALL-CAPS ("JOGAR AGORA", "DEPÓSITO", "COLETAR", "VER TODOS"). Headings use display type for excitement. Body copy is informative and friendly but rarely chatty.

**Casing:** 
- Display / marquee headlines → Sentence case or all-caps (font-dependent; Luckiest Guy is decorative caps)
- Section headings → Sentence case ("Mais Jogados", "Favoritos")
- Labels, tags, buttons → ALL-CAPS with +4% letter-spacing
- Body → Sentence case

**Pronouns:** Second person "você" implicit; copy addresses the player directly but rarely uses literal "você". Example: "Ganhe pontos a cada aposta", "Jogue o novo Pachinko 3".

**Emoji:** Sparingly in UI chrome (🔥 hot, ⭐ favorites, ★ VIP, 🎉 wins). Never in body text. The "Dr. Bingo" host character illustration fills the mascot role.

**Numbers / currency:** Always `R$` with dot-thousands + comma-decimal (`R$ 321.434,20`). Multipliers as `× 1,85`. Timers `01m 30s` or `01:23:45` in mono.

**Example copy seen in product:** "Lançamento oficial em abril", "Jogue agora Pachinko 3", "Um jogo exclusivo Dr. Bingo", "Baixe agora no seu celular", "Mais Jogados", "Favoritos", "Ver todos (50)", "Missão Diária", "Torneios", "Promoções", "Club VIP", "Coletar".

---

## Visual Foundations

**Colors.** Monochromatic violet spine (`#0D051E` → `#F3E6FA`) carries 90% of the UI. Accents fire off it in three temperatures:
- Hot — magenta/pink for primary CTAs and selected states
- Rich — gold/orange for money, deposit, jackpot  
- Fresh — lime/green for wins and the "Coletar" reward moment

**Type.** Luckiest Guy (display) provides the party energy — reserved for the wordmark and festive headlines. Inter does everything else, weighted from 400 to 900. Labels ship ALL-CAPS with +4% tracking. A mono face (JetBrains Mono) handles odds, timers, and currency for a tabular feel.

**Spacing.** 4-point scale, biased toward the 12–24 range. Hero paddings go bigger (42–68 from Figma). Cards have ~22px inner padding.

**Backgrounds.** Solid `#0D051E` base. Hero and feature areas use the `grad-violet` or `grad-cover` (`#AB00B9 → #3B00CC`) gradients, often overlaid with radial highlight glows (gold + magenta blobs at 25% opacity, `mix-blend-mode: screen`). Game imagery is full-bleed, always overlaid with a bottom protection gradient so titles read.

**Animation.** Smooth ease-out for most motion (`cubic-bezier(.22,1,.36,1)`). CTAs get a pop ease with a slight overshoot (`cubic-bezier(.34,1.56,.64,1)`). Glow breathes subtly on rest; hover lifts 1-2px AND amplifies glow by ~30%. Durations: fast 120ms, base 200ms, slow 360ms.

**Hover.** Lift (`translateY(-1px..-2px)`) + brighter glow. Never darken/lighten the fill alone.

**Press.** Scale to 0.97 + snap glow to resting state. ~80ms.

**Borders.** Cards have `1px rgba(255,255,255,0.04–0.16)` — barely-there hairlines. Inputs use a 1.5px border; focus replaces it with magenta + triple-layer glow (ring + neon).

**Shadows.** Always dark-drop (`rgba(0,0,0,0.3–0.6)`) stacked with a colored glow when the element is emphasized. Never airy white/gray shadows.

**Glass.** `backdrop-filter: blur(29px)` is the canonical glass effect — taken from the Figma hero label.

**Protection gradients vs capsules.** Imagery uses protection gradients (bottom-fade) for titles. Top bar items sit inside a full-width dark pill (capsule).

**Radii.** Everything is rounded — cards `16–20`, tiles `16`, inputs `12`, buttons are pills (`999`), hero label is `56`. No sharp corners anywhere.

**Transparency / blur.** Used liberally on overlay surfaces (dropdowns, sticky bars), rarely on primary content.

**Imagery vibe.** Saturated, slightly warm, with strong key lights against a dark/purple environment. Game covers are busy, high-contrast, often with gold lettering or character illustrations. Dr. Bingo mascot is the recurring human touch.

---

## Iconography

**System:** Substituted. The Figma file references `Icon/Share`, `Icon/User`, `Icon/Chevron_down`, `Icon/Wallet`, `Icon/Menu`, `Icon/Warning`, `Icon/Error`, `Icon/trophy`, `Icon/Like` by name — all of which are standard UI glyphs. **No icon SVGs were present in the VFS.** 

We substitute **Lucide** (CDN: https://unpkg.com/lucide-static) as the closest match: same 24px grid, ~1.75px stroke, rounded joins. **Please confirm or attach your real icon pack** so we can swap.

**Approach:** Outlined icons at rest; filled variants for selected/awarded states (star, heart).  
**Emoji:** Only in marketing copy and host-level micro-moments (🔥 🎉 ⭐). Never as a functional UI icon.  
**Unicode glyphs:** Used inline for quick decoration (★ ♡ ⏱) — should be replaced with SVG for production.  
**Custom:** The Dr. Bingo mascot illustration is the brand's hero asset; game-tile covers ship per-game.

---

## Usage Rules — quick reference

1. **One glow per screen.** Glows are loud; more than one competes and the hierarchy collapses.
2. **Accent gradients are semantic:** magenta=action, gold=money, lime=win. Don't cross them.
3. **Labels are ALL-CAPS bold** with `letter-spacing: 0.04em`. Don't use label styles for headings or body.
4. **Luckiest Guy is for display only.** Never below 32px, never for UI chrome.
5. **Dark surface first.** Light surfaces don't exist in this system.
6. **Pills > squares.** When in doubt, radius 999.
7. **Mono for anything with digits that matter** (money, multipliers, timers) — tabular fit.
8. **Protection gradient before text-on-image.** Never place a label on raw imagery.

---

## Caveats

- **Figma file is minimal** — it contains text styles and the cover, not a full component library. All components (buttons, inputs, tiles, nav) were designed to match the product screenshot's style language, not lifted 1:1 from Figma.
- **No icon assets** in the file. Lucide used as a stand-in.
- **Mascot & game art** not provided — cards use gradient placeholders. Please attach the Dr. Bingo character + a few game covers if you want them in a UI kit.
- **Fonts loaded from Google Fonts CDN** (Inter, Luckiest Guy, JetBrains Mono). Flag if you need local `.ttf`/`.woff2` files.
- **Semantic error color (`#FF3355`)** was not in Figma — inferred to complement the palette. Confirm or replace.
- **Green scale** has many near-identical values in Figma; I consolidated to two.
