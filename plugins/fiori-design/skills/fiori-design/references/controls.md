# Controls — design intent → Fiori control

**Covers:** the right semantic UI5 control for a given UI intent. Never reach for raw HTML.

**Source:** https://www.sap.com/design-system/fiori-design-web — Components

## Mapping table

| Intent | Control |
| --- | --- |
| Page scaffold | `sap.f.DynamicPage` / `sap.uxap.ObjectPageLayout` |
| Action button | `sap.m.Button` (use `type` for emphasis) |
| Primary/positive/negative semantic button | `Button type="Emphasized" / "Accept" / "Reject"` |
| Responsive table | `sap.m.Table` (column pop-in on small screens) |
| Grid / large / analytical table | `sap.ui.table.Table` / `AnalyticalTable` / `TreeTable` |
| Form | `sap.ui.layout.form.SimpleForm` (or `sap.ui.comp.smartform.SmartForm`) |
| Status / state | `sap.m.ObjectStatus` with semantic `state` |
| Key figure / amount | `sap.m.ObjectNumber` |
| Empty / no-data / error state | `sap.m.IllustratedMessage` |
| Card (overview/dashboard) | `sap.f.Card` in `sap.f.GridContainer` |
| Modal dialog | `sap.m.Dialog` |
| Confirmation / alert | `sap.m.MessageBox` |
| Transient success ("Saved") | `sap.m.MessageToast` |
| Inline contextual message | `sap.m.MessageStrip` |
| Aggregated messages | `sap.m.MessagePopover` |
| Value help / picker | `sap.m.SelectDialog`, `sap.ui.comp.valuehelpdialog.ValueHelpDialog` |

## Button hierarchy (important)

- **One** `Emphasized` (primary) action per context — the single most likely next step (e.g. **Save**).
- Secondary actions: `Transparent` / `Default`.
- Use **semantic** types (`Accept`/`Reject`) only for genuinely positive/negative actions, not for general buttons.
- Buttons are verbs (see `content-and-tone.md`).

## Tables

- Default to **`sap.m.Table`** (responsive, pops columns into a details row on phones).
- Use **`sap.ui.table.*`** only for large datasets, fixed columns, or analytical/tree needs — it is not responsive in the same way.
- Express row status with `ObjectStatus`, never by coloring the row manually.

## Anti-patterns

- ❌ `<div>` / `<span>` / raw HTML for layout or interaction.
- ❌ A custom-styled clickable element instead of `sap.m.Button` / `sap.m.Link`.
- ❌ Two emphasized buttons competing in one toolbar.
- ❌ `alert()` / browser dialogs instead of `MessageBox` / `MessageToast`.
