# Netflix Machine Learning Projects

**Name:** Shivam Gyanesh Tiwari
**Internship:** Machine Learning Internship, Auspify Technologies
**Date:** October 2026

Hi, I'm Shivam. This repository has my work for the Auspify Machine Learning Internship. Every project uses the same Netflix titles dataset (8,790 titles added between 2008 and 2021) and is a Jupyter notebook that explains each step in plain language and runs from top to bottom.

---

## My 6 projects

### Task 1 – Content Recommendation System (Easy)
**Notebook:** `Task1_Recommendation_System.ipynb`
I built a system that suggests similar Netflix titles based on genres, director, country, rating and title words. It turns each title into TF-IDF features and finds the closest ones with cosine similarity.
**Result:** 93% of the recommendations share a genre with the chosen title, compared with 22% for random picks.

### Task 2 – Content Type Prediction (Easy)
**Notebook:** `Task2_Content_Type_Prediction.ipynb`
I trained Logistic Regression, Decision Tree and Random Forest models to predict whether a title is a Movie or a TV Show. I left out `duration` and raw genre names on purpose, because both give the answer away (data leakage).
**Result:** Random Forest reached 98.7% accuracy with an F1 score of 0.978.

### Task 3 – Audience Rating Classification (Medium)
**Notebook:** `Task3_Audience_Rating_Classification.ipynb`
I grouped the 14 rating labels into Kids, Family, Teens and Adults, then trained and tuned a Decision Tree and a Random Forest with GridSearchCV.
**Result:** the tuned Random Forest reached 62.5% accuracy, against 46% for a model that always guesses the biggest group. Ratings depend on content that this data can't show, so this is a realistic ceiling.

### Task 4 – Content Segmentation (Medium)
**Notebook:** `Task4_Content_Segmentation.ipynb`
I used K-Means clustering (with PCA for the visuals) to group titles without any labels, then named each group from its real numbers.
**Result:** 7 clusters, including older feature films, kids' TV series, documentaries and stand-up, children's movies, thrillers, and crime and drama series.

### Task 5 – Trend Forecasting (Advanced)
**Notebook:** `Task5_Trend_Forecasting.ipynb`
I forecast how many titles Netflix adds per month, comparing a "same as last year" baseline with Holt-Winters and SARIMA on the last 12 months of data.
**Result:** Holt-Winters was best (RMSE about 43 vs about 57 for the baseline), and I used it to forecast the next 12 months.

### Task 6 – Content Success Analytics Engine (Advanced)
**Notebook:** `Task6_Content_Success_Analytics_Engine.ipynb`
An end-to-end pipeline: feature engineering, four models compared and tuned, automatically written business insights, a one-page visual report, and a saved model. The dataset has no views, so I defined success as a TV show reaching 2 or more seasons and say so openly in the notebook.
**Result:** ROC-AUC of about 0.76 in cross-validation and 0.82 on the test set. The top 10% of shows by score reached 2+ seasons 76% of the time, versus 32% overall.

---

## Repository contents

```
Task1_Recommendation_System.ipynb
Task2_Content_Type_Prediction.ipynb
Task3_Audience_Rating_Classification.ipynb
Task4_Content_Segmentation.ipynb
Task5_Trend_Forecasting.ipynb
Task6_Content_Success_Analytics_Engine.ipynb
Dataset.csv
screenshots/        proof of completed tasks
```

## How to run

1. Open a notebook in Google Colab (colab.research.google.com).
2. Upload `Dataset.csv` using the Files panel on the left.
3. Click **Runtime > Run all**.

On your own computer, install the libraries with `pip install pandas numpy scikit-learn matplotlib statsmodels jupyter` and keep `Dataset.csv` in the same folder as the notebooks.

## Things I want to be upfront about

- The dataset has no plot descriptions or cast, so Task 1 is less rich than it could be.
- In Task 6 "success" is a proxy (2+ seasons), not real viewing data.
- The insights describe patterns in the data, not proven causes.

## What I learned

The biggest thing I learned is that the hardest part of machine learning is often the data, not the model. In Task 2 I found two hidden leaks (`duration` and the genre names) that would have given a fake near-perfect score, so now I always ask whether a result is too good to be true.

I also learned to compare every model with a simple baseline, like random picks in Task 1 or "same as last year" in Task 5, and to keep the test set untouched until the very end. Tasks 3 and 6 taught me that a modest score can be an honest one: a rating depends on content the data can't show, and in Task 6 I had to define "success" as a proxy because there were no viewing numbers.

In Task 6 I learned how to package the work as a reusable pipeline and turn model results into plain-English business insights. With more time I would add real viewing data and plot descriptions, which would make the recommendations and the success predictions much stronger.

I used Claude, an AI assistant made by Anthropic, to help write the code and explain each step to me, and then ran the notebooks myself to check the results.
