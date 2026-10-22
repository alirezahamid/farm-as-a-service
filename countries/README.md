# Countries (regional availability)

The guides in [`docs/`](../docs/) are general. Laws, subsidies, tax, and
prices are local. They live here, one folder per country.

## Available regions

| Code | Country | Status |
| --- | --- | --- |
| [`uk`](uk/README.md) | United Kingdom | Starter. Many TODOs. |
| [`ph`](ph/README.md) | Philippines | Starter. Many TODOs. |

Your country is not here? Add it.

## How to add your country

1. Find your two-letter country code (ISO 3166-1 alpha-2), in lowercase.
   Examples: `de`, `fr`, `us`, `ca`, `nz`. The United Kingdom uses `uk`,
   because that is what people look for.
2. Create `countries/<code>/README.md`.
3. Copy the section headings from [`uk/README.md`](uk/README.md):
   - Who runs what (the main agencies)
   - Land and prices
   - Planning and zoning
   - Registering animals
   - Selling food
   - Subsidies and grants
   - Tax notes
   - Useful links
4. Link to official sources for every rule. Laws change. Add the date you
   checked.
5. Mark anything you are not sure of with `<!-- TODO: needs source -->`.
6. Add a row to the table above and to the main [README](../README.md).
7. Open a pull request.

## Rules for country pages

- Write in English, so everyone can review. A translation in the same folder
  is welcome, for example `README.de.md`.
- If rules differ by state, province, or nation, say so. Add sub-pages if it
  gets long, for example `countries/us/vermont.md`.
- Prices need a year and a currency.
- This is not legal or tax advice. Say so at the top of the page.
