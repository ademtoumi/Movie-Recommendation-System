# Movie Recommendation System — Association Rule Mining

> **Machine Learning Project** | ESI-SBA | 2024/2025

## Overview

This project implements association rule mining (Apriori and FP-Growth) on the MovieLens dataset to discover movie co-occurrence patterns and generate recommendations. The system filters positive user interactions (ratings ≥ 3.5), encodes user-movie transactions, and extracts association rules by lift metric. A Streamlit application provides interactive exploration of recommendations with movie poster fetching via TMDB API.

## Methodology

1. **Data Filtering:** Keep ratings ≥ 3.5 to capture positive user preferences
2. **Transaction Encoding:** Group movies per user into binary transaction matrices
3. **Frequent Itemset Mining:** Apriori / FP-Growth with `min_support = 0.01`, `max_len = 2`
4. **Association Rules:** Generate rules with `metric = "lift"`, `min_threshold = 0.01`
5. **Recommendation:** Given a movie title, return consequent movies sorted by lift score

## Tech Stack

- Python 3.x, Streamlit
- mlxtend (TransactionEncoder, apriori, fpgrowth, association_rules)
- Pandas, NumPy, Requests
- Scikit-learn
- Jupyter Notebooks
- MLflow (experiment tracking)

## Repository Structure

```
.
├── train.ipynb                    # End-to-end pipeline notebook
├── analyze_mlflow_runs.py         # MLflow experiment analysis
├── StreamLit/
│   ├── app.py                     # Streamlit application
│   ├── requirements.txt           # App dependencies
│   └── ml-latest-small/           # MovieLens dataset
├── report.pdf                     # Project report
├── MLFlow-report.pdf              # Experiment tracking report
├── screenshot.jpeg                # App screenshot
└── README.md                      # This file
```

## Dataset

- **MovieLens ml-latest-small** (GroupLens)
- `movies.csv` — movie metadata (movieId, title, genres)
- `ratings.csv` — user ratings (userId, movieId, rating, timestamp)

## Setup

```bash
# Create virtual environment
python3 -m venv .venv
source .venv/bin/activate

# Install dependencies
pip install -r StreamLit/requirements.txt
pip install mlxtend seaborn pandas matplotlib jupyterlab

# Run Streamlit app
streamlit run StreamLit/app.py

# Open notebook
jupyter lab
```

> **Note:** Set `TMDB_API_KEY` as an environment variable before running the app. Get a free key at https://www.themoviedb.org/settings/api

## TMDB API Configuration

The app fetches movie posters from TMDB. Set your API key:

```bash
export TMDB_API_KEY="your_tmdb_api_key"
```

> Get a free API key at [https://www.themoviedb.org/settings/api](https://www.themoviedb.org/settings/api)

## Authors

**Adem Toumi** — ESI-SBA, Engineering Degree in AI & Data Science  
**Ahmed Saadi** — ESI-SBA, Engineering Degree & M2 in AI & Data Science

## License

MIT
