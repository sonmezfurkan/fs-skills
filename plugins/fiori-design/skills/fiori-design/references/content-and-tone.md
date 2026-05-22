# Content & tone (UI text)

**Covers:** how labels, messages, and microcopy should read in a Fiori app.

**Source:** https://www.sap.com/design-system/fiori-design-web — Foundations → UI Text / Content

## Capitalization

- **Sentence case** everywhere — labels, titles, buttons, column headers, menu items. ("Create event", not "Create Event".)
- Capitalize only the first word and proper nouns. No Title Case, no ALL CAPS.

## Voice

- Concise and specific; lead with the action. ("Create event", not "Click here to create a new event".)
- Address the user as "you"; refer to the app/system as "we" sparingly. Avoid jargon and internal/technical terms.
- One term per concept, used consistently across the whole app (don't alternate "delete" / "remove").

## Buttons & actions

- Buttons are **verbs**: **Save**, **Delete**, **Add**, **Edit**.
- Prefer a specific verb over generic "OK". In a save dialog use **Save** / **Discard**, not **OK** / **Cancel**.
- **Cancel** is fine for dismissing without committing.

## Messages

- Error/warning messages state **what happened** and **what to do next** — no blame, no stack traces, no error codes as the headline.
  - ✅ "This event is fully booked. Reduce the number of attendees or pick another session."
  - ❌ "Error 500: capacity constraint violated."
- Success: a brief `MessageToast` ("Event saved"), not a modal.
- Empty states (`IllustratedMessage`): say why it's empty and offer the next step.

## Formatting (locale-aware)

- Format dates, numbers, and currency with UI5 formatters (`sap.ui.core.format.DateFormat`, `NumberFormat`) — never hand-built strings. They respect the user's locale automatically.
- Don't hard-code date/number/currency formats.

## Anti-patterns

- ❌ Title Case or ALL CAPS labels.
- ❌ "OK" where a specific verb is clearer.
- ❌ Raw exception text or error codes shown to users.
- ❌ Manually formatted dates/amounts (`"05/22/2026"`, `"$1,000.00"`).
