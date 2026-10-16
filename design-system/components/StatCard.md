# StatCard

KPI cards at the top of the Overview tab: Rows, Columns, Size and Data Health for the selected source and time range.

## Rules
- `surface-dim` ground, `radius-xl`, `space-4` padding; label in `body-medium` at 500 with a 16px `primary` icon; value in `title-large` (22px, 400).
- Data Health uses `success`, `warning` or `danger` by the same bands as the E-Score: 80% or more, 70–79%, below 70%.
- No data yet: the value is "—" in `ink-faint`, never 0.
- Four cards in one row on desktop, two per row on narrow screens.
