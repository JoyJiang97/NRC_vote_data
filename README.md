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
| `SECY_number` | Unique identifier for the vote (string). The pattern is SECY-YY-XXXX. YY stands for the introduction year. (e.g., 20 means the SECY was introduced in 2000.) | `SECY-00-0001` |
| `SRM Description` | Describe the content of that SRM. | `Pilot Program for NMSS Initiative on Streamlining Inspection and Enforcement` |
| `SRM Date` | Date of the SRM publication in MM/DD/YYYY format. | `2/14/2000` |
| `SRM Year` | Year of the SRM publication in YYYY format. | `2000` |
| `SRM url` | The URL link to access the SRM file| `https://www.nrc.gov/sites/default/files/doc_library/cdn/legacy/reading-rm/doc-collections/commission/srm/2000/2000-0001srm.pdf)` |
| `Description` | Describe the content of the SECY. | `Pilot Program for NMSS Initiative on Streamlining Inspection and Enforcement` |
| `SECY Date` | Date of the SECY introduction in MM/DD/YYYY format. | `1/3/2000` |
| `SECY Year` | Year of the SECY introduction in YYYY format. | `2000` |
| `SECY url` | The URL link to access the SECY file| `https://www.nrc.gov/sites/default/files/doc_library/cdn/legacy/reading-rm/doc-collections/commission/srm/2000/2000-0001srm.pdf)` |
| `detailed_type` | Unique identifier for the member casting the vote (internal id). | `M-2001-02` |
| `title` | Unique identifier for the member casting the vote (internal id). | `M-2001-02` |
| `voter` | Unique identifier for the member casting the vote (internal id). | `M-2001-02` |
| `Vote Date` | Date of the vote in MM/DD/YYYY format. | `2/8/2000` |
| `CVR Year` | Year of the vote in YYYY format. | `2000` |
| `SRM Business Days` | How many business days does it take from SECY introduction to final SRM? | `29` |
| `Vote Business Days` | How many business days does it take from SECY introduction to this vote? | `25` |
| `Vote_SRM Business Days` | How many business days does it take from this vote to final SRM? | `4` |
| `First_vote` | Is this the first vote of this SECY? | `FALSE` |
| `Last_vote` | Is this the last vote of this SECY? | `TRUE` |
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
