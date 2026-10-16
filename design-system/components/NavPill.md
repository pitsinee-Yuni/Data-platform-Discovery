# NavPill

Sidebar navigation: the logo row, pill buttons for app-level destinations, and a labelled list of data products.

## Parts
- **Logo row**: the Discovery mark at 40px (`radius-md` corners) beside the wordmark "Discovery" alone, in `title-large` size at weight 500 (22px, Medium) and `ink-muted`, as Google Drive sets "Drive".
- **Nav pill** (`dd-nav-pill`): `body-medium` text (14px, 500) with a 20px icon, `radius-full`. Active: `secondary-container` ground, `on-secondary-container` text, semibold. Hover: `surface-container-high`.
- **Create pill** (`is-create`): always `surface` with a `border-control` outline so the main action stands out from the destinations.
- **Section label**: `title-medium` (16px, 500) in sentence case ("Data Product") with a count chip in `mono-small`.
- **Data product item** (`dd-nav-item`): `radius-lg`, `ink-muted` until active.

## Rules
- The sidebar ground is `surface-dim`; it collapses to 72px and shows icons only (no wordmark, labels or counts).
- Keep destinations to Platform Overview and Create Data Product; data products are listed, not pinned.
