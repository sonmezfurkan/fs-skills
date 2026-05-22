# Theming (Horizon)

**Covers:** using the Horizon theme and theme parameters. No hard-coded colors.

**Source:** https://www.sap.com/design-system/fiori-design-web — Foundations → Colors / Theming

## Themes

Horizon is the current Fiori theme. Ship these four and don't replace the palette:

- `sap_horizon` — default (light)
- `sap_horizon_dark`
- `sap_horizon_hcb` — high-contrast black
- `sap_horizon_hcw` — high-contrast white

(`sap_fiori_3` / Quartz is the previous generation — don't target it for new apps.)

## Use theme parameters, never literals

Read parameters instead of writing hex/rgb. Common semantic parameters:

| Purpose | Parameter |
| --- | --- |
| Brand / primary | `sapBrandColor`, `sapHighlightColor` |
| Body text / titles / links | `sapTextColor`, `sapTitleColor`, `sapLinkColor` |
| Backgrounds | `sapBackgroundColor`, `sapGroupContentBackground`, `sapTile_Background` |
| Positive (success) | `sapPositiveColor`, `sapPositiveTextColor`, `sapPositiveBackground` |
| Negative (error) | `sapNegativeColor`, `sapNegativeTextColor`, `sapNegativeBackground` |
| Critical (warning) | `sapCriticalColor`, `sapCriticalTextColor`, `sapCriticalBackground` |
| Neutral / informative | `sapNeutralColor`, `sapInformativeColor` |

In JS/TS, read them **asynchronously** (the sync form is deprecated):

```js
import Parameters from "sap/ui/core/theming/Parameters";

Parameters.get({
  name: ["sapBrandColor", "sapNegativeColor"],
  callback: (params) => { /* use params.sapBrandColor */ }
});
```

In LESS/CSS, reference the theme's LESS parameters / CSS custom properties rather than literal colors.

## Rules

- ❌ No hard-coded hex/rgb in views, controllers, or CSS.
- Custom CSS is a last resort — scope it tightly and pull values from theme parameters.
- Must survive **dark** and **high-contrast** themes; fixed colors break them.
- For deeper customization use the UI Theme Designer, not ad-hoc overrides.
- Theme custom controls via `library.source.less` using theme parameters.
