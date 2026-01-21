# NRC_vote_data

A curated dataset and supporting code for analyzing NRC voting records, for SECYs introduced from 1997 to 2025. This repository collects raw and processed vote data, scripts and notebooks for cleaning[...] 

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
Each record in the processed dataset contains the following fields:

### Variables
| Variable | Description | Example |
|---|---:|---|
| `vote_id` | Unique identifier for the vote (string). Use a stable pattern across imports (e.g., year + sequence). | `V1997-001` |
| `date` | Date of the vote in YYYY-MM-DD format. | `2003-05-12` |
| `issue` | Short description or category of the vote (e.g., topic or docket summary). | `License renewal` |
| `member_id` | Unique identifier for the member casting the vote (internal id). | `M-2001-02` |
| `member_name` | Full name of the member. | `Jane A. Smith` |
| `party` | Party or affiliation (string). If not applicable, use `None` or blank. | `Independent` |
| `vote` | Vote recorded (standardized values: `Yes`, `No`, `Abstain`, `Recused`, `Not Present`). | `Yes` |
| `location` | Optional geographic info (state, district, or office). May be blank for federal-only members. | `MD` or `Washington, DC` |
| `notes` | Optional free-text notes about the vote (e.g., partial concurrence, special conditions). | `Concurred in part` |

Notes:
- Types: most fields are strings; `date` is parsable as a date. In pandas use `parse_dates=["date"]`.
- Missing values: use empty strings or standard NA markers consistent with other data in the repo (e.g., `NaN` or blank).
- Vote normalization: when merging sources, normalize vote values to the set listed above (`Yes`, `No`, `Abstain`, `Recused`, `Not Present`).

Example CSV row
```csv
vote_id,date,issue,member_id,member_name,party,vote,location,notes
V2005-034,2005-11-02,Rule change affecting inspection,M-2003-01,John Q. Public,Independent,Yes,VA,
```

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