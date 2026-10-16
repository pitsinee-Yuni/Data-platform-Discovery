# Modal

Dialogs for creating, confirming and warning, on a `scrim` backdrop.

## Parts
- Panel: `surface`, `radius-dialog` (28px), `shadow-dialog`, 24px padding, 360–480px wide.
- Optional status icon: a 48px disc, `caution` for rename, `danger-action` for delete.
- Title in `headline-small` (24px, 400), as Google Drive dialogs; body copy in `body-medium` `ink-muted`.
- Impact box: `caution-soft` with `caution-border` and `on-caution-soft` text for changes; `danger-soft` for deletes. It lists exactly what will change.
- Actions right-aligned: a text Cancel, then the primary or danger action.

## Rules
- Rename needs a new, unique name and a ticked acknowledgement before the button enables.
- Delete needs the data product's name typed exactly before Delete permanently enables. Deletes cannot be undone; say so.
- Esc and a backdrop click cancel. The browser's own confirm dialogs are never used.
