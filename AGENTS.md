# Agent context

This repository is Amit Erraguntla and Zubin Oommen's collaboration for the
2027 NFL Big Data Bowl.

Before proposing or implementing analysis, read
[the competition theme](docs/competition-theme.md). That document contains
the theme and evaluation questions supplied by the collaborators. The example
topics are possibilities, not a selected research direction. No research
question has been selected yet.

Read [the dataset overview and data dictionary](docs/datasets.md) before working
with the CSVs. It records collaborator-supplied documentation, not a validated
schema; check actual files before relying on types, counts, or join keys.

## Environment and layout

- Use `uv sync --locked` to reproduce the environment and `uv run` to run commands.
- Python is pinned in `.python-version`; dependencies are declared in
  `pyproject.toml` and resolved in `uv.lock`.
- Use Polars for tabular processing, NumPy for numerical work, and Matplotlib
  and Seaborn for visualization. Jupyter Notebook is installed for exploration.
- Keep notebooks in `src/notebooks/` and reusable Python code in `src/main/`.
- Keep original CSVs in `data/raw/` unchanged. Write derived datasets to
  `data/processed/`. See [data/README.md](data/README.md).
- Do not commit datasets, `.venv/`, or credentials.
- When adding dependencies, use `uv add` (or `uv add --dev`) and update both
  `pyproject.toml` and `uv.lock`.
- Use `uv run ruff check .` and `uv run ruff format .` for linting and formatting.

## Analysis conventions

- Favor a focused question about a movement trait, position group, or drill,
  with a clear connection to on-field NFL performance.
- Explain how a coach, scout, or front office could use a result.
- Inspect actual schemas, units, identifiers, and missing values before making
  assumptions about the data. Validate join keys and row counts.
- Distinguish exploratory hypotheses from findings supported by data. Do not
  describe associations as causal effects without a justified design.
- Account for relevant football context, sample size, selection effects, and
  uncertainty. Avoid leakage across players or time when evaluating models.
- Keep transformations reproducible and record seeds and analysis choices
  where applicable. Do not invent results or undocumented dataset details.
