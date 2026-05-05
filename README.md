# Predicting Movie Ratings Using Film Features

**DSA 210 Introduction to Data Science – Term Project**

---

## Project Overview

The film industry generates enormous amounts of data, but predicting whether a film will resonate with audiences remains a challenging task. IMDb ratings are one of the most widely used indicators of movie quality and audience satisfaction.

This project explores whether objective film features — such as **budget**, **genre**, **runtime**, **vote count**, and **revenue** — can be used to predict a movie's audience rating using machine learning techniques.

---

## Motivation

Understanding what drives movie ratings can be valuable for:
- **Producers** – to make data-informed production decisions
- **Distributors** – to evaluate commercial potential
- **Streaming platforms** – to better curate and recommend content

---

## Data Source

**TMDB 5000 Movie Dataset** (Kaggle – The Movie Database)

Two CSV files were used and merged on a shared movie ID:
- `tmdb_5000_movies.csv` – budget, revenue, genres, runtime, release date, vote average, vote count
- `tmdb_5000_credits.csv` – cast and crew (director extracted)

TMDB's `vote_average` field is used as the target variable. It represents audience ratings on a 1–10 scale, comparable to IMDb scores.

After cleaning and outlier removal, the final dataset contains **4,274 movies**.

---

## Approach

### 1. Data Cleaning & Preprocessing
- JSON-encoded columns (genres, cast, crew) parsed
- Zero-encoded budget/revenue entries replaced with NaN
- Low-quality rows filtered (unreleased, <10 votes, missing runtime)
- Outliers removed using the IQR method

### 2. Exploratory Data Analysis
- Rating distribution, trends over time, genre and language comparisons
- Correlation matrix and scatter plots for numerical features
- Budget tier analysis

### 3. Hypothesis Testing
- **H1** – Vote count is positively correlated with rating
- **H2** – High-budget films are rated differently from low-budget films
- **H3** – Genre has a significant effect on rating
- **H4** – English-language films vs non-English films

### 4. Machine Learning
Seven regression models trained and compared:

| Model | RMSE | R² |
|---|---|---|
| **Gradient Boosting** | **0.6503** | **0.4284** |
| Random Forest | 0.6576 | 0.4154 |
| Ridge | 0.6763 | 0.3817 |
| Linear Regression | 0.6766 | 0.3811 |
| Lasso | 0.6785 | 0.3777 |
| XGBoost | 0.6918 | 0.3530 |
| Decision Tree | 0.7475 | 0.2448 |

Models evaluated using **RMSE** and **R²**. 5-fold cross-validation applied to the top 3 models.

### 5. Feature Importance
`log_votes` (vote count) was the most important feature across all tree models, consistent with H1. Secondary features were `popularity`, `log_revenue`, and `runtime`.

---

## Key Findings

- Gradient Boosting achieved the best performance (R² = 0.43, RMSE = 0.65)
- Vote count is the strongest predictor of rating
- Low-budget films are rated slightly higher than high-budget films on average
- Non-English films are rated higher than English films in this dataset
- Genre significantly affects ratings (Drama, Documentary > Action, Comedy)

---

## Tools & Technologies

- Python (pandas, numpy, scikit-learn, xgboost, statsmodels, matplotlib, seaborn)
- Jupyter Notebook
- TMDB 5000 Dataset (Kaggle)

---

## Author

**DSA 210 – Introduction to Data Science**
Yağız Mert Göçmen
