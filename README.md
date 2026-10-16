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
1. **Popularity Baseline:** Recommends top-rated and most frequently rated movies globally.
2. **Content-Based Filtering:** Converts genres into binary features, builds weighted user preference profiles, and uses cosine similarity.
3. **Item-Based Collaborative Filtering:** Computes item-item similarity matrices using user rating pivot tables.

---

## Key Empirical Findings
* **Best Rating Predictor:** **Item-Based Collaborative Filtering** achieved the lowest MAE ($0.924$) and RMSE ($1.070$).
* **Personalization:** Content-Based and Collaborative Filtering successfully generated personalized recommendation lists per user, whereas Popularity returned uniform lists.

---
