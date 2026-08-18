# CyberForge v6.4 Risk Scoring

Risk scores are recalculated from the findings produced by each analysis.

## Factors

- Severity: Critical / High / Medium / Low / Info
- Confidence: confirmed / high / medium / low
- Exploitability weighting
- Optional bounded impact/exposure factors
- Duplicate finding suppression

The score is capped at 100, but it is not a fixed score shared by all modules.

Each report includes:

- `risk_score`
- `risk_level`
- `risk_analysis`
- per-finding contribution
- finding counts
- human-readable reasons for the score

A module with no findings should not inherit another module's score.
