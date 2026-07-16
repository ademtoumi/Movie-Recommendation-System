# Movie Recommendation Using Association Rule Mining

**Machine Learning Project — ESI-SBA, 2024–2025**

---

## Overview

This project implements a movie recommendation system based on association rule mining applied to user rating data from the MovieLens dataset. Frequent itemset mining algorithms — Apriori and FP-Growth — are used to identify co-occurrence patterns between movies rated positively by the same users. The resulting association rules are exposed through an interactive Streamlit application, with experiment tracking managed via MLflow.

---

## Objectives

- Apply association rule mining to user-movie interaction data to discover meaningful co-occurrence patterns suitable for recommendation.
- Compare the Apriori and FP-Growth algorithms in terms of rule generation and computational efficiency under varying support thresholds.
- Deploy an interactive recommendation interface and establish a reproducible experiment tracking workflow using MLflow.

---

## Methodology

1. **Data Preparation.** Ratings from the MovieLens dataset (ml-latest-small, 100K+ ratings) are filtered to retain only those with a score of 3.5 or above. The filtered data is encoded as a binary user-movie transaction matrix, where each entry indicates whether a given user rated a given movie positively.

2. **Frequent Itemset Mining.** Both Apriori and FP-Growth algorithms are applied to the transaction matrix with a minimum support threshold of 0.01 and a maximum itemset length of 2, producing frequent movie pairs.

3. **Rule Generation.** Association rules are derived from the frequent itemsets and ranked by lift, prioritizing movie pairs whose co-occurrence exceeds what would be expected under independence.

4. **Streamlit Deployment.** A web application allows users to search for a movie by title and retrieve associated recommendations sorted by lift. Movie posters are fetched dynamically via the TMDB API.

5. **Experiment Tracking.** MLflow records each experimental run, logging parameters (minimum support, algorithm choice) and metrics (rule count, execution time) to facilitate systematic comparison across configurations.

---

## Technologies

Python · mlxtend · Streamlit · Pandas · NumPy · Scikit-learn · MLflow · Jupyter Notebook

---

## Repository Structure

```
movie_recommendation_sys-master/
├── StreamLit/
│   └── app.py
├── train.ipynb
├── analyze_mlflow_runs.py
├── report.pdf
└── MLFlow-report.pdf
```

---

## Report

[Project Report](report.pdf)  
[MLflow Experiment Analysis](MLFlow-report.pdf)

---

## Authors

Adem Toumi — ESI-SBA  
Ahmed Saadi — ESI-SBA
