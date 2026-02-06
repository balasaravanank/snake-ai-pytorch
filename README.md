## Snake AI (PyTorch) - Reinforcement Learning

This repo implements the classic Snake game and a simple Deep Q-Learning (DQN-style) agent in PyTorch that learns to play it.

**What’s inside**
- `snake_env.py`: Snake game environment used for training (state, rewards, collisions)
- `train.py`: training loop + epsilon-greedy action selection
- `dqn_model.py`: PyTorch model (`Linear_QNet`) and trainer (`QTrainer`)
- `plot_utils.py`: plotting/training visualization helpers
- `play_human.py`: play Snake as a human with keyboard

## Requirements

- Windows/macOS/Linux
- Python 3.11 (recommended)
- [`uv`](https://github.com/astral-sh/uv)

Dependencies are installed from `requirements.txt` (includes `torch`, `pygame`, `numpy`, `matplotlib`, `ipython`).

## Install uv
**pipx (recommended)**

```powershell
python -m pip install --user pipx
python -m pipx ensurepath
pipx install uv
uv --version
```

## Setup (using uv)

From the project folder:

```powershell
uv python install 3.11
uv venv --python 3.11
uv pip install -r requirements.txt
```

Note: `torch` wheels can be large. If you hit a network timeout during install:

```powershell
$env:UV_HTTP_TIMEOUT = "300"
uv pip install -r requirements.txt
```

## Run

### Train the AI agent

```powershell
uv run python train.py
```

### Play as a human

```powershell
uv run python play_human.py
```

## Notes

- This setup uses CPU PyTorch by default (via the `requirements.txt` index URL). If you want GPU/CUDA PyTorch, adjust the PyTorch wheel index in `requirements.txt` to match your CUDA version.
