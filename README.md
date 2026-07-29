# Loa U.S. Healthcare Procedure Price Benchmarks

A dated, non-PHI snapshot of aggregate U.S. healthcare procedure price benchmarks published by [Loa](https://www.loacare.com/). Each row summarizes source-labeled hospital prices for one procedure and geographic area and links to the corresponding live Loa price page.

## Snapshot

- Version: `2026-07-29`
- Rows: 964 unique procedure-location benchmarks
- Procedures: 30
- Locations: 77
- States: 38
- Geographic scopes: 879 city rows and 85 state rows
- Format: CSV
- SHA-256: `89087c2d4ef426ed3e7cb98ba90cbedaab25088b32c7c8ba1c06de3bba439efd`

## Access

- [Dataset file in this repository](./data/loa-us-healthcare-price-benchmarks.csv)
- [Canonical live CSV](https://www.loacare.com/datasets/loa-us-healthcare-price-benchmarks.csv)
- [Methodology, provenance, and limitations](https://www.loacare.com/methodology)
- [Browse live procedure price pages](https://www.loacare.com/prices)
- [Machine-readable data package](./datapackage.json)

## Columns

| Column | Description |
| --- | --- |
| `dataset_version` | Snapshot date in `YYYY-MM-DD` format. |
| `procedure_name` | Human-readable procedure name. |
| `procedure_slug` | Canonical Loa procedure identifier. |
| `procedure_category` | Loa procedure category. |
| `cpt_codes` | Pipe-delimited CPT/HCPCS codes used for the procedure. |
| `location` | Human-readable city/state or state label. |
| `location_slug` | Canonical Loa location identifier. |
| `city` | City name when the row is city-scoped. |
| `state` | Two-letter U.S. state abbreviation. |
| `geographic_scope` | `city` or `state`. |
| `source_labeled_hospital_count` | Number of selected hospitals represented in the aggregate. |
| `minimum_price_usd` | Minimum selected listed price, rounded to U.S. dollars. |
| `median_price_usd` | Median selected listed price, rounded to U.S. dollars. |
| `average_price_usd` | Arithmetic mean of selected listed prices, rounded to U.S. dollars. |
| `maximum_price_usd` | Maximum selected listed price, rounded to U.S. dollars. |
| `latest_source_update` | Most recent source update represented by the row. |
| `source_page_url` | Live Loa page with the benchmark and source context. |

## Method summary

The snapshot uses current indexed hospital price records. For each procedure and location, Loa selects one preferred current price per hospital, applies the same procedure-specific eligibility floors used by the live price pages, and calculates summary statistics from up to 100 eligible source-labeled hospital rows. City rows require at least three city-matched hospitals. State rows are used only when the primary runtime falls back from insufficient city coverage.

The broader Loa price sitemap also includes separately qualified pages backed only by raw Hospital Price Transparency fallback records. Those pages are intentionally excluded from this uniform aggregate snapshot. See the [canonical methodology](https://www.loacare.com/methodology) for the full selection rules, provenance, coverage boundary, and caveats.

## Appropriate use

This dataset is useful for exploratory analysis, journalism, research, and software prototypes that need dated aggregate healthcare price benchmarks. It does not contain Protected Health Information and must not be treated as a quote, final bill, medical recommendation, or guarantee of patient responsibility. Prices can change, professional fees may be separate, and users should confirm current pricing directly with the provider.

## Citation

> Loa. *U.S. Healthcare Procedure Price Benchmarks*. Version 2026-07-29. https://www.loacare.com/methodology

The canonical landing page is `https://www.loacare.com/methodology`. Please cite that URL so readers can reach current provenance and limitations even after this snapshot is superseded. GitHub also renders the repository's machine-readable [`CITATION.cff`](CITATION.cff) as copyable citation formats.

## Terms

Access and use are governed by the [Loa Terms of Service](https://www.loacare.com/terms). No separate open-source or open-data license is granted by this repository.
