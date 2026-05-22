# Accessibility

**Covers:** keyboard, screen-reader, and contrast requirements. Fiori targets WCAG 2.1 AA and EN 301 549.

**Source:** https://www.sap.com/design-system/fiori-design-web — Foundations → Accessibility

## The shortcut: use semantic controls

`sap.m` / `sap.f` controls ship correct roles, keyboard handling, and ARIA. Most accessibility is **earned for free by not using raw HTML**. A styled `<div>` has none of it.

## Keyboard

- Every interactive element is reachable and operable by keyboard (Tab / Shift+Tab, Enter/Space, arrow keys in lists & tables).
- Don't trap focus; manage focus on dialog open/close and after navigation.
- Don't remove focus outlines.

## Labels & names

- Associate labels with fields via `sap.m.Label` `labelFor`, or `ariaLabelledBy` / `ariaDescribedBy`.
- Use `sap.ui.core.InvisibleText` to name controls that have no visible label (e.g. an icon-only button — also set `tooltip`).
- **Never** use a placeholder as the label; placeholders disappear on input.
- Give icon-only buttons a `tooltip`.

## Color & contrast

- **Never convey meaning by color alone.** Pair color with text or an icon — e.g. `ObjectStatus` `state="Error"` *and* its text/icon.
- Keep Horizon's contrast ratios; don't override with low-contrast custom colors.
- Support the high-contrast themes (`sap_horizon_hcb` / `_hcw`) — verify nothing relies on a specific hue.

## Structure

- Provide a sensible heading/section hierarchy (Object Page sections give this naturally).
- Use landmark/region semantics from the floorplan controls rather than inventing your own.

## Anti-patterns

- ❌ Clickable `<div>` (no role, no keyboard, no ARIA).
- ❌ Status shown only as a red dot with no text.
- ❌ Placeholder-as-label.
- ❌ Removing focus rings for "cleaner" visuals.
