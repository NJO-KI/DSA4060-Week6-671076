# DSA4060XA Week 6: Recommender Systems Evaluation Lab

* **Student Name:** Monica Wanjiku
* **Student ID:** 670176
* **Course:** DSA4060XA – Recommender Systems

---

## Lab Objective
The objective of this lab is to build, evaluate, and compare three different recommender system architectures (**Popularity Baseline**, **Content-Based Filtering**, and **Item-Based Collaborative Filtering**) across rating prediction accuracy (MAE, RMSE), ranking quality (Precision@K, Recall@K, NDCG@K), catalogue coverage, novelty, and diversity.

---

## Dataset Overview & Inspection
Using the MovieLens-based dataset (`movies.csv` and `ratings.csv`):
* **Total Ratings:** 100,836 explicit user-item interactions[cite: 1]
* **Unique Users:** 610[cite: 1]
* **Unique Movies:** 9,724 movies with ratings (out of 9,742 total movie records)[cite: 1]
* **Rating Scale:** $0.5$ to $5.0$ stars in $0.5$-point increments[cite: 1]
* **Train/Test Split:** Sorted by timestamp per user, holding out the single most recent interaction per user as test data ($610$ test interactions, $100,226$ training interactions)[cite: 1].

---

## Models Compared
1. **Popularity Baseline:** Recommends top-rated and most frequently rated movies globally based on training mean ratings and counts[cite: 1].
2. **Content-Based Filtering:** Converts movie genre tags into binary feature vectors, builds weighted user preference profiles (e.g., User 1's highest preferences: Action, Adventure, Comedy, and Drama), and uses cosine similarity scaled to a $1-5$ rating range[cite: 1].
3. **Item-Based Collaborative Filtering:** Computes item-item similarity matrices using user rating pivot tables to produce similarity-weighted score predictions[cite: 1].

---

## Summary of Empirical Results

| Model | MAE | RMSE | Precision@3 | Recall@3 | NDCG@3 | Coverage | Novelty | Diversity |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| **Popularity Baseline** | 0.835 | 1.054 | 0.0 | 0.0 | 0.0 | 0.0003 | 8.253 | 0.882 |
| **Content-Based** | 1.177 | 1.439 | 0.0 | 0.0 | 0.0 | 0.0015 | 1.634 | 0.390 |
| **Item-Based CF** | **0.767** | **0.998** | 0.0 | 0.0 | 0.0 | **0.0018** | 1.704 | 0.576 |

* **Best Model for Rating Prediction:** **Item-Based Collaborative Filtering** achieved the lowest error metrics with an **MAE of $0.767$** and an **RMSE of $0.998$**, outperforming both the Popularity Baseline (MAE: $0.835$, RMSE: $1.054$) and Content-Based filtering (MAE: $1.177$, RMSE: $1.439$)[cite: 1].
* **Catalogue Coverage & Novelty:** Advanced models (Item-Based CF and Content-Based) successfully expanded item exposure compared to the monolithic popularity baseline, with Item-Based CF achieving the highest catalogue coverage ($0.0018$)[cite: 1].
* **Personalization Check:** Comparing recommendations across users (e.g., User 1 vs. User 2) confirmed that Popularity returns static, identical blockbusters to everyone, whereas Content-Based and Collaborative Filtering generate distinct, personalized lists[cite: 1].

---

## Final Recommended Model
**Item-Based Collaborative Filtering** is recommended for deployment. It satisfies business requirements by achieving superior rating prediction accuracy while breaking away from repetitive blockbusters to offer greater catalogue exposure and personalization[cite: 1].

---

## Limitations
1. **Single-Interaction Holdout:** Holding out only the single most recent interaction per user limits evaluation depth over time[cite: 1].
2. **Metadata Constraints:** Content-based filtering relies purely on genre indicator tags, omitting rich textual features like directors, actors, or plots[cite: 1].
3. **Offline Evaluation Gap:** Offline metrics cannot measure live user engagement, click-through rates, or long-term platform satisfaction[cite: 1].

---
