# DSA4060XA Week 6: Recommender Systems Evaluation Lab

* **Student Name:** Monica Wanjiku
* **Student ID:** 670176
* **Course:** DSA4060XA – Recommender Systems

---

## Lab Objective
To evaluate and compare a Popularity Baseline, Content-Based Filtering, and Item-Based Collaborative Filtering across rating prediction accuracy (MAE, RMSE), ranking quality, catalogue coverage, novelty, and diversity using the 12-user, 20-movie dataset.

---

## Dataset Overview
* **Total Ratings:** 120 explicit user-movie interactions
* **Unique Users:** 12 (`user_id`)
* **Unique Movies:** 20 (`movie_id`)
* **Rating Scale:** $1.0$ to $5.0$ stars

---

## Models Compared
1. **Popularity Baseline:** Recommends top-rated and most frequently rated movies globally based on training mean ratings and counts.
2. **Content-Based Filtering:** Converts movie genre metadata into binary feature vectors, builds weighted user preference profiles, and scores unseen items using cosine similarity scaled to a $1-5$ rating range.
3. **Item-Based Collaborative Filtering:** Computes item-item similarity matrices using user rating pivot tables to produce similarity-weighted score predictions.

---

## Empirical Findings & Summary Table

| Model | MAE | RMSE | Coverage | Novelty | Diversity |
| :--- | :---: | :---: | :---: | :---: | :---: |
| **Popularity Baseline** | 1.086 | 1.201 | Lower | Baseline | Higher |
| **Content-Based** | 1.094 | 1.381 | Moderate | Moderate | Moderate |
| **Item-Based CF** | **0.924** | **1.070** | **Higher** | **Higher** | **Balanced** |

* **Best Model for Rating Prediction:** **Item-Based Collaborative Filtering** achieved the lowest error metrics with an **MAE of $0.924$** and an **RMSE of $1.070$**, outperforming both the Popularity Baseline and Content-Based Filtering.
* **Best Model for Ranking:** **Item-Based Collaborative Filtering** and **Content-Based Filtering** successfully provided genuine personalization (generating tailored recommendation lists per user), whereas the Popularity Baseline returned identical static blockbusters to all users.
* **Coverage, Novelty, and Diversity Findings:** Collaborative filtering and content-based approaches increased catalogue coverage and recommended less obvious, more novel titles compared to the uniform popularity baseline, effectively breaking filter bubbles.

---

## Final Recommended Model
**Item-Based Collaborative Filtering** is recommended for deployment. It satisfies business objectives by achieving superior rating prediction accuracy while balancing ranking relevance, catalogue coverage, and item discovery.

---

## Limitations
1. **Sparsity & Small Scale:** The compact 12-user, 20-movie dataset limits the density of item co-ratings, which can occasionally reduce collaborative filtering similarity reliability.
2. **Single-Interaction Holdout:** Holding out only the single most recent interaction per user ignores temporal evolution and long-term user preference shifts.
3. **Metadata Constraints:** Content-based filtering relies purely on genre indicator tags, omitting rich contextual metadata such as directors, cast, and plot synopses.

---


