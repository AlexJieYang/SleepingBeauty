# SleepingBeauty

Descriptive analyses of sleeping-beauty timing, impact, disruption, novelty, exceptional papers and field heterogeneity.

## Install

Use Python 3.11. From the repository root:

```bash
python -m venv .venv
# Activate .venv using the command for your operating system.
python -m pip install -r requirements.txt
cp config.example.json config.json
jupyter lab
```

## Configure and run

Set `data_dir`, `output_dir` and `seed` in `config.json`, then open a notebook and run its cells in order with a fresh kernel. Relative directories resolve against the configuration file location. The repository root is the Jupyter working directory.

`RESEARCH_CONFIG` selects a configuration file; `RESEARCH_DATA_DIR`, `RESEARCH_OUTPUT_DIR` and `RESEARCH_SEED` provide environment overrides. The default seed is 2026. Tables use CSV, single-CSV ZIP archives or Excel. File naming is defined in `project_utils.DATA_FILES`; `input_schema.json` specifies the table field contracts.

Figures render in Jupyter. Explicit file exports use the configured output directory. Notebooks are stored with clear execution state.

## Notebooks

- `Figure 1 Distribution.ipynb`
- `Figure 2 Impact.ipynb`
- `Figure 3 Disruption.ipynb`
- `Figure 3 Novelty.ipynb`
- `Figure 4 Canon.ipynb`
- `Figure 5 heterogeneity.ipynb`

## Methods

The notebooks group papers by delay, beauty-coefficient percentile, publication period and field. Percentile-based categories use nonmissing observations. Field-specific regressions use OLS with publication-year categorical effects; the binary hit outcome uses an OLS linear-probability model. Coefficient error bars are 1.96 times model standard errors. Bootstrap figures show separate lower and upper interval distances.

Bootstrap intervals use full-size resamples of finite observations and deterministic random generators.

## Source checks

```bash
python scripts/validate_sources.py
```

This command parses Python and notebook source, validates JSON and checks notebook execution state. GitHub Actions runs the same source checks without executing research analyses.

## Citation and license

`CITATION.cff` provides software citation metadata. Cite the associated publication using its bibliographic record. Project code and documentation use the MIT license. Third-party data retain their providers' licenses and access terms.
