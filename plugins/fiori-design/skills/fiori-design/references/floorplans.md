# Floorplans (page patterns)

**Covers:** which Fiori page pattern to choose for a use case, and how to build it in freestyle UI5.

**Source:** https://www.sap.com/design-system/fiori-design-web — Foundations → Page Layouts / Floorplans

Pick the floorplan **before** placing controls. The floorplan determines the page scaffold, header behavior, and where actions live.

## Decision guide

| Goal | Floorplan | Freestyle scaffold |
| --- | --- | --- |
| Find & act on a set of items (filters + table) | **List Report** | `sap.f.DynamicPage` (filter bar in header) + `sap.m.Table` / `sap.ui.table.Table` |
| A focused list of items needing action, no filter bar | **Worklist** | `sap.f.DynamicPage` + table |
| View / edit a single object with grouped sections | **Object Page** | `sap.uxap.ObjectPageLayout` |
| At-a-glance KPIs and entry points | **Overview Page** (cards) | `sap.f.Card`s in `sap.f.GridContainer` |
| Analytics + line items together | **Analytical List Page** | charts + `sap.ui.table.AnalyticalTable` |
| Guided multi-step creation | **Wizard** | `sap.m.Wizard` |
| Master ↔ detail, progressive disclosure | **Flexible Column Layout** | `sap.f.FlexibleColumnLayout` |

When unsure between List Report and Worklist: use a **Worklist** only when there's a single, well-defined set of items the user works through; otherwise use a **List Report** with a filter bar.

## DynamicPage anatomy (`sap.f.DynamicPage`)

- **Title area** (`DynamicPageTitle`) — `heading` (object/page title), `actions` (global actions, right-aligned), `navigationActions`. Collapses to a **snapped** title on scroll.
- **Header content** (`DynamicPageHeader`) — filter bar, KPIs, or object facts; `pinnable` so users can keep it open.
- **Content** — the table, form, or main body.
- **Footer** (`footer` aggregation, `sap.m.OverflowToolbar`) — finalizing actions (**Save** / **Cancel**) sit here, right-aligned, primary action emphasized.

## Object Page anatomy (`sap.uxap.ObjectPageLayout`)

- **Header title** (`ObjectPageDynamicHeaderTitle`) — object title, subtitle, key actions; snaps on scroll.
- **Header content** (`ObjectPageDynamicHeaderContent`) — object facts, status, key figures, image.
- **Anchor bar** — auto-generated from sections; the in-page navigation.
- **Sections / subsections** (`ObjectPageSection` → `ObjectPageSubSection`) — grouped content; one concern per section.
- **Footer** — edit/save/cancel actions for the object.

## Rules

- One page = one floorplan. Don't mix a List Report header with an Object Page body.
- Global/finalizing actions go in the **footer toolbar**, not scattered in the content.
- Title snapping is expected behavior — don't suppress it with a fixed header unless there's a strong reason.
- Use `sap.m.IllustratedMessage` for empty/no-data/error states inside any floorplan.
