# NRC_vote_data

A curated dataset and supporting code for analyzing NRC voting records, for SECYs introduced from 1997 to 2025. This repository collects raw and processed vote data, scripts and notebooks for cleaning and analysis, and documentation to reproduce common analyses.

## Contents
- `NRC_vote_data/NRC_vote_data.csv/` — Cleaned and merged datasets ready for analysis.
- `notebooks/` — Jupyter notebooks demonstrating exploratory analysis and visualizations.
- `scripts/` — Data processing and utility scripts (Python/R).
- `README.md` — This file.

## Project goals
- Provide a clean, documented dataset of NRC votes suitable for research and reproducible analysis.
- Supply example analyses and tooling to help users explore vote patterns, commission behavior, and temporal trends.
- Make it easy for others to contribute corrections, new data, or new analyses.

## Data description
Each record in the processed dataset contains (example fields):
- `vote_id` — Unique identifier for the vote
- `date` — Date of the vote (YYYY-MM-DD)
- `issue` — Short description or category of the vote
- `member_id` — Unique identifier for the member casting the vote
- `member_name` — Member full name
- `party` — Party or affiliation
- `vote` — Vote recorded (e.g., "Yes", "No", "Abstain")
- `location` — Optional: geographic info (state, district)

## Quick start

Requirements
- Python 3.8+ (or R if you prefer)
- Recommended: create a virtual environment and install dependencies listed in `requirements.txt`.

Example: load processed CSV with pandas
```python
import pandas as pd

df = pd.read_csv("data/processed/nrc_votes_processed.csv", parse_dates=["date"])
print(df.info())
```

Run a notebook
1. Install requirements: `pip install -r requirements.txt`
2. Start Jupyter: `jupyter lab` or `jupyter notebook`
3. Open notebooks in the `notebooks/` directory.

## Provenance & sources
- Source datasets and acquisition steps should be documented in `docs/provenance.md`.
- When adding new raw data, include the original source URL, retrieval date, and any manual notes.

## Licensing & citation
- Suggested: Code under the MIT License, data under CC BY 4.0. If you prefer a different license, update `LICENSE` and `LICENSE-DATA`.
- Please cite this repository if you use the dataset in publications. Add a CITATION.cff or guidance in `docs/citation.md`.

## Contribution guide
- See `CONTRIBUTING.md` for how to propose changes, data additions, or corrections.
- Use issues to report problems or request new features.
- For data changes: open a pull request with the raw source, transformation script, and notes in `docs/provenance.md`.

## Roadmap / ideas
- Add unit tests for data validation and schema checks
- Add CI to run data integrity checks on PRs
- Expand notebooks with reproducible analysis use-cases

## Contact
Maintainer: Joy Jiang (GitHub: @JoyJiang97)  
For questions or partnership, open an issue or email (add preferred email here).

---

If you want, I can:
- Commit this README.md to `main` (or another branch) with a commit message you provide.
- Create `docs/` placeholders like `data_dictionary.md`, `provenance.md`, `contributing.md`, and a basic `requirements.txt`.
- Suggest or add a license file (MIT for code, CC BY 4.0 for data) and create `CITATION.cff`.
