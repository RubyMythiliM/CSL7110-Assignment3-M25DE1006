-----
# Assignment 3 Report

## Movie Recommendation System

**Name:** Ruby Mythili
**Roll Number:** M25DE1006
**Course:** CSL7110 – Machine Learning with Big Data

-----

# 1. Introduction

Recommendation systems are widely used in modern applications to help users discover relevant content. Platforms such as Netflix, Amazon, and Spotify use recommendation algorithms to personalize user experience by suggesting movies, products, or music based on user preferences.

In this assignment, different recommendation system techniques were implemented using the **MovieLens Small dataset**. The goal was to explore how various recommender models work and compare their behavior. The following approaches were implemented:

* Content-Based Filtering
* User-Based Collaborative Filtering
* Item-Based Collaborative Filtering
* Matrix Factorization using Singular Value Decomposition (SVD)
* Hybrid Recommendation System

These models were implemented using Python in a Jupyter Notebook and executed in Google Colab.

---

# 2. Dataset Description

The dataset used in this assignment is the **MovieLens Small Dataset**, provided by GroupLens.

Dataset link:
[https://grouplens.org/datasets/movielens/](https://grouplens.org/datasets/movielens/)

The dataset contains movie ratings given by users along with movie metadata.

### Dataset Statistics

| Attribute | Value  |
| --------- | ------ |
| Users     | 610    |
| Movies    | 9742   |
| Ratings   | 100836 |

### Ratings Dataset Fields

| Column    | Description                   |
| --------- | ----------------------------- |
| userId    | Unique ID for each user       |
| movieId   | Unique ID for each movie      |
| rating    | Rating given by user          |
| timestamp | Time when rating was provided |

### Movie Metadata Fields

| Column  | Description             |
| ------- | ----------------------- |
| movieId | Unique movie identifier |
| title   | Movie title             |
| genres  | Genre categories        |

The ratings dataset was used to construct the **user–item interaction matrix**, which is required for collaborative filtering methods.

---

# 3. Methodology

## 3.1 Content-Based Filtering

Content-based filtering recommends movies based on similarity between item features.

In this assignment, movie **genres** were used as features to represent each movie. The genres were transformed into numerical vectors using **TF-IDF (Term Frequency–Inverse Document Frequency)**.

The similarity between movies was calculated using **cosine similarity**.

Steps followed:

1. Extract movie genres from the dataset
2. Convert genres into TF-IDF feature vectors
3. Compute cosine similarity between movie vectors
4. Recommend movies with the highest similarity scores

This method recommends movies that have similar genre characteristics to the selected movie.

---

## 3.2 User-Based Collaborative Filtering

User-based collaborative filtering recommends movies based on the behavior of similar users.

The main idea is that **users who have rated similar movies in the past will likely prefer similar movies in the future**.

Steps followed:

1. Construct a **user–item rating matrix**
2. Compute **cosine similarity between users**
3. Identify the most similar users
4. Recommend movies highly rated by similar users but not yet seen by the target user

This approach leverages patterns in user rating behavior.

---

## 3.3 Item-Based Collaborative Filtering

Item-based collaborative filtering recommends movies similar to those that a user has already liked.

Instead of comparing users, this method compares **items (movies)**.

Steps followed:

1. Transpose the user–item matrix
2. Compute cosine similarity between movie vectors
3. Identify movies with the highest similarity scores
4. Recommend those movies to the user

This method is commonly used in production recommendation systems because it is more stable when user activity changes.

---

## 3.4 Matrix Factorization (SVD)

Matrix factorization is a widely used technique for recommendation systems.

In this assignment, **Singular Value Decomposition (SVD)** was used to decompose the user–item rating matrix into latent factors.

Steps followed:

1. Construct the user–item matrix
2. Replace missing ratings with zero values
3. Apply Singular Value Decomposition
4. Reduce the dimensionality of the matrix
5. Reconstruct the predicted rating matrix

The reconstructed matrix provides **predicted ratings for unseen movies**, which can then be used to generate recommendations.

---

## 3.5 Hybrid Recommendation System

A hybrid recommendation model was implemented by combining:

* Content-based similarity scores
* Collaborative filtering predictions (SVD)

Both scores were normalized and combined using a weighted average.

Formula used:

Final Score = α × Content Score + (1 − α) × SVD Score

This approach helps combine the advantages of both methods and improves recommendation quality.

---

# 4. Results

The implemented recommendation techniques generated the following results.

### Content-Based Filtering

Using genre similarity, the system recommended movies similar to **Toy Story (1995)**.

Example recommendations included:

* Toy Story 2 (1999)
* Monsters, Inc. (2001)
* Shrek the Third (2007)
* Antz (1998)

These recommendations were generated based on similarity in movie genres.

---

### User-Based Collaborative Filtering

By identifying users with similar rating patterns, the system recommended movies such as:

* Blade Runner (1982)
* The Godfather (1972)
* Die Hard (1988)

These movies were highly rated by users who had similar preferences to the target user.

---

### Item-Based Collaborative Filtering

Using item similarity, movies similar to **Toy Story (1995)** included:

* Star Wars: Episode IV – A New Hope
* Forrest Gump
* Jurassic Park
* The Lion King

These recommendations are based on similar rating patterns across users.

---

### Hybrid Recommendation

The hybrid recommender system combined content-based similarity and collaborative filtering predictions.

Example recommendations included:

* True Lies
* Aliens
* Star Trek II: The Wrath of Khan
* The Fifth Element

This approach provided more diverse and personalized recommendations.

---

# 5. Model Evaluation

The recommendation system was evaluated using **Root Mean Squared Error (RMSE)**.

The dataset was split into training and testing sets, and the **SVD model from the Surprise library** was trained.

Result:

RMSE = **0.868**

A lower RMSE value indicates that predicted ratings are close to the actual ratings in the dataset.

---

# 6. Assumptions

The following assumptions were made during implementation:

* Missing ratings in the user–item matrix were treated as zero values.
* Cosine similarity was used to measure similarity between users and items.
* Genre information was used as the main feature for content-based filtering.
* A simple weighted average was used to combine scores in the hybrid recommender system.
* The MovieLens small dataset was assumed to be representative for testing recommendation algorithms.

---

# 7. GitHub Repository

The complete implementation of the assignment is available in the GitHub repository:

[https://github.com/RubyMythiliM/CSL7110-Assignment3-M25DE1006](https://github.com/RubyMythiliM/CSL7110-Assignment3-M25DE1006)

The repository contains:

* Jupyter Notebook implementation
* Report documentation
* Project README file



Name it exactly:

```
M25DE1006_CSL7110_Assignment3.pdf
```

### 3️⃣ Push updated REPORT.md

```
git add REPORT.md
git commit -m "Update final assignment report"
git push
```

---


