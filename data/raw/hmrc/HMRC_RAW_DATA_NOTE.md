# HMRC raw-data status

The official HMRC UK Trade Info OTS API was queried live for all six primary categories for 2014M01–2026M07, grouped by `MonthId`, `CountryId`, and `SuppressionIndex` with summed `Value` and `NetMass`. The live responses contained **58,196 country-month records** in total.

Because the live browser/API environment and the local file-building container are isolated, the untouched 58,196 response rows could not be transferred as raw bytes into this repository. This repository does **not** pretend otherwise.

What is included:
- `hmrc_query_manifest.csv`: exact API URLs used for each category;
- `live_extraction_audit.csv`: record counts and completeness diagnostics observed from the live responses;
- `data/interim/hmrc_api_monthly_measures/*.json`: exact 151-month category-level analytical measures persisted from the live extraction and used for the models;
- `scripts/01_acquire_hmrc.py`: reproduces and saves the full country-month records on any normal internet-enabled machine;
- processed panel and all model outputs.

Live extraction audit found zero null-country rows and zero non-zero suppression-index rows in these aggregated query responses. A handful of country-month rows had missing/non-positive mass, but their import-value share was zero or effectively zero (maximum observed share about 3.86e-7 in Fish). This does not remove the broader methodological limitation that HMRC suppression and quantity definitions can affect trade statistics, so the dissertation should retain that limitation.
