# Figma canvas plan

Source of truth for pushing this design system onto a Figma file via `use_figma` once MCP is authenticated.

**Code canvas (available now):** open `docs/canvas.html` — Cover, Color, Typography, Spacing & Radius, and Components artboards mirroring the page plan below.

## Brand lock

- Primary: `#002C76` → `primary/600`
- Secondary: `#B51F26` → `secondary/600`
- Typeface: Poppins (Regular, Medium, SemiBold, Bold)

## Phase 1 — Foundations

1. Create file: `Design System`
2. Collections:
   - **Primitives** (mode: Value) — all primitive colors from `tokens/primitives.json`
   - **Color** (modes: Light, Dark) — aliases from `semantic.light.json` / `semantic.dark.json`
   - **Spacing** (mode: Value)
   - **Radius** (mode: Value)
   - **Typography** (mode: Value) — Poppins sizes/weights
3. Set scopes (never `ALL_SCOPES`) and WEB code syntax `var(--…)` matching `styles/tokens.css`
4. Text styles: Display, H1–H4, Body LG, Body, Body SM, Label, Caption
5. Effect styles: Shadow/sm, Shadow/md, Shadow/lg

## Phase 2 — Pages

```
Cover
Getting Started
Foundations / Color
Foundations / Typography
Foundations / Spacing & Radius
---
Button
Input
Checkbox
Toggle
Badge
Avatar
Card
---
Utilities
```

## Phase 3 — Components (dependency order)

| Component | Variant axes (cap ≤ 30) |
| --- | --- |
| Button | Size=Sm/Md/Lg × Style=Primary/Secondary/Outline/Ghost × State=Default/Hover/Disabled |
| Input | Size=Sm/Md/Lg × State=Default/Focus/Error/Disabled |
| Checkbox | State=Unchecked/Checked/Indeterminate/Disabled |
| Toggle | State=Off/On/Disabled |
| Badge | Style=Brand/Danger/Neutral × Size=Sm/Md |
| Avatar | Size=Sm/Md/Lg × Type=Image/Initials |
| Card | Elevation=None/Sm/Md |

All fills, strokes, padding, gap, and radius bound to variables.

## Resume prompt

> Continue design system build. Run ID: ds-brand-002c76. Load figma-generate-library + figma-use. Authenticate Figma MCP, create new design file, execute Phase 1 from tokens in `/workspace/tokens`.
