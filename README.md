# Binary Classification with NLP

## Problem Statement

To build multiple binary classification models to classify the scraped data from Pushshift's API and compare the models performance. Aslo to do exploratory data analysis.

## URLs used for Web Scraping

- https://api.pushshift.io/reddit/search/submission?subreddit=iphone
- https://api.pushshift.io/reddit/search/submission?subreddit=android

## Data Dictionary


|Feature|Type|Description|
|---|---|---|
|id|object|Comment ID|
|author|object|Name of the Author| 
|is_premium|int|Is the Author premium user or not| 
|score|int|Comment score| 
|body|object|Text content of the Comment| 
|subreddit|int|post category 0-iphone, 1-Android| 


## Summary
The work starts with scraping of data from the above mentioned URLs, after getting the response from an API required fields are mapped and stored into a dataframe. The data collected is from past 75 days at the rate of 100 comments from each day for each category.

The data is checked for null values and removed if any. Then datatype conversions and column name renaming is done at required stages. Then the cleaned dataset is exported into .csv file.

NLP is done with the help of countvectorizer for the 'author' and 'body' columns, the vector is fitted and then transformed. The transformed data is then converted into a dataframe.

The Exploratory Data Analysis is done with required visualizations and statistics. The input features are selected and the output to be predicted is determined. Then the input dataset is splitted into test and train data. A Logistic regression model is created and trained. The metrics of the model is then generated to get deep insight on the model. Then Random forest classifier model is created and trained. The performance is then evaluated.

## Conclusion 
From the Observation of various evaluation parameters such as accuracy, cross validation and confusion matrix, it is seen that there is a significant difference in performance of Logistic Regression model and Random Forest Classifier. Both the models performs well with the test data with >70% accuracy. At times we can observe similar performance from both the model. The Logistic regression model performance is consistent and have better accuracy.

This solution can be enhanced and used in various social media platforms and forums to classify the genuine post from the violent ones. Further the genuine post can be tagged to the appropriate classes.
