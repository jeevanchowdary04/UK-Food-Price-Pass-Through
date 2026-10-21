# Research-question traceability

| RQ | Core specification | Implementation | Primary output | Dissertation-facing evidence |
|---|---|---|---|---|
| RQ1 | 0–3 distributed lag | `scripts/03_reproduce_final_analysis.py`; `models.py::lincomb` | `rq1_coefficients.csv`; `cumulative_effects_rq1_rq3.csv` | cumulative 0.1253; category Figure 05; robustness Figure 08 |
| RQ2 | cost × lagged-HHI interactions | same canonical analysis script | `rq2_coefficients.csv`; cumulative effects table | low/median/high HHI Figure 06; moderation p≈0.819 |
| RQ3 | cost × HHI × disruption interactions | same canonical analysis script | `rq3_coefficients.csv`; cumulative effects table | regime Figure 07; disruption difference p≈0.007; HHI-specific p≈0.440 |
| Diagnostics | BP, Pesaran CD, Ljung–Box, ADF | canonical analysis script | diagnostic CSVs | rationale for robust covariance |
| Robustness | lag, outlier, period, FE and concentration alternatives | canonical analysis script | `robustness_cumulative_effects.csv` | Figure 08 and sensitivity table |

The purpose of this matrix is auditability: a reviewer can move from a research question to the exact implementation and numerical output without relying on prose alone.
