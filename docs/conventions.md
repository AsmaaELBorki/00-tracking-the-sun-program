# Program Conventions

## Repository Structure

Each analytical repository follows the same internal structure:

- `data/`
  - `processed/` (inputs and outputs only)
- `notebooks/`
- `docs/`
- `README.md`

Raw data is never committed to analytical repositories.

## Notebook Design

Notebooks are:
- readable
- ordered
- explicit about inputs and outputs
- limited in scope

Each notebook:
- prints intermediate results
- documents assumptions in Markdown
- saves derived artifacts explicitly

## Naming Conventions

- snake_case for files and variables
- explicit suffixes for derived datasets
- no ambiguous abbreviations

Example:
`tracking_the_sun_CA_2024_config_features.parquet`
