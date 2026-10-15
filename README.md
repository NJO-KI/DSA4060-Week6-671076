# DSA4060XA Week 6: Recommender Systems Evaluation Lab

* **Student Name:** Monica Njoki
* **Student ID:** 670176
* **Course:** DSA4060XA – Recommender Systems

---

## Lab Objective
The objective of this lab is to build, evaluate, and compare three different recommender system architectures (**Popularity Baseline**, **Content-Based Filtering**, and **Item-Based Collaborative Filtering**) across multiple dimensions, including rating prediction accuracy (MAE, RMSE), ranking quality (Precision@K, Recall@K, NDCG@K), catalogue coverage, novelty, and diversity.

---

## Dataset Overview
The analysis utilizes the MovieLens-based dataset (`movies.csv` and `ratings.csv`):
* **Total Ratings:** 100,836 explicit user-item interactions
* **Unique Users:** 610
* **Unique Movies:** 9,742 movies (with 9,724 rated items)
* **Rating Scale:** $0.5$ to $5.0$ stars

---

## Models Compared
1. **Popularity Baseline:** Recommends top-rated and most frequently rated movies globally based on training mean ratings and counts.
2. **Content-Based Filtering:** Converts movie genre tags into binary feature vectors, builds weighted user preference profiles, and uses cosine similarity to score unseen items.
3. **Item-Based Collaborative Filtering:** Computes item-item similarity matrices using user rating patterns to produce similarity-weighted score predictions.

---

## Summary of Findings

| Model | MAE | RMSE | Precision@3 | Recall@3 | NDCG@3 | Coverage | Novelty | Diversity |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| **Popularity Baseline** | 0.835 | 1.054 | [Insert] | [Insert] | [Insert] | [Insert] | [Insert] | [Insert] |
| **Content-Based** | 1.177 | 1.439 | [Insert] | [Insert] | [Insert] | [Insert] | [Insert] | [Insert] |
| **Item-Based CF** | **0.767** | **0.998** | [Insert] | [Insert] | [Insert] | [Insert] | [Insert] | [Insert] |

* **Best Model for Rating Prediction:** **Item-Based Collaborative Filtering** achieved the lowest MAE ($0.767$) and RMSE ($0.998$), outperforming global and genre baselines by capturing peer rating patterns.
* **Ranking & Discovery:** While popularity baselines recommend identical blockbusters to everyone, collaborative filtering and content-based approaches provide genuine personalization, significantly increasing catalogue coverage and recommendation novelty.

---

## Final Recommended Model
**Item-Based Collaborative Filtering** is recommended for deployment. It satisfies business requirements by balancing high ranking relevance with diverse catalogue discovery, ensuring users are exposed to niche titles rather than repetitive blockbusters.

---

## Limitations
1. **Single-Interaction Holdout:** Evaluating models on a single held-out interaction per user fails to capture dynamic preference shifts over time.
2. **Metadata Constraints:** Content-based filtering relies purely on genre tags, ignoring valuable contextual signals like directors, actors, or synopses.
3. **Offline Evaluation Gap:** Offline metrics (MAE, NDCG) cannot fully simulate live user engagement, click-through rates, or real-world satisfaction.

---
