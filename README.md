# Opioid-Overprescribing

Capstone project for the online Python Data Science and Machine Learning course by CodingNomads.

## Background

The opioid crisis in the United States has created a significant societal and economical impact in the past few years. After recent interventions to decrease opioid-related deaths over the years through programs such as the naloxone program, the pandemic appears to be reversing that trend and we are seeing an increase in deaths. According to the NIH, nearly 50,000 people died from opioid-involved overdose in 2019 in the United States and the "economic burden" is estimated to be $78.5 billion. 

## Problem Statement

As a pharmacist, I tried to figure out where in the process of a person becoming addicted to opioids that an intervention would have the most impact, or would at least be the most feasible. 

One of the most common ways people acquired opioids was from a doctor's prescription. In terms of feasibility of the data that I could gather, I decided to focus this project on doctors who were overprescribing opioids, whether intentionally or unintentionally. If we can determine who is prescribing significantly more opioids than the average doctor, we can offer more education regarding the impact of opioids and proper prescribing habits, or perform an audit to see if there is more malicious intent behind the overprescribing (greed, willful negligence, etc.). 

The main question we want to answer is: 

* Can we predict which prescribers are overprescribing opioids, and thus further exacerbating the opioid crisis?

## Dataset

We use 2 datasets, both large, from the Medicare Part D [website](https://www.cms.gov/Research-Statistics-Data-and-Systems/Statistics-Trends-and-Reports/Medicare-Provider-Charge-Data/PartD2015). Medicare Part D is the part of Medicare that covers prescription drugs ("D" for drugs). The data we chose to use is from 2015, and they are ""Medicare Provider Utilization and Payment Data: 2015 Part D Prescriber" and "Medicare Provider Utilization and Payment Data: Part D Prescriber Summary Table CY2015". 

I create a subset of the data focusing on the specific specialty "family practice" due to limited computing power and time. The code is located in a separate Jupyter notebook. You can download just the "family practice.csv" dataset to use for analysis if computing is also an issue (these are large datasets).

## Solution

For this project, I decided to take multiple approaches to analyze the data. 
I first had to preprocess, and clean the data. 
Next:

* Supervised Learning
  * Create a Decision Tree Classifier
  * Tune Hyperparameters by visualizing learning and validation curves
  * Create new Decision Tree Classifier with new hyperparameters to see if scores improved
* Unsupervised Learning
  * Perform KMeans Clustering
  * Perform DBSCAN Clustering
  * Visualizing centroids for each method
* Decomposition
  * Perform Principal Components Analysis (PCA)
  * Try to visualize clusters in 2-D

## Benchmark Model

I haven't seen any other studies or projects that have done this previously in the same manner as I have (please feel free to link them to me if you find them). I decided to implement sklearn's DummyClassifier that classified randomly. 

## Evaluation Metrics

* Supervised Learning
  * F1 Score
* Unsupervised Learning
  * Silhouette score (we're not comparing against anything. Silhouette score just measures how well the clusters are separated)

## Requirements
* Python 3.9
* Python libraries (numpy, pandas, matplotlib.pyplot, scipy, seaborn, sklearn)
* Jupyter Notebook
