Netflix Machine Learning Internship Tasks

This repository contains my work on five machine learning tasks prepared for the Netflix ML internship assignment. The tasks cover different areas of machine learning, including content recommendations, classification, clustering, and time-series forecasting.

I've kept each task in a separate Jupyter notebook so it's easier to understand and test them individually. The notebooks also contain the outputs and charts from my runs, which means you can review the results without having to execute everything again.

I’ve also added a "docs/" folder with a write-up for each task. These explain the approach and results in simpler terms, alongside the actual implementation in the notebooks.

Project Structure

Task| Description| Notebook| Write-up
1| Recommendation System| "Task1_Recommendation_System.ipynb"| "docs/Task1_Recommendation_System.md"
2| Content Type Prediction| "Task2_Content_Type_Prediction.ipynb"| "docs/Task2_Content_Type_Prediction.md"
3| Audience Rating Classification| "Task3_Audience_Rating_Classification.ipynb"| "docs/Task3_Audience_Rating_Classification.md"
4| Content Segmentation| "Task4_Content_Segmentation.ipynb"| "docs/Task4_Content_Segmentation.md"
5| Trend Forecasting| "Task5_Trend_Forecasting.ipynb"| "docs/Task5_Trend_Forecasting.md"

The assignment requires four out of six tasks, and I've included five in this repository.

Running the Project

If you want to try the notebooks on your own system, here's how to get started.

1. Set up the files

Extract the project folder and check that "Dataset.csv" is in the same directory as the notebooks. The notebooks use this file as their input dataset.

2. Install the dependencies

Open a terminal in the project directory and run:

pip install -r requirements.txt

3. Check the environment

Run the setup script to check whether the required libraries are available:

python check_setup.py

4. Open Jupyter Notebook

Start Jupyter with:

jupyter notebook

Open any task notebook and select Kernel → Restart & Run All. This runs the cells in order and lets you check the complete workflow, from loading the data to generating the results.

If you'd rather not configure Python on your computer, you can use Google Colab instead. Upload a notebook along with "Dataset.csv", then select Runtime → Run all.

Results to Check

I’ve listed the main outputs below so you can compare them with your own run. The numbers are approximate, and small differences may occur because of changes in library versions or execution environments.

- Task 1 – Recommendation System: The dataset should contain 8,790 rows and 10 columns. When you look up Narcos, the first recommendation should be Narcos: Mexico. Genre matching is around 93%, compared with roughly 22% for random recommendations. Same-type matching is around 97%, compared with approximately 56% for random picks.

- Task 2 – Content Type Prediction: The leakage check prints "100.0%" twice. The Random Forest model reaches around 98.7% accuracy, with an F1 score of approximately 0.978. The cross-validated F1 score is also around 0.978.

- Task 3 – Audience Rating Classification: After cleaning, around 8,708 rows should remain. The dummy baseline achieves roughly 46% accuracy, while the tuned Random Forest reaches about 62–63% accuracy, with a macro F1 score near 0.61.

- Task 4 – Content Segmentation: The selected number of clusters should be "k = 7". The notebook generates a profile table for all seven clusters, including two groups consisting almost entirely of TV shows.

- Task 5 – Trend Forecasting: The analysis uses 80 months of data, from January 2015 to August 2021. Holt-Winters gives an RMSE of around 43, compared with approximately 57 for the seasonal naive baseline. The notebook also produces a 12-month forecast covering September 2021 to August 2022.

These values are useful for checking whether the notebooks are running as expected. If your results differ significantly, rerun the notebook from the beginning before investigating further.

One thing worth checking in Task 2 is the data leakage test. A "100.0%" leakage-check result should be interpreted according to what the check actually measures; it should not automatically be treated as model accuracy or evidence of a reliable model.

Running a Notebook from the Terminal

You don't have to open Jupyter manually every time. You can also execute a notebook directly from the terminal using "nbconvert".

For example, to run Task 1:

jupyter nbconvert --to notebook --execute --inplace Task1_Recommendation_System.ipynb

To run another task, replace the notebook filename with the one you want to execute. If the command completes without an error, the notebook has finished executing successfully.

Common Issues

Dataset not found

If you get "FileNotFoundError: Dataset.csv", check that the dataset is in the expected folder. If your files are arranged differently, update "DATA_PATH" in the notebook's Step 0 cell.

Missing Python libraries

If Python reports "ModuleNotFoundError", install the dependencies using:

pip install -r requirements.txt

Charts are missing

Run the relevant cells inside Jupyter Notebook or Google Colab. A regular terminal doesn't automatically display notebook charts.

Task 3 takes longer to run

Task 3 includes hyperparameter tuning, which tests different model settings. Depending on your computer, this can take a minute or two, so a short delay is normal.

A Note Before You Start

If you're exploring the project for the first time, I'd suggest starting with one of the write-ups in "docs/" and then opening the corresponding notebook. That way, you can understand what the task is trying to solve before looking through the code.

The notebooks and write-ups are organised separately so you can focus on one task at a time, whether you want to understand the approach, inspect the results, or run the implementation yourself.