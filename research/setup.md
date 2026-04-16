# Assignment Setup

Complete these steps once before opening any of the assignment notebooks.

## 1. Open a terminal on OSC

Log in to OSC via [OnDemand](https://ondemand.osc.edu/) (Clusters → Shell Access) or SSH:

```bash
ssh <your-username>@pitzer.osc.edu
```

All commands below run on the OSC login node.

## 2. Configure Git

Set your name and email so commits are attributed to you:

```bash
git config --global user.name "Your Name"
git config --global user.email "your-email@example.com"
```

### SSH key for GitHub

OSC login nodes can't do browser-based auth, so you need an SSH key:

```bash
# Generate a key (press Enter at all prompts to accept defaults)
ssh-keygen -t ed25519 -C "your-email@example.com"

# Print the public key
cat ~/.ssh/id_ed25519.pub
```

Copy the output, then go to [GitHub → Settings → SSH Keys → New SSH Key](https://github.com/settings/keys) and paste it.

Test that it works:

```bash
ssh -T git@github.com
# Should print: "Hi <username>! You've successfully authenticated..."
```

## 3. Install the GitHub CLI (gh)

`gh` lets you create issues, PRs, and repos from the terminal:

```bash
# Download and extract
curl -LsSf https://github.com/cli/cli/releases/download/v2.67.0/gh_2.67.0_linux_amd64.tar.gz | tar xz -C /tmp
cp /tmp/gh_2.67.0_linux_amd64/bin/gh ~/.local/bin/

# Authenticate (follow the prompts — choose SSH when asked)
gh auth login
```

Verify:

```bash
gh --version
```

## 4. Clone the assignments repo

```bash
cd ~
git clone git@github.com:frenken-lab/lab-assignments.git
cd lab-assignments
```

## 5. Install uv (Python package manager)

[uv](https://docs.astral.sh/uv/) is a fast Python package manager that replaces pip + virtualenv:

```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
```

Verify:

```bash
uv --version
```

If it says `command not found`, restart your terminal — the installer adds `~/.local/bin` to your PATH but that only takes effect in new shells.

## 6. Install dependencies

Load OSC's Python 3.12, then let uv create the venv and install everything from the lockfile:

```bash
module load python/3.12
uv sync --python $(which python3)
```

This creates a `.venv/` directory and installs all pinned dependencies from `uv.lock`. Everyone gets the exact same versions.

## 7. Activate the virtual environment

```bash
source .venv/bin/activate
```

Your prompt should show `(.venv)` at the beginning. **You need to run this every time you open a new terminal.**

## 8. Register the Jupyter kernel

Jupyter won't see your venv unless you register it as a named kernel:

```bash
python -m ipykernel install --user --name=lab-assignments --display-name="Lab Assignments"
```

This creates a kernel spec that points to your `.venv` Python. You only need to do this once — it persists across sessions. When you open a notebook, select the **"Lab Assignments"** kernel.

## 9. Verify the install

```bash
python -c "
import polars, pandas, altair, networkx
print('polars', polars.__version__)
print('pandas', pandas.__version__)
print('altair', altair.__version__)
print('networkx', networkx.__version__)
"
```

You should see version numbers for all four. If you get an `ImportError`, re-run step 6 (`uv sync`).

## 10. Launch Jupyter

**Option A — OSC OnDemand (recommended):**

1. Go to [ondemand.osc.edu](https://ondemand.osc.edu/) → Interactive Apps → Jupyter
2. Set working directory to `~/lab-assignments`
3. Under "Python version", make sure it picks up your `.venv/`
4. Launch and open a notebook

**Option B — Command line:**

```bash
jupyter notebook --no-browser
```

This prints a URL with a token. Copy it and open in your browser.

**Verify the kernel:** In any notebook, run this in a cell:

```python
import sys
print(sys.executable)
```

It should end with `.venv/bin/python`. If it doesn't, the kernel is using the wrong Python — see Troubleshooting.

## Quick reference: every new terminal session

```bash
cd ~/lab-assignments
module load python/3.12
source .venv/bin/activate
```

## Troubleshooting

| Problem | Fix |
|---------|-----|
| `uv: command not found` | Restart terminal, or `export PATH="$HOME/.local/bin:$PATH"` |
| `gh: command not found` | Same as above — check `~/.local/bin/gh` exists |
| `module: command not found` | You're not on an OSC node |
| `git@github.com: Permission denied` | SSH key not added to GitHub, or not loaded. Run `ssh-add ~/.ssh/id_ed25519` |
| `ImportError` after install | `.venv` not activated. Run `which python` — should show `.venv/bin/python` |
| Jupyter can't find packages | Wrong kernel selected. Make sure you pick **"Lab Assignments"** from the kernel menu, not the default Python. Verify with `import sys; print(sys.executable)` in a cell |
| "Lab Assignments" kernel not in list | Re-run step 8: `python -m ipykernel install --user --name=lab-assignments --display-name="Lab Assignments"` |
| `pip install` instead of `uv sync` | Use `uv sync` — it installs from the lockfile so everyone has the same versions |
