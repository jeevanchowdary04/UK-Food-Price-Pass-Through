# HMRC raw-data provenance

The dissertation uses the official HMRC UK Trade Info OTS API. During the live extraction session the API returned **58,196 supplier-country-month records** across the six frozen core categories and 151 months (2014-01 to 2026-07). The counts and quality audit are preserved in `hmrc_live_extraction_audit.csv`, and the exact query design is in `api_query_manifest.csv`.

The chat/browser execution environment did not expose the full downloaded 58,196-row browser payload as a mountable local file. Therefore this repository **does not mislabel reconstructed rows as the original raw supplier-country payload**. Instead it includes:

1. the persisted category-month analytical extracts in `data/interim/hmrc_monthly_api_core/`;
2. the exact live-query design and record counts;
3. `scripts/01_acquire_hmrc.py`, which downloads and persists the full supplier-country-month raw extracts on any normal internet-enabled Python environment;
4. the final 906-row panel and every model output used in the technical analysis.

This distinction is deliberate for academic integrity and reproducibility.

Official endpoint: https://api.uktradeinfo.com/OTS
Country dimension: https://api.uktradeinfo.com/Country
Commodity dimension: https://api.uktradeinfo.com/Commodity
