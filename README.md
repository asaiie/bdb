# bdb
NFL Big Data Bowl 2027

Amit Erraguntla & Zubin Oommen

## Setup

Install [uv](https://docs.astral.sh/uv/getting-started/installation/), then run
this command from the repository root:

```sh
uv sync --locked
```

Everyday commands:

```sh
uv run python path/to/script.py       # Run a Python script in the project environment
uv run jupyter notebook               # Launch Jupyter Notebook
uv run jupyter notebook example.ipynb # Open an existing notebook directly
uv run ruff check .                   # Check code for lint errors
uv run ruff format .                  # Format code in place
```

To intentionally change dependencies, use `uv add PACKAGE` (or
`uv add --dev PACKAGE` for development tools), then commit both `pyproject.toml`
and `uv.lock`. Commit `.python-version` too; never commit `.venv`.

## Data

Place the nine original CSVs in `data/raw/`. Store generated datasets in
`data/processed/`. Dataset contents are ignored by Git; see [data/README.md](data/README.md)
for sharing and verification conventions.
