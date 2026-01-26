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
| `SRM_date` | SRM publication date (string in source) | `2/14/00` |
| `SRM_year` | Year of SRM publication | `2000` |
| `SRM_url` | Full URL to SRM document | `https://www.nrc.gov/sites/default/files/doc_library/cdn/legacy/reading-rm/doc-collections/commission/srm/2000/2000-0001srm.pdf` |
| `SECY_description` | Title/summary of the SECY paper | `Pilot Program for NMSS Initiative on Streamlining Inspection and Enforcement` |
| `SECY_date` | SECY publication date (string in source) | `1/3/00` |
| `SECY_year` | Year SECY was introduced/published | `2000` |
| `SECY_url` | Full URL to SECY document | `https://www.nrc.gov/docs/ML0036/ML003672266.pdf` |
| `detailed_type` | Document type/category | `Other` |
| `voter_last_name` | Commissioner last name | `Diaz` |
| `CVR_date` | Vote record date (string in source) | `2/8/00` |
| `CVR_year` | Year of the vote record | `2000` |
| `bdays_to_SRM` | Business days from CVR (vote) to SRM | `29` |
| `bdays_to_CVR` | Business days from SECY to CVR (vote) | `25` |
| `bdays_CVR_to_SRM` | Business days from CVR (vote) to SRM | `4` |
| `is_first_vote` | Row corresponds to the first vote within a SECY | `FALSE` |
| `is_last_vote` | Row corresponds to the last vote within a SECY | `TRUE` |
| `role_at_CVR` | Voter role at time of vote (CVR) | `Commissioner` |
| `voter_party` | Voter party label | `Republican` |
| `voter_start_date` | Start date of voter’s service | `8/23/96` |
| `voter_end_date` | End date of voter’s service | `6/30/01` |
| `voter_gender` | Voter gender label (as coded) | `Male` |
| `chair_at_CVR` | Chair at time of the vote (CVR) | `Meserve` |
| `voter_days_served` | Days served by voter at observation time | `1265` |
| `voter_term_number` | Term number (as coded) | `1` |
| `chair_at_SECY` | Chair at time SECY was issued | `Meserve` |
| `chair_at_SECY_start_date` | Chair’s term start date (SECY context) | `10/29/99` |
| `chair_at_SECY_end_date` | Chair’s term end date (SECY context) | `3/31/03` |
| `role_at_SECY` | Voter role at time SECY was issued | `Commissioner` |
| `SECY_before_term` | SECY occurred before voter’s term started | `FALSE` |
| `bdays_to_CVR_original` | Original construction of SECY→CVR business days | `25` |
| `bdays_to_SRM_original` | Original construction of SECY→SRM business days | `29` |
| `next_chair` | Next chair after the chair at SECY | `Diaz` |
| `bdays_before_chair_end` | Business days from event to chair term end (as coded) | `845` |
| `responsible_chair` | Chair attributed as responsible for timing (definition-specific) | `Meserve` |
| `commissioner_count_SECY` | # commissioners at SECY stage | `5` |
| `commissioner_count_CVR` | # commissioners at vote stage | `5` |
| `commissioner_count_SRM` | # commissioners at SRM stage | `5` |
| `commissioner_count_average` | Average commissioner count across stages | `5` |
| `is_commissioner_count_consistent` | Indicator that commissioner counts are consistent across stages | `1` |
| `congress_majority` | Numeric code for congressional majority (as coded) | `1` |
| `presidency_party` | Numeric code for presidency party (as coded) | `0` |
| `voter_party_code` | Numeric party code for voter | `1` |
| `same_chair` | Whether chair is the same across relevant stages (as coded) | `TRUE` |
| `voter_congress_diff` | Difference metric: voter party vs Congress majority (as coded) | `0` |
| `voter_presidency_diff` | Difference metric: voter party vs presidency party (as coded) | `1` |
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

