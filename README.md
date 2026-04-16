# Lab Assignments

Two tracks of hands-on assignments for the MSL research lab. Pick the track that matches where you are:

| Track | For | Start here |
|-------|-----|------------|
| **[Onboarding](onboarding/)** | New undergrads joining the lab. General tools, OSC/W&B setup, Python stack, first ML project. | [`onboarding/README.md`](onboarding/README.md) |
| **[Research](research/)** | Students assigned a dataset and contributing to GraphIDS. EDA → dataframes → graph construction. | [`research/README.md`](research/README.md) |

## Prose lives in the MkDocs guide

These notebooks are **templates** — skeleton cells with TODOs. The full explanations, worked examples, and theory live in the lab setup guide:

**[OSU-CAR-MSL/lab-setup-guide](https://osu-car-msl.github.io/lab-setup-guide/assignments/)**

Read the assignment page there, then open the corresponding template here and fill it in.

## Setup

Both tracks share one environment:

```bash
# On OSC
module load python/3.12
uv venv
source .venv/bin/activate
uv sync
```

For full setup details (git, SSH, Jupyter kernel, dataset paths), see [`research/setup.md`](research/setup.md) — the same instructions apply to both tracks.

## License

MIT
