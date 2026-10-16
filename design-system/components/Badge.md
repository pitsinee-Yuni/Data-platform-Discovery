# Badge

Small `label-small` (11px) labels that state the status of a column or data product in words.

## Variants
- **Missing** (`dd-badge-missing`): `on-warning-soft` on `warning-soft`. A designed column that the latest ingestion did not contain. It disappears on its own once data for the column arrives.
- **Not in design** (`dd-badge-extra`): `on-info-soft` on `info-soft`. A column found in data but not in the Data Dictionary. It stays until a Project Manager clicks Add to dictionary.
- **Added to dictionary** (`dd-badge-added`): `on-success-soft` on `success-soft`. Shown right after adding, until a description is entered.
- **No data** (`dd-badge-nodata`): a new data product with no Parquet file yet.
- **Data type** (`dd-badge-type`): `mono-small` type names in the Preview tooltip and Data Dictionary.

## Rules
- Every status carries its word; colour is never the only signal.
- One badge per row in the Data Dictionary, after the column name.
