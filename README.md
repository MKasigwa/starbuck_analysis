# Starbucks Analysis

## Table of Contents

1. [Introduction](#introduction)
2. [Structure](#structure)
3. [Data Sets](#dataset)
4. [Conclusion](#conclusion)
5. [Dependencies](#dependencies)
6. [Authors](#authors)
7. [License](#license)
8. [Acknowledgements](#acknowledgements)
9. [Screenshots](#screenshots)

<a name="introduction"></a>

### Introduction

This data set contains simulated data that mimics customer behavior on the Starbucks rewards mobile app. Once every few days, Starbucks sends out an offer to users of the mobile app. An offer can be merely an advertisement for a drink or an actual offer such as a discount or BOGO (buy one get one free). Some users might not receive any offer during certain weeks. 

Not all users receive the same offer, and that is the challenge to solve with this data set.

Your task is to combine transaction, demographic and offer data to determine which demographic groups respond best to which offer type. This data set is a simplified version of the real Starbucks app because the underlying simulator only has one product whereas Starbucks actually sells dozens of products.

Every offer has a validity period before the offer expires. As an example, a BOGO offer might be valid for only 5 days. You'll see in the data set that informational offers have a validity period even though these ads are merely providing information about a product; for example, if an informational offer has 7 days of validity, you can assume the customer is feeling the influence of the offer for 7 days after receiving the advertisement.

You'll be given transactional data showing user purchases made on the app including the timestamp of purchase and the amount of money spent on a purchase. This transactional data also has a record for each offer that a user receives as well as a record for when a user actually views the offer. There are also records for when a user completes an offer. 

Keep in mind as well that someone using the app might make a purchase through the app without having received an offer or seen an offer.

<a name="structure"></a>

## Structure

Here's the file structure of the project

```
- .ipynb_checkpoints
  | - Starbucks_Capstone_notebook-checkpoint.ipynb

- data
  | - portfolio.json
  | - profile.json
  | - transcript.json

- Starbucks_Capstone_notebook.ipynb
- README.md

```
<a name="dataset"></a>

# Data Sets

The data is contained in three files:

* portfolio.json - containing offer ids and meta data about each offer (duration, type, etc.)
* profile.json - demographic data for each customer
* transcript.json - records for transactions, offers received, offers viewed, and offers completed

Here is the schema and explanation of each variable in the files:

**portfolio.json**
* id (string) - offer id
* offer_type (string) - type of offer ie BOGO, discount, informational
* difficulty (int) - minimum required spend to complete an offer
* reward (int) - reward given for completing an offer
* duration (int) - time for offer to be open, in days
* channels (list of strings)

**profile.json**
* age (int) - age of the customer 
* became_member_on (int) - date when customer created an app account
* gender (str) - gender of the customer (note some entries contain 'O' for other rather than M or F)
* id (str) - customer id
* income (float) - customer's income

**transcript.json**
* event (str) - record description (ie transaction, offer received, offer viewed, etc.)
* person (str) - customer id
* time (int) - time in hours since start of test. The data begins at time t=0
* value - (dict of strings) - either an offer id or transaction amount depending on the record

<a name="conclusion"></a>

# Conclusion
After experimenting with various models, I discovered that the LGBM Classifier not only achieved the highest F1-score of 0.58, the metric chosen for evaluating test data performance, but also exhibited the highest accuracy. Consequently, I employed this model to identify factors predicting customer offer completion. Upon refining the model, I determined that the most influential predictors are the time taken to respond, customer income, and the year of customer enrollment.

<a name="dependencies"></a>

## Dependencies

- Python 3.5+
- Machine Learning Libraries: NumPy, SciPy, Pandas, Sciki-Learn
- Model Loading and Saving Library: Pickle, sklearn
- Web App and Data Visualization: Seaborn, Plotly

<a name="authors"></a>

## Authors

- [Miracle Kasigwa](https://github.com/MKasigwa)

<a name="license"></a>

## License

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

<a name="acknowledgements"></a>

# Acknowledgements
I would like to thanks Udacity and Starbucks(https://www.starbucks.com/) for providing me with the datasets to use for this project.

<a name="screenshots"></a>
# Screenshots


