# Predicting churns with Spark

This project uses PySpark to predict churn based on a 240MB dataset of a fictitious music service platform, "Spartify". Check out my [blog post](https://medium.com/@yudaifurukawa/sparkify-user-churn-prediction-with-pyspark-950b5fce941a?sk=46d933464e3654201db4e9d513255eb8) for more details!


## 1. Motivation

Losing customers (aka., churn) is an important business problem, because the cost of acquiring a new customer is often much higher than retaining an existing one. Churn is a very common KPI to track for service providers and being able to predict churn can help a company to prioritize retention program on customers who are most likely to churn, taking actions even before a churn happens.

In this project, I used [Spark](https://spark.apache.org/) to analyze user activity dataset and build a machine learning model to identify users who are most likely to churn.


## 2. Project Objectives
The goal of this project is to predict which users are at risk to churn either downgrading from premium to free tier or cancelling their service altogether.

I will take the following steps in this project:
1. Load large datasets into Spark and manipulate them using pythons pyspark API.

2. Using Spark dataframes, engineer features that will help in the prediction of churn.

3. Use Spark ML to build and tune machine learning models that will predict churn.


## 3. Summary of the end-to-end problem solution
The Project starts with loading the data, dropping cases where there were no user IDs, and checking abnormalities.
Following this, the target variable (whether a user has churned or not) is defined and several features at user level are created. The original log data contains many rows for individual users. To perform binary classification, we will need to have only one row for each user.
These features are then compared across the two user groups (churn vs non-churn) and a new dataframe containing only the relevant features and the labels are created. From the new dataframe, training and testing datasets are created and used to compare Random Forest, Decision Treem, and Gradient-Boosted Tree. The models are evaluated using precision, recall, and F1-score.
Finally, the best model is chosen and hyperparameters were tuned using grid search.


## 4. Installation

- **Cloud deployment on [IBM Watson](https://www.ibm.com/watson):**

    Environment Default: Spark 2.4 & Python 3.6

    Creator: IBM

    Hardware configuration (Driver): 1 vCPU and 4 GB RAM

    Hardware configuration (Executor): 1 vCPU and 4 GB RAM

    Number of executors: 2

    Spark version: 2.4

    Software version: Python 3.6


## 5. Datasets

- **User activity dataset** from [Udacity](https://www.udacity.com/) <br>
    The dataset logs user demographic information (e.g. user name, gender, location State) and activity (e.g. song listened, event type, device used) at individual timestamps.

    A small subset (~240MB) of the full dataset was used for both exploratory data analysis and tuning the machine learning model.


## 6. Results

- it seems machine learning algorithms can predict users who will end up unsubscribing. Among the algorithms tested, the decision tree classifier did the best in all the evaluation metrics (Accuracy, precision, Recall, and F-Score). The details of the result is in my [blog post](https://medium.com/@yudaifurukawa/sparkify-user-churn-prediction-with-pyspark-950b5fce941a?sk=46d933464e3654201db4e9d513255eb8)

