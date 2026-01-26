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
| Variable | Description | Example |
|---|---|---|
| `SECY_number` | SECY identifier (unique paper ID) | `SECY-23-0053` |
| `SRM_description` | Title/summary of the SRM document | `Staff Requirements Memo for SECY-20-XXXX...` |
| `SRM_date` | SRM publication date (string in source) | `2020-07-15` |
| `SRM_year` | Year of SRM publication | `2020` |
| `SRM_url` | Full URL to SRM document | `https://www.nrc.gov/reading-rm/doc-collections/commission/srm/2020/` |
| `SECY_description` | Title/summary of the SECY paper | `Proposed rule on...` |
| `SECY_date` | SECY publication date (string in source) | `2020-05-01` |
| `SECY_year` | Year SECY was introduced/published | `2020` |
| `SECY_url` | Full URL to SECY document | `https://www.nrc.gov/reading-rm/doc-collections/commission/secys/2020/` |
| `detailed_type` | Document type/category | `Proposed Rule` |
| `voter_last_name` | Commissioner last name | `Klein` |
| `CVR_date` | Vote record date (string in source) | `2020-06-10` |
| `CVR_year` | Year of the vote record | `2020` |
| `bdays_to_SRM` | Business days from vote to SRM (derived timing metric) | `35.0` |
| `bdays_to_CVR` | Business days from SECY to vote record (derived timing metric) | `42.0` |
| `bdays_CVR_to_SRM` | Business days from CVR to SRM | `12.0` |
| `is_first_vote` | Row corresponds to the first vote within a SECY | `True` |
| `is_last_vote` | Row corresponds to the last vote within a SECY | `False` |
| `role_at_CVR` | Voter role at time of vote (CVR) | `Commissioner` |
| `voter_party` | Voter party label | `R` |
| `voter_start_date` | Start date of voter’s service | `2018-01-01` |
| `voter_end_date` | End date of voter’s service | `2023-12-31` |
| `voter_gender` | Voter gender label (as coded) | `F` |
| `chair_at_CVR` | Chair at time of the vote (CVR) | `Klein` |
| `voter_days_served` | Days served by voter at observation time | `620` |
| `voter_term_number` | Term number (as coded) | `2` |
| `chair_at_SECY` | Chair at time SECY was issued | `Klein` |
| `chair_at_SECY_start_date` | Chair’s term start date (for SECY context) | `2017-11-01` |
| `chair_at_SECY_end_date` | Chair’s term end date (for SECY context) | `2021-01-20` |
| `role_at_SECY` | Voter role at time SECY was issued | `Commissioner` |
| `SECY_before_term` | SECY occurred before voter’s term started | `False` |
| `bdays_to_CVR_original` | Original construction of SECY→CVR business days | `45.0` |
| `bdays_to_SRM_original` | Original construction of SECY→SRM business days | `60.0` |
| `next_chair` | Next chair after `chair_at_SECY` | `Hanson` |
| `bdays_before_chair_end` | Business days from event to chair term end | `80.0` |
| `responsible_chair` | Chair attributed as responsible for timing (definition-specific) | `Klein` |
| `commissioner_count_SECY` | # commissioners at SECY stage | `5` |
| `commissioner_count_CVR` | # commissioners at vote stage | `4` |
| `commissioner_count_SRM` | # commissioners at SRM stage | `5` |
| `commissioner_count_average` | Average commissioner count across stages | `4.67` |
| `consistency_count` | Count/score of consistency conditions met (as coded) | `1` |
| `congress_majority` | Numeric code for congressional majority (as coded) | `1.0` |
| `presidency_party` | Numeric code for presidency party (as coded) | `1` |
| `voter_party_code` | Numeric party code for voter | `1.0` |
| `voter_congress_diff` | Party difference metric: voter vs Congress | `0.0` |
| `voter_presidency_diff` | Party difference metric: voter vs presidency | `1.0` |
| `post_Ostendorff` | Indicator for post-Ostendorff period | `True` |


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

