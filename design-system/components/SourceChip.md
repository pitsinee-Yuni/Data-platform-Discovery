# SourceChip

A source system attached to a data product, shown in the Source row of Metadata Properties.

## Rules
- `label-small` text, `on-secondary-container` on `secondary-container` with a light blue border, `radius-full`.
- In edit mode each chip gets a × button; Enter or a comma adds the typed name, Backspace in an empty field removes the last chip, Done saves.
- The chip order is the order of the Source filter options (after All) in every tab.
- The chip name must match the `{source}` part of the Parquet file name, for example `northwind` in `s.northwind.clean_data.0000.parquet`.
