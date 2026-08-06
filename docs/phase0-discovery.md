# Phase 0 Discovery — Design System Canvas

Run ID: `ds-brand-002c76`  
Brand lock: Primary `#002C76` · Secondary `#B51F26` · Typeface **Poppins**

## P0.a — Codebase analysis

| Source | Path | Role |
| --- | --- | --- |
| DTCG primitives | `tokens/primitives.json` | Color ramps, spacing, radius, font |
| Semantic light | `tokens/semantic.light.json` | Light-mode aliases → primitives |
| Semantic dark | `tokens/semantic.dark.json` | Dark-mode aliases → primitives |
| CSS tokens | `styles/tokens.css` | WEB code syntax (`var(--…)`) + text utilities |
| Preview | `docs/foundations.html` | Visual QA for foundations |
| Canvas plan | `docs/figma-plan.md` | Figma collections / pages / components |

No React component library yet — v1 components will be created in Figma first, then optionally Code Connected.

## P0.b / P0.c — Figma inspect + library search

**Blocked.** Figma MCP `serverStatus: needsAuth`. Interactive `mcp_auth` is unavailable in this cloud agent environment; authentication must be completed in Cursor Desktop.

## P0.d — Locked v1 scope

### Collections

| Collection | Modes | Contents |
| --- | --- | --- |
| Primitives | Value | `primary/*`, `secondary/*`, `gray/*`, white, black, success/warning/info |
| Color | Light, Dark | `color/bg/*`, `color/text/*`, `color/border/*`, `color/action/*`, `color/icon/*` |
| Spacing | Value | `spacing/none` → `spacing/3xl` |
| Radius | Value | `radius/none` → `radius/full` |
| Typography | Value | Poppins family, sizes, weights, line-heights |

### Styles

- **Text:** Display, H1–H4, Body LG, Body, Body SM, Label, Caption (Poppins)
- **Effect:** Shadow/sm, Shadow/md, Shadow/lg

### Pages

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

### v1 components (variant caps ≤ 30)

| Component | Axes |
| --- | --- |
| Button | Size × Style × State (3×4×3 = 36 → split: Primary set + Secondary/Outline/Ghost set, or Size×Style with State as overlay — prefer Size×Style=12 with State via variants carefully; plan: Size Sm/Md/Lg × Style Primary/Secondary/Outline/Ghost × State Default/Hover/Disabled = 36 → **split** into Button Primary (Size×State) + Button Secondary family OR use Style×Size with Disabled boolean — **decision: Size × Style × State where Disabled is BOOLEAN property, Hover via separate variant only for interactive docs → Size×Style×State(Default/Hover/Disabled)=36 still high. Cap: Size×Style (12) + State as BOOLEAN Disabled + INSTANCE for icon. Document Hover as style override on Default.** |
| Input | Size × State (Default/Focus/Error/Disabled) |
| Checkbox | State (Unchecked/Checked/Indeterminate/Disabled) |
| Toggle | State (Off/On/Disabled) |
| Badge | Style × Size |
| Avatar | Size × Type |
| Card | Elevation |

**Button matrix resolution:** Use `Size=Sm/Md/Lg` × `Style=Primary/Secondary/Outline/Ghost` × `State=Default/Hover/Disabled` = 36. Per skill rule (cap 30), split into two component sets:
1. `Button` — Style=Primary/Secondary × Size × State (18)
2. `Button Quiet` — Style=Outline/Ghost × Size × State (18)

### Naming

- Variables: slash-separated (`color/bg/brand`, `spacing/md`)
- Primitives: `primary/600`, `gray/50`
- WEB syntax: exact CSS names with `var()` wrapper, e.g. `var(--color-bg-brand)`
- Scopes: never `ALL_SCOPES`; primitives `[]`

## P0.e — Conflicts

| Conflict | Resolution |
| --- | --- |
| No Figma file yet | Create new `Design System` design file after auth |
| Empty main repo vs foundations branch | Bring foundations onto `cursor/design-system-canvas-5b42` as source of truth |
| Code has no component impl | Figma-first for v1 atoms; Code Connect optional in Phase 4 |

## P0.f — Gap analysis

| In code, not Figma | In Figma, not code | Conflict |
| --- | --- | --- |
| All primitives + semantic tokens | *(unknown — no file)* | N/A until inspect |
| CSS variables + foundations preview | | |
| Planned components (docs only) | | |

**Blocker:** Authenticate Figma MCP, then resume Phase 0.b–0.c → Phase 1.
