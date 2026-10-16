# FilterBar

The Source select and Time Range button that filter a tab, on a `surface-dim` bar aligned right.

## Parts
- **Label**: `body-medium` at 500 in `ink-muted`, followed by a colon (Source:, Time Range:).
- **Select / range button**: `body-medium` text on `surface`, `border-control`, `radius-lg`, `shadow-xs`. The calendar icon is `primary`.
- **Presets** in the date picker: Last 7 Days, Last 30 Days, Current Year. The preset that matches the current range is `secondary-container`.

## Rules
- The range button shows the preset and the actual dates ("Last 7 Days · 9 Oct – 15 Oct") so the label always matches the chart.
- Dates: short form "9 Oct" on buttons and axes; full form "Fri, 9 Oct 2026" in tooltips. Presets include today.
- Source options: All first, then sources in chip order. The Quality Report has no All.
- No summary text beside the filters: the controls show the current state.
