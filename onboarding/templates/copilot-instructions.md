# Copilot Instructions

> Starter template for Assignment 2c — copy this to `.github/copilot-instructions.md` in your 2a EDA repository and customize. GitHub Copilot reads this file on every suggestion.

This project analyzes the HCRL Survival IDS dataset for automotive CAN bus intrusion detection.

## Conventions

- Use **polars** for data manipulation (not pandas)
- Use **altair** for visualization (not matplotlib/seaborn)
- Use **scikit-learn** for baseline ML models
- Follow PEP 8; formatter is **ruff**, line length 100
- Prefer explicit column names over positional indexing
- Keep functions small and composable

## Output format

- No docstring paragraphs on trivial functions — one line is enough
- Type hints on public functions
- No `print` for debugging — use `logging` or return values
