# Starbucks Capstone Challenge

# DATASETS

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

# PROBLEM STATEMENT
- The problem that I chose to solve was to build a model that predicts whether a customer will respond to an offer.
- First, I will wrangle and combine the data from offer portfolio, customer profile, and transaction. Each row of this combined dataset will describe the customer demographic data, offer's attributes, and whether the offer was successful.
- Second, I will create a model based that is able to give a good accuracy metric. Accuracy measures how well a model correctly predicts whether an offer is successful.
- Third, I will obtain the important feature columns that influences the success of an offer

# RESULTS
Model: Random Forest Classifier
Accuracy: 0.672855879752

The problem that I chose to solve was to build a model that predicts whether a customer will respond to an offer.

After performing the exploratory data analysis and data wrangling, I ran a Machine Learning algorithm, specifically Random Forest to give prediction if a customer will respond to the offer (complete the offer) or not. After performing hyperparameter tuning, I was able to achieve an accuract of 67.28%.

I was also able to extract the important features (Feature Importance: refers to a numerical value that describes a feature's contribution to building a model that maximizes its evaluation metric). The analysis suggests the following top five features based on their importance:

1. Membership Days
Reasoning: People who are Starbucks member for very long are more loyal and more likely to respond to the offers.
2. Income
Reasoning: People who have comparatively high income are more likely to respond to the offers.
3. Age
Reasoning: Age plays an important factor in deciding as to how likely a person will respond to the offers.
4. Reward
Reasoning: The more the reward, the better the chance of an individual responding to the offers.
5. Gender
Reasoning: In the group of people who responds positively to the offers, the contribution of female members is more as compared to the group of people who do not respond to the offers.

I will also like to add that the column mobile and email have negligible contribution for the simple reason that the above two options are present for all kind of promotions (offers) and thereby are not providing any additional information.

# ACKNOWLEDGEMENTS
- Starbucks for the data
- Udacity for the guidance
