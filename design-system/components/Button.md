# Button

Pill-shaped buttons for every action in Discovery: `primary` for the one main action, `text` for cancel, `danger` for destructive actions.

## Variants
- **Primary** (`dd-btn-primary`): `primary` fill, `on-primary` text, `shadow-xs`. One per dialog or toolbar: Apply, Save, Create, Rename, Add Row.
- **Text** (`dd-btn-text`): `primary` text, `primary-soft` on hover. Cancel and secondary choices.
- **Danger** (`dd-btn-danger`): `danger-action` fill. Only for permanent deletes (Delete permanently, Delete column), always inside a confirm dialog.
- **Outline** (`dd-btn-outline`): `surface` with `border-control`. In-row actions such as Add to dictionary.

## Sizes
Every button label is `body-medium` at weight 500 (14px), as in Google Drive. `dd-btn-sm` only tightens the padding for toolbars and cards; `dd-btn-xs` (11px) is kept for inline editors (Done, Save in Responsible Persons).

## Rules
- Shape is always `radius-full`.
- Labels are verbs in Title Case for nav-level actions (Create Data Product, Add Row) and sentence case for in-row actions (Add to dictionary).
- Disabled buttons drop to 45% opacity and lose the shadow; say why nearby (for example, "Type the name to confirm").
- Focus: a solid 2px `primary` outline, 2px offset.
