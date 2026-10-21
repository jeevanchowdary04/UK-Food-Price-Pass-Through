# Quick start

## Offline reproduction

```bash
python -m venv .venv
# Windows: .venv\Scripts\activate
# macOS/Linux: source .venv/bin/activate
pip install -r requirements-lock.txt
python scripts/00_validate_environment.py
python scripts/03_reproduce_final_analysis.py
python scripts/04_make_figures.py
python scripts/05_verify_reported_results.py
pytest -q
```

Expected headline checks: 906-row master panel, 882-row primary sample, eight final figures and a final technical audit of `PASS`.

## Live HMRC refresh

A live refresh is optional and requires internet access:

```bash
python scripts/01_acquire_hmrc.py
python scripts/02_build_panel.py
python scripts/03_reproduce_final_analysis.py
python scripts/04_make_figures.py
python scripts/05_verify_reported_results.py
```

For methodology and formula details, see `docs/03_FORMULAS_AND_MODELS.md` and `docs/04_TECHNICAL_IMPLEMENTATION.md`.
