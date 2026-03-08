# Assignment 3 Report
## Movie Recommendation System

Name: Ruby Mythili  
Roll Number: M25DE1006  

---

# 1 Introduction

Recommendation systems help users discover relevant content by analyzing user preferences and item characteristics. These systems are widely used in platforms such as Netflix, Amazon, and Spotify.

In this assignment, different recommendation algorithms were implemented using the MovieLens dataset.

---

# 2 Dataset Description

The MovieLens Small dataset contains user ratings for movies.

Dataset statistics:

- 610 users
- 9742 movies
- 100836 ratings

Each rating contains:
- userId
- movieId
- rating
- timestamp

Movie metadata contains:
- movieId
- title
- genres

---

# 3 Methodology

## 3.1 Content-Based Filtering

Content-based filtering recommends movies based on similarity between movie features.

Steps:
1. Genres were converted into TF-IDF vectors.
2. Cosine similarity was computed between movies.
3. Similar movies were recommended based on genre similarity.

---

## 3.2 User-Based Collaborative Filtering

This approach recommends movies liked by users with similar rating behavior.

Steps:
1. User–item rating matrix was created.
2. Cosine similarity was computed between users.
3. Movies liked by similar users were recommended.

---

## 3.3 Item-Based Collaborative Filtering

Item-based filtering recommends movies similar to a selected movie.

Steps:
1. User–item matrix was transposed.
2. Cosine similarity between movies was computed.
3. Similar movies were recommended.

---

## 3.4 Matrix Factorization (SVD)

Matrix factorization decomposes the rating matrix into latent features.

Steps:
1. Missing ratings were filled with zero.
2. Singular Value Decomposition was applied.
3. Reduced latent factors were used to reconstruct predicted ratings.

---

## 3.5 Hybrid Recommendation System

A hybrid approach was implemented by combining:

- Content-based scores
- SVD predicted ratings

Scores were normalized and combined using weighted averaging.

---

# 4 Evaluation

The recommender system was evaluated using **Root Mean Squared Error (RMSE)**.

Result:

RMSE ≈ 0.868

Lower RMSE indicates better prediction accuracy.

---

# 5 Conclusion

Different recommendation techniques were implemented and compared.

Key observations:

- Content-based filtering relies on item features.
- Collaborative filtering uses user behavior.
- Matrix factorization captures hidden patterns.
- Hybrid models combine multiple techniques to improve recommendations.

These methods form the foundation of modern recommendation systems used in real-world applications.

---

# 6 GitHub Repository

https://github.com/RubyMythiliM/CSL7110-Assignment3-M25DE1006
