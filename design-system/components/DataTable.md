# DataTable

Data tables in Discovery: the All Data Product Table, Data Dictionary and Preview share one style.

## Parts
- Section title above the table: `title-medium` (for example "All Data Product Table").
- Wrapper: `surface`, `border`, `radius-xl`, `shadow-xs`.
- Header: `body-medium` at 500 in `ink-muted` on `surface-dim`, sentence or Title Case, never uppercase. Metric headers are tinted by meaning: Pass `success`, Chain Exhausted `danger-mark`, Completeness `info`.
- Cells: `body-medium` (14px, as in Google Drive's file list); names semibold `ink`; counts, column names and dates in `mono-medium`. Row hover `row-hover`.

## Value rules
- Pass (data that can be used, including empty cells in optional columns): `success`, medium.
- Chain Exhausted above 10%: `danger-action`, medium.
- Completeness (share of cells with a value across all columns, higher is better; it can be lower than Pass when optional columns are empty) below 90%: `warning`, medium.
- No file yet: "—" in `ink-faint` in every metric cell, plus the No data badge. A file with zero rows shows 0 and the reason.
- Data Dictionary rows: Missing rows on `warning-row`, Not-in-design rows on `info-row`.
- Right-click on a name opens the ContextMenu (Rename, Delete).
