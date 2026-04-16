# Onboarding Track

Six assignments that take a new undergraduate from "just joined the lab" to "productive with the lab's tool stack." Spans ~4 weeks.

## How to use this folder

Each assignment has a full **guide** on the MkDocs site ([osu-car-msl.github.io/lab-setup-guide/assignments](https://osu-car-msl.github.io/lab-setup-guide/assignments/)) and — if it has a hands-on coding component — a **template** here that you fill in while following the guide.

> **Read the guide → open the template → fill it in → publish the result.**

## Assignments

| # | Guide (MkDocs) | Template (this folder) | Notes |
|---|----------------|------------------------|-------|
| 1 | [Personal Website](https://osu-car-msl.github.io/lab-setup-guide/assignments/personal-website/) | — | Procedural only; no code template |
| 2a | [Exploratory Data Analysis](https://osu-car-msl.github.io/lab-setup-guide/assignments/exploratory-data-analysis/) | [`02a-eda.ipynb`](02a-eda.ipynb) | Polars + altair + sklearn |
| 2b | [Research Infrastructure](https://osu-car-msl.github.io/lab-setup-guide/assignments/concepts-admin-setup/) | [`02b-research-infra.ipynb`](02b-research-infra.ipynb) | SQL experiment tracker (accounts in guide) |
| 2c | [AI-Augmented Development](https://osu-car-msl.github.io/lab-setup-guide/assignments/ai-augmented-development/) | [`templates/`](templates/) | Starter `CLAUDE.md` + `copilot-instructions.md` |
| 3a | [Package Management Concepts](https://osu-car-msl.github.io/lab-setup-guide/assignments/package-management-concepts/) | [`03a-package-management.ipynb`](03a-package-management.ipynb) | Shell-heavy notebook using `!` cells |
| 3b | [Neural Network from Scratch](https://osu-car-msl.github.io/lab-setup-guide/assignments/neural-network-from-scratch/) | [`03b-nn-from-scratch.ipynb`](03b-nn-from-scratch.ipynb) | numpy only; forward/backward stubs |

## Scheduling

- **2a + 2b + 2c** — assigned together, 2 weeks total.
- **3a + 3b** — assigned together, 2 weeks total.

## Deliverables

Every assignment ends with a blog post on your personal Quarto site. See the [Publishing Guide](https://osu-car-msl.github.io/lab-setup-guide/assignments/publishing-guide/) for the full workflow.

## Templates folder

`templates/` contains starter files you copy into your own project repos:

- `templates/CLAUDE.md` — drop into the root of your 2a EDA repo
- `templates/copilot-instructions.md` — drop into `.github/` of your 2a EDA repo

Customize each to match your actual project before committing.
