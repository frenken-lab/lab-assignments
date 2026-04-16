# Creating and Assigning a GitHub Issue

## The big picture

These assignments are building toward a concrete contribution to the codebase: a **dataset preprocessing module** for your assigned dataset. This file will live at:

```
graphids/core/data/datasets/<your_dataset>.py
```

Look at the existing dataset files for reference — [`can_bus.py`](https://github.com/frenken-lab/graphids/blob/main/graphids/core/data/datasets/can_bus.py), [`epic.py`](https://github.com/frenken-lab/graphids/blob/main/graphids/core/data/datasets/epic.py), [`wadi.py`](https://github.com/frenken-lab/graphids/blob/main/graphids/core/data/datasets/wadi.py) are all in that directory. Each one defines the domain-specific preprocessing: attack taxonomy, feature schema, column parsing, and an `InMemoryDataset` adapter that feeds into the shared graph pipeline.

The three notebook assignments build up to that:
1. **EDA** — understand your dataset's structure, columns, labels, and quality
2. **Polars vs Pandas** — get comfortable with the dataframe operations you'll use for preprocessing
3. **Tabular to Graph** — learn how tabular rows become graph data (the core transformation your module will perform)

## 1. Draft your issue

Go to the repository's **Issues** tab on GitHub and click **New issue**.

- **Title:** `Add <dataset_name> dataset module` (e.g., "Add WaDi dataset module")
- **Body:** Describe what the module will do — loading raw data, defining the attack taxonomy, extracting features, and producing graph-ready output. Mention which dataset you're working with and where the raw data lives (`/fs/ess/PAS1266/`).
- **Label:** `models`

## 2. Assign yourself

On the right sidebar of your new issue, click **Assignees** and select your name.

If you don't see yourself in the list, ask Robert to add you as a collaborator on the repo.
