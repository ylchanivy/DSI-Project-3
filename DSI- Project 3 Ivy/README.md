# Problem Statement:
Documention classification in the past used to be done manually and requires high labour hour.<br>
As a marketer who is intereted in identify what are the keywords that users in the Reddit community use when discussing on 2 topics: coffee and restaurant so that the keywords can be later used in content creation.<br>
In this project, We will train a classifier to take in text input and then classify to which group the text belongs to in order to reduce labour hour and increase classification accuracy.<br>


# Dataset:
Data of 2 subreddit: Coffee & Restaurant were scrapped using Reddit API.<br>
After getting our url in json, request is sent to Reddit using a non-deafault value for the key 'User-agent' to prevent Reddit from shutting our script from accessing its API. <br> 
A status code of 200 shows that the request was received and understood ad is being processed.<br>
The Json file received is a nested dictionary, access to key 'data' and then key'children' to get the "content".<br>
As each Reddit request will only return 25 posts, a for loop is used to hit Reddit API repeatedly to collect a minimum of 1000 posts from each subreddit. The for loop will have an empty list created to store Arandom sleep duration is included at the end of loop to give anatural break in between request.<br>
The scraped data is saved in a Pandas Dataframe and exort as csv file. 


# Executive Sumamary:
coffee & restaurat has 1245 and 1228 observations respectively as on 18th October 2019 when data was scrapped.<br>
20% of the 2 data sets will later be splited in two subsets: one for training (or development) and the other one for testing (or for performance evaluation).<br>
Within the traning set, train-test-split is performed again with stratify =y ensure the train set and validation set has the approximately the same percentagea of samples of each subreddit as the complete set.<br>
2 models: Logistic Regression and Multinomial Naive Bayes is performed after CountVectorize and gridsearch is used to search for the optimum parameter. <br>The final testing daya is then predicted using the best model selected.



# Conclusion:
The best model chosen in this project is CountVectorizer Multinomial Naive Bayes tuned with hyperparameter withe the final prediction score of 94.73%.In this project, the Key Merics we are looking at Accuracy as any misclassification in the subreddit post will result in an ambiguos state as to which group of subject this word belongs to when creating content.<br><br>
Limitation:
The dataset used in this project is unproportional with more data coming from subreddit 0 and lesser from subreddit 1.<br>
Can explore using the same picked best model on a more balanced data set to check on the train, validation and prediction score.<br>
Recommendation:
To use other classifier model to see how this unproportional dataset will score.
