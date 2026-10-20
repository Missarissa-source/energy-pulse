# energy-pulse

US energy dashboard. EIA API v2 -> Python ingest -> DuckDB -> dbt -> Evidence.
Airflow orchestrates. Solo project, public repo, zero-cost tooling only.

## Environment
- Windows (PowerShell), 16 GB RAM. Give PowerShell-compatible commands.
- Python 3.13 in a project venv (.venv). Docker Desktop for Airflow only.

## Working style
- I am learning data engineering. Briefly explain non-obvious choices.
  Prefer simple, readable code over clever code.
- For anything touching more than one file, propose a plan first.
  Keep diffs small.
- Do not add dependencies, services, or paid tools without asking.
- Never read, print, or commit .env or API keys.

## Conventions
- Python: type hints, ruff, pytest.
- Raw tables are loaded as returned (strings) and typed in dbt staging.
  Loads must be idempotent.
- dbt: staging -> marts. Every model states its grain in its yml
  description and has tests on that grain.
