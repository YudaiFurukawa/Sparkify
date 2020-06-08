# Predicting churns with Spark

This project uses PySpark to predict churn based on a 240MB dataset of a fictitious music service platform, "Spartify". Check out my [blog post](https://medium.com/@yudaifurukawa/sparkify-user-churn-prediction-with-pyspark-950b5fce941a?sk=46d933464e3654201db4e9d513255eb8) for more details!

## 1. Motivation

Losing customers (aka., churn) is an important business problem, because the cost of acquiring a new customer is often much higher than retaining an existing one. Churn is a very common KPI to track for service providers and being able to predict churn can help a company to prioritize retention program on customers who are most likely to churn, taking actions even before a churn happens.

In this project, I used [Spark](https://spark.apache.org/) to analyze user activity dataset and build a machine learning model to identify users who are most likely to churn.

## 2. Project Objectives
The objectives of this project are:
1. Load large datasets into Spark and manipulate them using pythons pyspark API.

2. Using Spark dataframes, engineer features that will help in the prediction of churn.

3. Use Spark ML to build and tune machine learning models that will predict churn.

## 3. Installation

- **Cloud deployment on [IBM Watson](https://www.ibm.com/watson):**

    Environment Default: Spark 2.4 & Python 3.6

    Creator: IBM

    Hardware configuration (Driver): 1 vCPU and 4 GB RAM

    Hardware configuration (Executor): 1 vCPU and 4 GB RAM

    Number of executors: 2

    Spark version: 2.4

    Software version: Python 3.6


## 4. Datasets

- **User activity dataset** from [Udacity](https://www.udacity.com/) <br>
    The dataset logs user demographic information (e.g. user name, gender, location State) and activity (e.g. song listened, event type, device used) at individual timestamps.

    A small subset (~240MB) of the full dataset was used for both exploratory data analysis and tuning the machine learning model.




## 5. Results

- it seems machine learning algorithms can predict users who will end up unsubscribing. Among the algorithms tested, the decision tree classifier did the best in all the evaluation metrics (Accuracy, precision, Recall, and F-Score). The details of the result is in my [blog post](https://medium.com/@yudaifurukawa/sparkify-user-churn-prediction-with-pyspark-950b5fce941a?sk=46d933464e3654201db4e9d513255eb8)

