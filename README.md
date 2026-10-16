# Data Platform Discovery

Interactive prototype of the **Discovery Application** for the Excise Generative AI (SMITT) Data Platform project (118_DataPlatformV.4.1).

**Open the prototype:** https://pitsinee-yuni.github.io/Data-platform-Discovery/

## What's in it

- **Platform Overview** – all data products, one row per data product and source, with Pass, Chain Exhausted, Completeness and E-Score. Pass = cells with a value that converted; Chain Exhausted = cells with a value that no transformer could convert; Completeness = cells that have a value (100% − empty cells, higher is better, orange below 90%). Click an E-Score to open its Quality Report; right-click a name to rename or delete.
- **Overview** – KPI cards, editable metadata (DGA standard), source chips, E-Score and Responsible Persons.
- **Data Dictionary** – column design compared with the ingested data (Missing / Not in design / Found as), add, edit and remove columns.
- **Preview** – sample rows with column search, source and date filters, sorting.
- **Quality Report** – daily quality trend (last 7 days by default), top issues, AI recommendations, execution steps and Investigate Rows.
- **Lineage** – Landing → Staging → Integration, one row per source.

All data is mock data built into the page; changes reset when the page is reloaded.

## Files

- `index.html` – the whole prototype in one file (Tailwind CSS, Chart.js and the Inter font load from public CDNs, so an internet connection is needed).
