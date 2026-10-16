# EScoreBadge

The E-Score in the All Data Product Table: a clickable pill that opens the Quality Report for that row's data product and source.

## Thresholds
- **≥ 80%**: `success` text on a pale green ground.
- **70–79%**: orange (watch).
- **< 70%**: `danger` text on `danger-soft`.

## Rules
- Always show the chevron (›): it marks the badge as a link. Clicking it opens the Quality Report tab with the row's source selected and the chart on the last 7 days; clicking elsewhere in the row opens Overview.
- Value in `mono-small`, whole percent, no decimals.
- Tooltip: "View Quality Report for <source>".
- The E-Score card on the Overview tab uses the same bands with a status pill: Optimal (≥ 0.80), Monitor (0.70–0.79), Needs Review (< 0.70).
