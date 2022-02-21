# Starbucks Capstone Project: Predict Effective Offers

## Introduction

This project was done as part of the Udacity Data Scientist
Nanodegree. The goal of the project is to use the transactional,
customer demographic data and offer data to provide develop data insights and 
models to help predict offer effectiveness.

## Installations
This project was written in Python, using Jupyter Notebook on Anaconda. The relevant Python packages for this project are as follows:

- pandas
- numpy
- math
- json
- matplotlib
- seaborn
- sklearn.model_selection (train_test_split module)
- sklearn.preprocessing (StandardScaler )
- sklearn.ensemble (Voting and Stacking Classifier)


## Datasets
The dataset used in this project is a simulated dataset provided by Starbucks meant to mimic user behavior and offer activity on the Starbucks Mobile App. The dataset was provided in JSON format
and consist of three separate files:

Portfolio.json - Data related to the different offers shared by Starbucks such as discounts, and BOGOs
* reward (int) - The amount of reward given for completing an offer
* channels (list of strings) –Distribution methods for offer
* difficulty (int) - The minimum required to spend to complete an offer
* duration (int) - Time for the offer to be open, in days
* offer_type (string) - A type of offer ie BOGO, discount, informational
* id (string) - Offer id

Profile.json - User demographic data such as Age, Income, Gender, etc.
* age (int) - age of the customer
* became_member_on (int) - date when customer created an app account
* gender (str) - gender of the customer (note some entries contain 'O' for other rather than M or F)
* id (str) - customer id
* income (float) - customer's income

Transaction.json - Contains data representing the overall user and offer activity on the Starbucks Mobile Reward app such as offers being viewed, and completed, and user transactions.
* event (str) - record description (ie transaction, offer received, offer viewed, etc.)
* person (str) - customer id
* time (int) - time in hours since the start of the test. The data begins at time t=0
* value - (dict of strings) - either an offer id or transaction amount depending on the record

## Project Goal/Problem Statement
The overarching goal of this project is to provide data tools that enable Starbucks to more efficiently expose users to offers. To this end we will deliver 1) visual analysis highlighting the offer success rates across different demographic factors, and 2) predictive models that help estimate the probability of an offer success for a given customer (binary classification problem).

## Results
A detailed review of the different insights and models developed for this project can be found [here](https://andrewangeles-17598.medium.com/starbucks-capstone-8a7f55060e47).

### Heuristics
Before jumping into the results, we start with the baseline offer success rate of roughly 48% when excluding offers of type 'informational' (no offers of type 'informational' are flagged as 'success'). Offer success is defined as a user receiving an offer, viewing an offer, and completing an offer.

* Individuals with higher income were more likely to complete an offer as individuals in the bottom quartile successfully completed offers 38% of the time while individuals in the top quartile completed offers roughly 65% of the time.
* Individuals who identified as Female or who chose not to identify, successfully completed offers 60% and 65% of the time, respectively. While individuals identified as men completed offers only 48% of the time.
* In general, users newer to the Starbucks Mobile Reward App were less likely to complete an offer as only 31% of newer users (lower quartile of platform age) completed an offer. While more seasoned users successfully completed offers about 60% of the time.

### Model Development
In this project, we implemented a variety of machine learning models commonly used in classification, namely: Logistic Regression, Random Forest Classifier, and SVM. The best individual learner was the SVM model with an accuracy of roughly 67%. Following the development of single learners, we leveraged meta-learners such as Voting Classifiers and Stacking Classifiers that leveraged the different individual learners created to create a model of models to create predictions. Both meta learners had accuracy rates of about 67%. 

During the model development process, we also leveraged GridSearch to try some hyperparameter tuning in an effort to improve model performance. As an example, looking at the Random Forest Classifier, we found the model could be improved from accuracy of 61% to 64% with different hyper-parameters. This process suggests that models developed during this project could be further improved with greater refinement of hyper-parameters.


## Licensing, Authors, Acknowledgements.
Data for the coding project was provided by Starbucks.

