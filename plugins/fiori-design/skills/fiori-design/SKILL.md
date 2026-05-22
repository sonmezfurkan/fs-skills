---
description: Aligns freestyle SAPUI5/OpenUI5 apps with the SAP Fiori Design Guidelines (Horizon). Use proactively when building or reviewing hand-written UI5 — choosing controls, page layout/floorplan, spacing, theming, accessibility, or UI text — in XML views, fragments, or controllers. Skip for Fiori Elements apps, which enforce these conventions through annotations.
---

# Fiori Design Guidelines for Freestyle UI5

## The principle

Freestyle UI5 gives you total layout freedom — and removes the guardrails Fiori Elements provides for free. This skill restores those guardrails: every hand-built view should look, behave, and read like a first-party Fiori app. **When in doubt, choose what a Fiori Elements app would have generated.**

## When this applies

- Hand-written XML views, fragments, JS/TS controllers, or custom controls.
- Any decision about a control, page structure, spacing, theme/styling, accessibility, or UI text.

## When it does NOT apply

- Fiori Elements apps (List Report / Object Page driven by annotations) — they already enforce the guidelines. Don't fight their conventions; express intent through annotations instead.

## Core checklist (apply on every UI5 task)

1. **Floorplan first** — pick the right page pattern before placing controls. → `references/floorplans.md`
2. **Semantic controls, not raw HTML** — use `sap.m` / `sap.f`; never `<div>`/`<span>` for app structure. → `references/controls.md`
3. **Right page scaffold** — `sap.f.DynamicPage` for most pages; `sap.uxap.ObjectPageLayout` for object pages. → `references/floorplans.md`
4. **Spacing via classes, not pixels** — UI5 margin/padding classes + content density; no magic numbers. → `references/layout-and-spacing.md`
5. **Horizon theme + theme parameters** — no hard-coded colors or fonts. → `references/theming.md`
6. **Responsive + accessible** — works phone→desktop; keyboard-reachable and labeled. → `references/layout-and-spacing.md`, `references/accessibility.md`
7. **UI text follows the tone rules** — sentence case, concise, action-led. → `references/content-and-tone.md`

## Reference map (load on demand)

- `references/floorplans.md` — page patterns and when to use each
- `references/controls.md` — design intent → correct Fiori control
- `references/layout-and-spacing.md` — DynamicPage, responsive grid, content density, spacing classes
- `references/theming.md` — Horizon, theme parameters, CSS do's and don'ts
- `references/accessibility.md` — keyboard, ARIA, labels, contrast
- `references/content-and-tone.md` — labels, messages, sentence case, terminology

## Non-negotiables

- No raw HTML (`<div>`/`<span>`) for app structure — use UI5 controls.
- No hard-coded hex colors or pixel spacing — use theme parameters + spacing classes.
- Every interactive control reachable by keyboard and labeled (no placeholder-as-label).
- One emphasized action per context; semantic state via `ObjectStatus`, not manual color.

---

> **Note:** The `references/` files are starter skeletons. Fill them in from the official guidelines at
> https://www.sap.com/design-system/fiori-design-web — each file lists the exact section to pull from.
