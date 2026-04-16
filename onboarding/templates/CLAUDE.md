# CLAUDE.md

> Starter template for Assignment 2c — copy this to the root of your 2a EDA repository and customize it. The guide is at [AI-Augmented Development](https://osu-car-msl.github.io/lab-setup-guide/assignments/ai-augmented-development/).

## Project Overview

Exploratory data analysis of the HCRL Survival IDS dataset for automotive CAN bus intrusion detection.

## Tech Stack

- Python 3.12+
- polars for data manipulation
- altair for visualization
- scikit-learn for baseline ML models
- Jupyter notebooks for analysis

## Commands

- Install dependencies: `uv pip install -r requirements.txt`
- Run notebook: `jupyter notebook notebooks/eda.ipynb`
- Preview blog post: `quarto preview` (from the Quarto site repo)

## Conventions

- Save figures to `figures/` as PNG with `scale_factor=2`
- Use polars expressions, not pandas APIs
- Pin dependencies in `requirements.txt`
- Keep notebook cells short — one idea per cell

## Notes for the assistant

- Prefer polars; if you suggest pandas, flag that you're deviating from convention
- Altair charts should use tooltips where useful
- Don't add matplotlib/seaborn dependencies — altair is the lab's chart library
