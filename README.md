# Design System

Brand foundations and canvas for **dscursor**.

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
  canvas.html              # Design System Canvas (artboard layout)
  foundations.html         # Linear foundations preview
  figma-plan.md            # Figma sync plan (variables, pages, components)
```

## Preview

Open the **Design System Canvas**:

```bash
# from repo root
python3 -m http.server 5173
```

Then open [http://localhost:5173/docs/canvas.html](http://localhost:5173/docs/canvas.html)

Artboards: Cover · Color · Typography · Spacing & Radius · Components (v1). Light/dark toggle included.

Linear view: [docs/foundations.html](docs/foundations.html)

## Figma canvas

Live Figma library creation requires **Figma MCP authentication in Cursor Desktop** (not available in this cloud agent environment). Token files above are the source of truth; see [docs/figma-plan.md](docs/figma-plan.md) for collections, pages, and v1 components to push once connected.

**Resume prompt after auth:**

> Continue design system build. Run ID: ds-brand-002c76. Load figma-generate-library + figma-use. Authenticate Figma MCP, create new design file, execute Phase 1 from tokens in `/workspace/tokens`.

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
