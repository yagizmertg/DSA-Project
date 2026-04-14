# Predicting IMDb Movie Ratings Using Film Features
 
**DSA 210 Introduction to Data Science – Term Project**
 
---
 
## Project Overview
 
The film industry generates enormous amounts of data, yet predicting whether a film will resonate with audiences remains a challenging task. IMDb ratings are among the most widely used indicators of movie quality and audience satisfaction.
 
This project explores whether objective film features — such as **budget**, **genre**, **runtime**, **vote count**, and **revenue** — can be used to accurately predict a movie's IMDb rating using machine learning techniques.
 
---
 
## Motivation
 
Understanding what drives IMDb ratings can be valuable for:
- **Producers** – to make data-informed production decisions
- **Distributors** – to evaluate commercial potential
- **Streaming platforms** – to better curate and recommend content
 
---
 
## Data Sources
 
| Dataset | Source | Contents |
|---|---|---|
| **IMDb Dataset** | Kaggle / IMDb Official | Movie titles, genres, ratings, vote counts, runtime |
| **TMDB Dataset** | Kaggle (The Movie Database) | Production budget, revenue, release date, genre |
 
Both datasets are publicly available on Kaggle and require no special access permissions.
 
The two datasets will be **merged using movie titles and release years** as keys. The final merged dataset is expected to contain approximately **5,000–10,000 movies** with sufficient feature coverage.
 
---
 
## Planned Approach
 
### 1. Data Collection & Merging
- Download IMDb and TMDB datasets from Kaggle
- Merge on movie title and release year
- Handle duplicates arising from the merge
 
### 2. Data Cleaning & Preprocessing
- Handle missing values (especially missing budget entries)
- Remove outliers to ensure data quality
 
### 3. Exploratory Data Analysis (EDA)
- Visualize rating distributions
- Examine correlations between features and ratings
- Compare ratings across genres, budget ranges, and release years
 
### 4. Modeling
Three regression models will be trained and compared:
- **Linear Regression** – baseline model
- **Random Forest** – captures non-linear relationships
- **Gradient Boosting** – handles complex feature interactions
 
Models will be evaluated using **RMSE** and **R²** metrics.
 
### 5. Feature Importance Analysis
Interpret which factors have the greatest impact on IMDb ratings.
 
---
 
## Expected Outcomes
 
- A predictive model capable of estimating IMDb ratings with reasonable accuracy
- **Hypothesis:** Number of votes will show the strongest correlation with rating, as popular films tend to have more stable scores
- Genre and budget are expected to show interesting but more variable relationships
 
---
 
## Deliverables
 
- **GitHub Repository** – all code and data pipeline scripts
- **Jupyter Notebook** – full analysis with visualizations
 
---
 
## Tools & Technologies
 
- Python (pandas, scikit-learn, matplotlib, seaborn)
- Jupyter Notebook
- Kaggle Datasets
 
---
 
## Author
 
**DSA 210 – Introduction to Data Science**  
Yağız Mert Göçmen
 
