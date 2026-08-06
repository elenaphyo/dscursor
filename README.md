# Design System

Brand foundations for **dscursor**.

| Token | Value |
| --- | --- |
| Primary | `#002C76` |
| Secondary | `#B51F26` |
| Typeface | **Poppins** |

## Structure

```
tokens/
  primitives.json          # DTCG primitives (color ramps, spacing, radius, type)
  semantic.light.json      # Light-mode semantic aliases
  semantic.dark.json       # Dark-mode semantic aliases
styles/
  tokens.css               # CSS custom properties + text utility classes
docs/
  foundations.html         # Visual foundations preview
docs/figma-plan.md         # Canvas sync plan (variables, pages, components)
```

## Preview

Open `docs/foundations.html` in a browser to review color ramps, typography, spacing, radius, and component previews (light/dark toggle included).

## Figma canvas

Creating the live Figma library requires **Figma MCP authentication** in Cursor Desktop. Token files above are the source of truth; see `docs/figma-plan.md` for the exact collections, pages, and v1 components to build on canvas once connected.

## Collections (Figma mapping)

| Collection | Modes | Contents |
| --- | --- | --- |
| Primitives | Value | `primary/*`, `secondary/*`, `gray/*`, white, black, status |
| Color | Light, Dark | Semantic `color/bg/*`, `color/text/*`, `color/border/*`, `color/action/*` |
| Spacing | Value | `spacing/xs` → `spacing/3xl` |
| Radius | Value | `radius/sm` → `radius/full` |
| Typography | Value | Poppins family, size, weight, line-height |

## v1 components

Button · Input · Checkbox · Toggle · Badge · Avatar · Card
