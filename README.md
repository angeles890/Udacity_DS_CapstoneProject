# Starbucks Capstone Project: Predict Effective Offers

## Introduction

This project was done as part of the Udacity Data Scientist
Nanodegree. The goal of the project is to use the transactional,
customer demographic data and offer data to provide develop data insights and 
models to help predict offer effectiveness.

## Datasets
The dataset used in this project is a simulated dataset provided by Starbucks meant to mimic user behavior and offer activity on the Starbucks Mobile App. The dataset was provided in Json format
and consist of three seperate files:

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

Transaction.json - Contains data reperesenting overall user and offer activity on the Starbucks Mobile Reward app such as offers being viewed, and completed, and user transactions.
* event (str) - record description (ie transaction, offer received, offer viewed, etc.)
* person (str) - customer id
* time (int) - time in hours since the start of the test. The data begins at time t=0
* value - (dict of strings) - either an offer id or transaction amount depending on the record
