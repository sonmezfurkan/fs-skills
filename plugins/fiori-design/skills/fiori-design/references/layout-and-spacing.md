# Layout & spacing

**Covers:** responsive layout, content density, and the spacing system. No magic-number pixels.

**Source:** https://www.sap.com/design-system/fiori-design-web — Foundations → Layout; SAPUI5 SDK "Using Predefined CSS Margin Classes"

## Spacing — use the predefined classes, never inline px

Four standard sizes (same scale for margins and padding):

| Size | rem | px |
| --- | --- | --- |
| Tiny | 0.5rem | 8px |
| Small | 1rem | 16px |
| Medium | 2rem | 32px |
| Large | 3rem | 48px |

- **Full margin:** `sapUiTinyMargin`, `sapUiSmallMargin`, `sapUiMediumMargin`, `sapUiLargeMargin`.
- **Single-sided:** add a direction — `Top`, `Bottom`, `Begin` (left/LTR), `End` (right/LTR). e.g. `sapUiSmallMarginTop`, `sapUiMediumMarginEnd`. `Begin`/`End` are RTL-aware; prefer them over `Left`/`Right`.
- **Responsive margin:** `sapUiResponsiveMargin` shrinks the margin as the screen narrows — use it on top-level containers.
- **Content padding:** `sapUiContentPadding`, `sapUiResponsiveContentPadding` for standard inner padding.

Spacing is RTL-aware out of the box: a `Begin` margin flips to the right in Arabic/Hebrew.

## Content density

Set the density on a root container based on input style:

- `sapUiSizeCozy` — touch (larger hit targets). Default on touch devices.
- `sapUiSizeCompact` — mouse/keyboard (denser). Default on desktop.
- `sapUiSizeCondensed` — even denser; **only valid combined with Compact, and only affects `sap.ui.table` controls.** Apply `sapUiSizeCondensed` on the table together with `sapUiSizeCompact` on a parent.

Pick density from the device, e.g. `sap.ui.Device.support.touch ? "sapUiSizeCozy" : "sapUiSizeCompact"`, and set it once on the component root / body.

## Breakpoints (S / M / L / XL)

Standard Fiori responsive breakpoints used by the Grid and adaptive layouts:

| Range | Width | Device |
| --- | --- | --- |
| **S** | < 600px | Smartphone |
| **M** | 600–1023px | Tablet |
| **L** | 1024–1439px | Desktop |
| **XL** | ≥ 1440px | Large desktop |

## Responsive layout

- Prefer `sap.m` (responsive) controls.
- Adaptive columns: `sap.ui.layout.Grid` / `sap.f.GridContainer`, or form `ResponsiveGridLayout` / `ColumnLayout`.
- Grid spans use the breakpoint letters, e.g. `<Grid defaultSpan="XL3 L3 M6 S12">` — 4 columns on desktop, 2 on tablet, 1 on phone.
- **Design phone-first**, then verify S / M / L / XL.

## Anti-patterns

- ❌ Inline `style="margin: 12px"` or hard-coded pixel gaps.
- ❌ Fixed pixel widths that don't reflow.
- ❌ Forgetting to set content density (controls default to cozy and look oversized on desktop).
