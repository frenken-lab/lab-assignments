# Lab Assignments

Guided notebook assignments for the MSL research lab. Each assignment builds toward a concrete contribution: a **dataset preprocessing module** added to the [GraphIDS](https://github.com/frenken-lab/KD-GAT) codebase.

## The Arc

Students are each assigned an ICS/SCADA dataset (WaDi or EPIC). Over three assignments, they go from raw data to graph-structured input ready for GNN training.

```
Part 1: EDA              Part 2: DataFrames         Part 3: Graphs
─────────────────        ─────────────────          ─────────────────
Understand your    →     Learn the tools you   →    Turn tabular rows
dataset: structure,      will use to preprocess      into graph data
time, labels, quality    it: Polars vs Pandas        using NetworkX
```

The end-goal: each student contributes a file at `graphids/core/data/datasets/<dataset>.py` that loads, preprocesses, and converts their dataset into graph-ready format.

## Assignments

| File | Description |
|------|-------------|
| [`dataset-eda.ipynb`](dataset-eda.ipynb) | Part 1 — Exploratory data analysis of assigned dataset (Polars + Altair) |
| [`dataframe-comparison.ipynb`](dataframe-comparison.ipynb) | Part 2 — Row vs columnar architecture, Pandas vs Polars performance comparison |
| [`graph-data.ipynb`](graph-data.ipynb) | Part 3 — Tabular to graph conversion using NetworkX sliding windows |

## Setup & Guides

| File | Description |
|------|-------------|
| [`setup.md`](setup.md) | Environment setup — uv, venv, dependencies, Jupyter |
| [`github-issue.md`](github-issue.md) | How to create and assign yourself a GitHub issue for your dataset module |
| [`quarto-post.md`](quarto-post.md) | Publishing your EDA + dataset description as a Quarto blog post |

## Prerequisites

- Access to OSC (Ohio Supercomputer Center)
- Python 3.12 via `module load python/3.12`
- [uv](https://docs.astral.sh/uv/) package manager
- Datasets are on the shared filesystem at `/fs/ess/PAS1266/`

## Tools Used

- **[Polars](https://docs.pola.rs/)** — primary dataframe library
- **[Pandas](https://pandas.pydata.org/)** — used in Part 2 for comparison
- **[Altair](https://altair-viz.github.io/)** — declarative visualization
- **[NetworkX](https://networkx.org/)** — graph construction (Part 3)

## Deliverables

Each assignment has a deliverable due the following week:

1. **Part 1** — Completed EDA notebook + dataset description published as a [Quarto](https://quarto.org/) blog post
2. **Part 2** — Completed comparison notebook with timing results and reflection
3. **Part 3** — Completed graph notebook demonstrating sliding-window graph construction

## License

MIT
