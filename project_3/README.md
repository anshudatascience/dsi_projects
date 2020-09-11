## Project 3: Web APIs & Classification



## Problem Statement
Nvidia is the top player in Garphic processors and AMD is trying to penetrate to gain market share in GPU. Data Science team at Nvidia keeps a track of reviews and comments across various social platforms, including Reddit post of Amd and Nvidia. The database keeps Nvidia product managers updated on what consumers are currently interested in. However, some internal system  failure caused the data of posts to get mixed up and loose the classification.

Nvidia Data science team had been given a task to classify Reddit posts of r/Nvidia and r/Amd. Natural Language Processing (NLP) and classification models, mainly Logistic Regression and Naive Bayes were used to make the binary classification. The final model will be selected based on the accuracy and ROC AUC scores. The model choosen achieved an accuracy of 0.89 and AUC of 0.88 and. This is crucial as the product managers need to know what people are discussing on both the subreddits.

Besides aiming for accuracy of our prediction, we wanted to target whether there are discussions around Amd or Nvidia so we can define the success that is evaluated by the model which has the highest score that combines both accuracy and ROC AUC score.

## Executive Summary¶
Using Reddit's API, we will be scraping posts through the subreddits of Nvidia and AMD using the 'requests' library. We used a for loop to extract posts via json and gave a randomised sleep duration between each loop. Randomised sleep helps server to not overload.

After examining the scraped data, we see that the posts selftext and the title both hold meaningful words for our analysis. We cleaned the posts by dropping the empty selftext and duplicate posts. We will do pre-processing of posts and EDA to check the most frequent words in the posts and the length of the posts. After combining the posts, we were left with the 2590 posts.

We have used 4 models include the CountVectorizer & Logistic Regression, TF-IDF & Logistic Regression, CountVectorizer & Naive Bayes and TF-IDF & Naive Bayes. GridSearchCV was used to optimise the model hyperparameters which were tuned to optimise accuracy and prevent overfitting. Comparing to the baseline score of 0.58, with all the models to find out the best model to decide on the accuracy.

Count Vectorizer & Naive Bayes classifier model achieves an accuracy of 0.88 and an AUC score 0.88. We can conclude that the |CountVectorizer & Naive Bayes classifier| is the best model with high score and Accuracy.

As mentioned in the problem statement, we are interested to find out whether the post is coming from Amd or Nvidia subreddit. The goal over here is to focus on the |accuracy & AUC ROC score of the model|.

|**Contents**|:
Importing Libraries
Data Collection
Data Cleaning
Pre-processing
Exploratory Data Analysis
Combined Dataframe & Save csv file
- Modelling
- Model #1: Count Vectorizer & Logistic Regression
- Model #2: TF-IDF & Logistic Regression
- Model #3: Count Vectorizer & Naive Bayes
- Model #4: TF-IDF & Naive Bayes
- Model Evaluation
- Model Evaluation: Confusion Matrix & Classification Report
-  ROC AUC plot 
- Identifying the Most Predictive Words
- Misclassified Data
- Conclusion and Recommendations

##  Methodology
## Data Collection
Data on two subreddits
- Nvidia and AMD  was gathered using the 'requests' library. We used a for loop to extract posts via json and gave a randomised sleep duration between each loop. Randomised sleep helps server to not overload.

|**Data Cleaning**|
The following steps were taken to clean the data:

As both datasets have over a 100 columns, we will only keep the columns that will be useful as predictors.
Remove any duplicated and null values posts
Concat both the datasets as they have same column

### Pre- processing¶
Pre-processing will help to transform our text.
The approach taken is as follows:

Remove HTML tags: As our text was collected through web scraping, there will be HTML tags present. Since these tags are not useful for classification, we will remove these.
Remove non-letters: Remove special characters and numbers
Lowercase all words and split word up
Remove stopwords: These are common words that are not useful for text classification.
Stemming words: This will convert each word to its stem form
Join words back into a string

|**Observation**| :
Wordclouds are great at providing quick snapshots of the top words appearing in each subreddit. However, we can't exactly quantify how frequently these words are appearing.
We will use CountVectorizer to tokenise our textual data and plot a barplot to visualise the top 20 most frequently occuring words for each subreddit.

- The words 'use', 'new' and 'game' are the top frequently occuring words on both subreddits. As these words are frequently seen in both subreddits, these words may not be important in helping us classify between Nvidia and Amd.

- 'ryzen' and 'xt' and 'rx'(belongs to AMD cpu,gpu and video card) more frequently appearing in Amd
- 'gtx' and 'rtx', 'ti' (belongs to gpu card) are more frequently in appearing in Nvidia

## Modeling 

- |Stratification| ensured that our train_test_split method returns training and test sets that have the same proportion of class labels as the input dataset.

The following 4 models will be built and scored against the train and test set:

CountVectorizer & Logistic Regression,
TF-IDF & Logistic Regression,
CountVectorizer & Naive Bayes
TF-IDF & Naive Bayes

|**Model| Train accuracy| Test accuracy|Precision|Recall|F1-Score|ROC AUC**|
|:---|:---:|:---:|:---:|:---:|:---:|---:|
|CountVectorizer & Logistic Regression |0.92|0.895|0.9|0.88|0.89|0.884|
|TF-IDF & Logistic Regression|0.91|0.891|0.9|0.88|	0.88|	0.88|
|CountVectorizer & Naive Bayes|0.907|0.882|0.882|0.88|0.88 |0.882|
|TF-IDF & Naive Bayes|	0.89|0.85|0.86|0.85|0.85|0.85|    
  
  
 ## Conclusion and Recommendations¶
In order to classify the subreddits Nvidia and AMD-  the data science team at Netflix built 4 models 
- CountVectorizer & Logistic Regression, TF-IDF & Logistic Regression, CountVectorizer & Naive Bayes and TF-IDF & Naive Bayes. After fine-tuning the hyperparameters of our models, the CountVectorizer & Logistic Regression  classifier was selected on the basis of its high accuracy and high AUC scores. The model achieved an accuracy of 0.89 on the test set, outperforming the baseline score of 0.587. The model achieved accuracty of 0.89 and ROC AUC of 0.884. 


 Due to some internal system failure caused the data of posts to get mixed up and loose the classification. Given that the team has managed to build a classification model, Nvidia product managers can now look back at the database and safely identify posts which belong to Nvidia or Amd. This keeps product managers well-informed on what content are coming from Amd or Nvidia posts.  A better understanding of customer discussion of likes and dislikes will help the team to make a better decision on improvement of next generation of GPU. 

|**Improvements**|: 

- In order to reduce misclassification, we can collect more training data to make better train the model 
- Once more data is obtained, other classification models like SVM, KNN and Random Forests can be used. 
- We can try using other hyperparameters to improve the accuracy and AUC ROC score
