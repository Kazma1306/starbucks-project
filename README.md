# starbucks-project

This repository has all the code and report for my Udacity Data Scientist Nanodegree Capstone project.

# data files
portfolio.json - containing offer ids and meta data about each offer (duration, type, etc.)
profile.json - demographic data for each customer
transcript.json - records for transactions, offers received, offers viewed, and offers completed

# profile.json
Rewards program users (17000 users x 5 fields)

gender: (categorical) M, F, O, or null
age: (numeric) missing value encoded as 118
id: (string/hash)
became_member_on: (date) format YYYYMMDD
income: (numeric)

#portfolio.json
Offers sent during 30-day test period (10 offers x 6 fields)

reward: (numeric) money awarded for the amount spent
channels: (list) web, email, mobile, social
difficulty: (numeric) money required to be spent to receive reward
duration: (numeric) time for offer to be open, in days
offer_type: (string) bogo, discount, informational
id: (string/hash)

# transcript.json
Event log (306648 events x 4 fields)

person: (string/hash)
event: (string) offer received, offer viewed, transaction, offer completed
value: (dictionary) different values depending on event type
offer id: (string/hash) not associated with any "transaction"
amount: (numeric) money spent in "transaction"
reward: (numeric) money gained from "offer completed"
time: (numeric) hours after start of test

## This project is to evaluate success rates of offers. 
The proccesses are categorized as bellow 
----- effective offers -------

offer received --> offer viewed --> transaction --> offer completed (BOGB/discount offers)
offer received --> offer viewed --> transaction (information offers)
----- ineffective offers -----

offer received --> offer viewed !--> transaction
----- offers are received but no action taken -----

offer received !-->

We define the success route as 
offer received --> offer viewed --> offer completed 
This is because viewing offers needs to be assiciated with the experiment success

## Query 
* Which channel more contributes to customer response?
* Average response time.
* Success-fail distribution by gender.

## Model 
we use RandomForestClassifer
accuracy is the mertics we use



## Medium: https://kazma-s-1306.medium.com/starbucks-capstone-project-b55e06ba3900
