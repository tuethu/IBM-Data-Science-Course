
# Final Assignment:
In this Assignment, you will demonstrate your understanding of the data science methodology by applying it to a given problem. Pick one of the following topics to apply the data science methodology to:

Emails
Hospitals
Credit Cards
You will have to play the role of the client as well as the data scientist to come up with a problem that is more specific but related to these topics.

# Project Title: Online Shopping Credit Cards Scram Detection


### Q1. Which topic did you choose to apply the data science methodology to? (2 points)
**My Answer** 
Credit Cards will be the topic I choose to apply the data science methodology for this assignment. 


### Q2. Next, you will play the role of the client and the data scientist. 
Using the topic that you selected, complete the Business Understanding stage by coming up with a problem that you would like to solve and phrasing it in the form of a question that you will use data to answer. (3 points)

You are required to:
Describe the problem, related to the topic you selected.
Phrase the problem as a question to be answered using data.

For example, using the food recipes use case discussed in the labs, the question that we defined was, "Can we automatically determine the cuisine of a given dish based on its ingredients?".

**My Answer**
1. Describe the problem:
Credit card scam happens while shopping online is a common issue in recent years. It can take various forms, such as a website without a secure connection, some messages with misspellings or poor grammar, some incredible purchase offers. Users have to be aware of those potential signs of those scams and take actions to protect themselves. This project will focus on how users in Japan can detect scam happens while users are doing online shopping. 
2. Phrase the problem as a question:  
The question to be answered in this project is, "How can a user in Japan detect credit card scam while shopping online?"

### Q3. Briefly explain how you would complete each of the following stages for the problem that you described in the Business Understanding stage, so that you are ultimately able to answer the question that you came up with. (5 points):

1. Analytic Approach
2. Data Requirements
3. Data Collection
4. Data Understanding and Preparation
5. Modeling and Evaluation

You can always refer to the labs as a reference with describing how you would complete each stage for your problem.

**My Answer**
1. Analytic Approach:
A Yes/No answer can be applied to this problem so we can use a classification model.

2. Data Requirements:
In order to create the appropriate model, we will require information regarding the website URL, the emails or messages users received online via SNS (LINE, Youtube,Instagram, X (fka Twitter) , TikTok, Threads, Facebook, LinkedIn)  to check if they have the following signs or not
-The website URL 
begins with a non-secure connection http:// 
variation name from the official website address
fake seller contact
require registration of bank account
-The messages/ emails contains 
misspellings or poor grammar
counterfeit coupons/gift card information 
unrealistic low price
stolen images or videos
impressive ad

3. Data Collection:
All of these data can be gathered from users' SNS accounts or email accounts (Gmail, Hotmail, yahoo, outlook etc.). For further analysis we can merge all the information of these emails/messages into one dataset and keep it in data lake or data warehouse such as Google Data Lakehouse or Google BigQuery. List of variables used in the modeling should also be created during this phrase. The preferable format of these data is in text. After extracting and merging data, to ensure data quality and efficiency, we will collaborate with programmers and DBAs for further discussion. 

4. Data Understanding and Preparation:
The redundant, misleading or missing data should be removed from the dataset since they do not represent the problem to be solved neither add value to the dataset.  Age, occupation, living areas, education, amount of money lost should be included in order to gain more insights of the study. Unavailable data will be acquired later, after obtaining intermediate results from the model. We will use text analysis to analyze unstructured or semi-structured text data. The groupings to classify the potential signs of scram will be helpful. 

We will use automation to reduce the data preparation time by around 50 percent and use the time to create better model. Besides that, domain knowledge (banking, IT) will be used to create features that enhance ML algorithms in the next phase. 


5. Modeling and Evaluation:
After the creation of the classification model, we will evaluate the results of the model to determine the efficiency in classifying the data by using the ROC curse. From this feedback we can make some adjustment such as adding parameters or changing algorithms to ensure that we can get the intended results. All of the results at this stage will be shared with stakeholders and related parties. 
