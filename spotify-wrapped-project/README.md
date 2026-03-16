# Personal Spotify Wrapped — End-to-End Data Science Project

## Project Overview

This project is a complete end-to-end data science case study inspired by Spotify Wrapped.  
Its objective is to analyze personal Spotify listening data across multiple time windows in order to uncover long-term patterns, behavioural shifts, and listening dynamics using reproducible and well-structured analytical workflows.

Rather than focusing on raw usage statistics, the project emphasizes **temporal comparison**, **custom metric design**, and **data storytelling**, demonstrating how behavioural data can be transformed into meaningful insights.

The final output includes:
- Exploratory analysis
- Comparative KPIs
- Visual storytelling
- A Wrapped-style report designed for non-technical audiences

This repository is intended as a **portfolio-ready project** showcasing applied data science skills.


## Business / Analytical Objectives

The project aims to answer the following questions:

- What defines the long-term listening identity of the user?
- How do musical preferences evolve over medium-term and short-term windows?
- When does exploration occur, and when does listening consolidate?
- Which artists form the stable core of the listening profile?
- How can behavioural patterns be summarized through interpretable KPIs?
- How can technical analysis be translated into clear and engaging storytelling?


## Data Source

The data is collected directly from the **Spotify Web API** using authenticated requests.

### Data types extracted:
- Top tracks (long-term, medium-term, short-term)
- Top artists (long-term, medium-term, short-term)
- Track metadata (duration, popularity, artist associations)

No third-party datasets are used.


## Project Structure

spotify-wrapped-project/
├── data/
│ ├── recently_played.csv
│ ├── top_artists_long_term.csv
│ ├── top_artists_medium_term.csv
│ ├── top_artists_short_term.csv
│ ├── top_tracks_long_term.csv
│ ├── top_tracks_medium_term.csv
│ └── top_tracks_short_term.csv
├── notebooks/
│ ├── 01_data_extraction.ipynb
│ ├── 02_eda.ipynb
│ └── 03_analysis.ipynb
├── wrapped_report/
│ ├── wrapped_report.md                                  # Final storytelling report (non-technical)
│ └── figures/                                           # Final visualizations
├── .env                                  
└── README.md


## Methodology

### 1. Data Extraction
- Spotify API authentication
- Programmatic extraction of user-specific listening data
- Export of raw datasets as CSV files for reproducibility

### 2. Exploratory Data Analysis (EDA)
- Cleaning and normalization of raw data
- Artist and track frequency analysis
- Popularity and duration distributions
- Period-based exploratory insights
- Identification of potential storytelling directions

### 3. Feature Engineering
- Design of a custom metric: **Estimated Listening Time (ELT)**  
  ELT combines track rank and duration to approximate listening influence.
- Careful handling of multi-artist tracks by splitting ELT proportionally
- Construction of artist-level and track-level aggregates

### 4. KPI Design and Comparative Analysis
- Global KPIs computed for each time window:
  - Unique tracks
  - Unique artists
  - Artist diversity ratio
  - Total ELT
  - ELT concentration (Top 5 artists)
  - Track recurrence ratio
- Direct comparison of long-term, medium-term, and short-term behaviour

### 5. Core Artist & Evolution Analysis
- Identification of artists appearing across all periods (identity core)
- Analysis of their influence over time
- Construction of an **Artist Evolution Matrix** to classify trends:
  - Stable
  - Emerging
  - New
  - Declining
  - Episodic

### 6. Storytelling & Reporting
- Translation of quantitative results into a Wrapped-style narrative
- Separation of technical notebooks from the final storytelling report
- Focus on clarity, interpretability, and visual communication


## Key Insights

- The listening profile is defined by a **stable long-term core**, not by short-lived trends.
- The medium-term period represents the highest level of exploration and diversity.
- The short-term window shows increased listening intensity and concentration.
- Changes in preferences occur gradually rather than abruptly.
- A balance exists between continuity and selective adoption of new artists.


## Skills Demonstrated

This project demonstrates proficiency in:

- Python (pandas, matplotlib, seaborn)
- API usage and authentication
- Data cleaning and preprocessing
- Feature engineering and metric design
- Comparative time-window analysis
- KPI definition and interpretation
- Data visualization best practices
- Analytical storytelling
- Project structuring and documentation
- Reproducible data science workflows


## How to Reproduce the Project

1. Clone the repository
2. Create a Spotify Developer account and obtain API credentials
3. Create a `.env` file with:
SPOTIPY_CLIENT_ID=...
SPOTIPY_CLIENT_SECRET=...
SPOTIPY_REDIRECT_URI=...
4. Install dependencies:
pip install -r requirements.txt
5. Run notebooks in order:

  - 01_data_extraction.ipynb

  - 02_eda.ipynb

  - 03_analysis.ipynb


## Final Notes

This project prioritizes analytical reasoning, interpretability, and communication over model complexity.
It is designed to reflect real-world data science workflows where understanding behaviour, defining meaningful metrics, and communicating insights are as important as technical execution.

The repository can be extended with:

  - Recommendation systems

  - Clustering of listening behaviour

  - Dashboard deployment

  - Automated pipelines



Author : **Sergio Sánchez**