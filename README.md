## Snake AI (PyTorch) - Reinforcement Learning

This repo implements the classic Snake game and a simple Deep Q-Learning (DQN-style) agent in PyTorch that learns to play it.

**What’s inside**
- `game.py`: Snake game environment used for training (state, rewards, collisions)
- `agent.py`: training loop + epsilon-greedy action selection
- `model.py`: PyTorch model (`Linear_QNet`) and trainer (`QTrainer`)
- `helper.py`: plotting/training visualization helpers
- `snake_game_human.py`: play Snake as a human with keyboard

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
uv run python agent.py
```

### Play as a human

```powershell
uv run python snake_game_human.py
```

## Notes

- This setup uses CPU PyTorch by default (via the `requirements.txt` index URL). If you want GPU/CUDA PyTorch, adjust the PyTorch wheel index in `requirements.txt` to match your CUDA version.
