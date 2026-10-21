# Technical implementation

## Pipeline

1. `00_validate_environment.py` — validates project configuration.
2. `01_acquire_hmrc.py` — live HMRC API acquisition route.
3. `02_build_panel.py` — panel construction/validation route.
4. `03_reproduce_final_analysis.py` — canonical RQ1–RQ3, diagnostics and robustness analysis.
5. `04_make_figures.py` — eight numbered final figures.
6. `05_verify_reported_results.py` — independent headline-result and artefact checks.

## Reusable package

- `features.py` — HHI, Top-3 share, safe log changes and trade aggregation.
- `panel.py` — ONS loading and common-period panel merge.
- `models.py` — lag creation, robust model fitting, coefficient tables and covariance-aware linear combinations.
- `quality.py` — category-level quality summaries and pre-specified coverage gates.
- `hmrc.py` — HMRC acquisition helpers.
- `plotting.py` — reusable visualisation utilities.

## Reproducibility design

The canonical offline run starts from verified monthly HMRC extracts and official ONS CPI input retained in the repository. The final analysis reconstructs the 906-row panel and 882-row primary sample, writes the analytical datasets locally, estimates all models, rebuilds result tables, and regenerates the figures. A separate verifier then checks reported headline values against the generated files.

## Numerical traceability

The main analysis outputs are CSV/JSON rather than values typed manually into documentation. `results/tables/findings_summary.json` provides a machine-readable record of sample sizes, RQ estimates, category-specific effects, robustness and global diagnostics.
