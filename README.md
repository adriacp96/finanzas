# INKFLOW

Minimal single-file finance tracker styled around a monochrome “Inkflow” aesthetic.  
The page lets you log cards and fixed expenses, visualizes payments per month/weekday, and syncs with Supabase snapshots if credentials are configured.

## Layout
- `index.html` contains all markup, styling, and JS in one document.
- The fixed expense list can render textual names (logos were previously handled via `renderExpenseName`).
- Cards use inline controls to edit day/charge-cycle and show totals via dynamically rendered calendar/chart sections.

## Getting started
1. Open `index.html` in a browser (or serve via a dev server if you prefer).
2. Update the Supabase constants if you want cloud sync; otherwise the UI works purely in-memory.
3. Add entries through the “New Card” / “New Expense” widgets, then tap “✎ Edit” to reveal inline editing.

## GitHub Pages
Deploy from the `main` branch with the root folder as the Pages source, then visit `https://<user>.github.io/finanzas/`.

## Assets
Logos used to live in `assets/`, but the current build renders only text so the folder is unused. If you reintroduce logos later, drop them into `assets/` (next to `index.html`) and update `renderExpenseName`.
