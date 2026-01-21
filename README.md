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


## Contact
Maintainer: Joy Jiang (GitHub: @JoyJiang97)  
For questions or partnership, open an issue or email (joyjiang1997@gmail.com).

