## Purpose

This file contains focused, actionable guidance for AI coding agents working in this repository (Boston House Pricing Prediction). The project is small and notebook-first—follow these conventions to be immediately productive.

## Big picture

- Primary artifact: the project is implemented as a Jupyter notebook: [Linear Regression ML Implementation.ipynb](Linear%20Regression%20ML%20Implementation.ipynb). Treat the notebook as the canonical source for model code and experiments.
- Supporting doc: [README.md](README.md) contains environment/setup hints (conda, Heroku mention). There is no `src/` package, tests, or CI configs present.

## How to make changes

- Prefer non-destructive edits to the notebook: add new cells for experiments or refactors rather than editing experimental cells in-place.
- If you extract reusable code, create a new `src/` directory and add a `requirements.txt` or `environment.yml` entry; update the README accordingly.
- Do not change `LICENSE` without explicit human approval.

## Environment & run commands (discoverable)

Create the conda environment used in the README:

```bash
conda create -p venv python==3.7 -y
```

Start Jupyter for iterative work:

```bash
conda activate ./venv
jupyter lab  # or jupyter notebook
```

For converting or running notebooks non-interactively, use `nbconvert` or `papermill`.

## Project-specific patterns

- Notebook-first workflow: experiments, visualizations, and model code live inside the notebook. When creating production-ready code, extract functions/classes into `src/` and keep notebooks for demos.
- Minimal repository structure: there are no unit tests or build scripts. Aim to add minimal, self-contained modules and small test files if you introduce logic that needs verification.
- Deployment hint: README references Heroku; no Procfile or app manifest is present. If implementing deployment, add a `Procfile` and `requirements.txt` and document steps in README.

## Editing guidelines for AI agents

- Make small, reversible changes. Commit frequently with clear messages.
- When modifying the notebook, include a short Markdown cell describing the change and the reason.
- If you add new files, update `README.md` with a one-paragraph explanation and any new environment commands.

## Integration & external dependencies

- No explicit dependency manifest exists. Inspect the notebook for imports to infer required packages (e.g., `numpy`, `pandas`, `scikit-learn`, `matplotlib`). Prefer adding a `requirements.txt` when adding code.

## Where to look

- Model and experiment code: [Linear Regression ML Implementation.ipynb](Linear%20Regression%20ML%20Implementation.ipynb)
- Setup instructions and environment hint: [README.md](README.md)

## When to ask the human

- Before changing licensing or deployment targets (Heroku).
- If you need access to datasets not committed here. (No `data/` directory exists in repo root.)

## Quick checklist for PRs

- Notebook edits: include an explanatory Markdown cell and clear changelog in PR description.
- New code modules: include `requirements.txt` and a one-line usage example in `README.md`.
- Keep changes minimal and easy to revert.

---

If anything is unclear or you want the instructions tuned for a particular workflow (tests, packaging, or CI), tell me which direction and I will update this file.
