# NRC_vote_data

A curated dataset and supporting code for analyzing NRC voting records, for SECYs introduced from 1997 to 2025. This repository collects raw and processed vote data, scripts and notebooks for cleaning and analysis, and documentation to reproduce common analyses.

## Contents
- `NRC_vote_data/NRC_vote_data.csv/` — Cleaned and merged datasets ready for analysis.
- `main_analysis_pipeline.ipynb/` — Jupyter notebooks demonstrating exploratory analysis and visualizations.
- `README.md` — This file.

## Project goals
- Provide a clean, documented dataset of NRC votes suitable for research and reproducible analysis.
- Supply example analyses and tooling to help users explore vote patterns, commission behavior, and temporal trends.
- Make it easy for others to contribute corrections, new data, or new analyses.

## Data description
| Variable | Description | Example (from `SECY-00-0001`) |
|---|---|---|
| `SECY_number` | SECY identifier (unique paper ID) | `SECY-00-0001` |
| `SRM_description` | Title/summary of the SRM document | `Pilot Program for NMSS Initiative on Streamlining Inspection and Enforcement` |
| `SRM_date` | SRM publication date (MM/DD/YYYY) | `2/14/2000` |
| `SRM_year` | Year of SRM publication | `2000` |
| `SRM_url` | Full URL to SRM document | `https://www.nrc.gov/sites/default/files/doc_library/cdn/legacy/reading-rm/doc-collections/commission/srm/2000/2000-0001srm.pdf` |
| `SECY_description` | Title/summary of the SECY paper | `Pilot Program for NMSS Initiative on Streamlining Inspection and Enforcement` |
| `SECY_date` | SECY publication date (MM/DD/YYYY) | `1/3/2000` |
| `SECY_year` | Year SECY was introduced/published | `2000` |
| `SECY_url` | Full URL to SECY document | `https://www.nrc.gov/docs/ML0036/ML003672266.pdf` |
| `detailed_type` | Document type/category | `Other` |
| `voter_last_name` | Commissioner last name | `Diaz` |
| `CVR_date` | Vote record date (MM/DD/YYYY) | `2/8/2000` |
| `CVR_year` | Year of the vote record | `2000` |
| `bdays_to_SRM` | Business days from SECY to SRM, adjusted* | `29` |
| `bdays_to_CVR` | Business days from SECY to CVR (vote), adjusted* | `25` |
| `bdays_CVR_to_SRM` | Business days from CVR (vote) to SRM | `4` |
| `is_first_vote` | Is this vote the first vote within a SECY? | `FALSE` |
| `is_last_vote` | Is this vote the last vote within a SECY? | `TRUE` |
| `role_at_CVR` | Voter role at time of vote, Commissioner or Chair | `Commissioner` |
| `voter_party` | Voter party label | `Republican` |
| `voter_start_date` | Start date of voter’s term at NRC | `8/23/96` |
| `voter_end_date` | End date of voter’s term at NRC | `6/30/01` |
| `voter_gender` | Voter gender label | `Male` |
| `chair_at_CVR` | Chair at time of the vote (CVR) | `Meserve` |
| `voter_days_served` | Days served by voter | `1265` |
| `voter_term_number` | How many terms has this voter served? | `1` |
| `chair_at_SECY` | Chair at time SECY was issued | `Meserve` |
| `chair_at_SECY_start_date` | Chair’s term start date (at time SECY was issued) | `10/29/1999` |
| `chair_at_SECY_end_date` | Chair’s term end date (at time SECY was issued) | `3/31/2003` |
| `role_at_SECY` | Voter role at time SECY was issued, Commissioner or Chair | `Commissioner` |
| `SECY_before_term` | SECY occurred before voter’s term started | `FALSE` |
| `bdays_to_CVR_original` | Original calculation of SECY→CVR business days* | `25` |
| `bdays_to_SRM_original` | Original calculation of SECY→SRM business days* | `29` |
| `next_chair` | Next chair after the chair at SECY | `Diaz` |
| `bdays_before_chair_end` | Business days from vote to chair term end | `845` |
| `responsible_chair` | Chair attributed as responsible for timing (definition-specific)*** | `Meserve` |
| `commissioner_count_SECY` | number of commissioners at SECY stage | `5` |
| `commissioner_count_CVR` | number of commissioners at vote stage | `5` |
| `commissioner_count_SRM` | number of commissioners at SRM stage | `5` |
| `commissioner_count_average` | Average commissioner count across SECY, CVR, and SRM stages | `5` |
| `is_commissioner_count_consistent` | Indicator that commissioner counts are consistent across SECY, CVR, and SRM stages (1 means consistent) | `1` |
| `congress_majority` | Numeric code for congressional majority (1 means Republican, 0 means Democrat and 0.5 means split congress)  | `1` |
| `presidency_party` | Numeric code for presidency party (1 means Republican and 0 means Democrat) | `0` |
| `voter_party_code` | Numeric party code for voter (1 means Republican, 0 means Democrat) | `1` |
| `same_chair` | Whether chair is the same across SECY, CVR, and SRM stages | `TRUE` |
| `voter_congress_diff` | Difference metric: voter party vs Congress majority | `0` |
| `voter_presidency_diff` | Difference metric: voter party vs presidency party  | `1` |
| `post_Ostendorff` | Indicator for post-Ostendorff period | `FALSE` |


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

