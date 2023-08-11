# 3-Way-Sentiment-Analysis-for-Tweets
## Overview
In this project, we'll build a 3-way polarity (positive, negative, neutral) classification system for tweets, without using NLTK's in-built sentiment analysis engine.

We'll use a logistic regression classifier, bag-of-words features, and polarity lexicons (both in-built and external). We'll also create our own pre-processing module to handle raw tweets.

## Data Used
training.json: This file contains ~15k raw tweets, along with their polarity labels (1 = positive, 0 = neutral, -1 = negative). We'll use this file to train our classifiers.

develop.json: In the same format as training.json, the file contains a smaller set of tweets. We'll use it to test the predictions of our classifiers which were trained on the training set.

## Preprocessing
The first thing that we'll do is preprocess the tweets so that they're easier to deal with, and ready for feature extraction, and training by the classifiers.

To start with we're going to extract the tweets from the json file, read each line and store the tweets, labels in separate lists.

Then for the preprocessing, we'll:

segment tweets into sentences using an NTLK segmenter
tokenize the sentences using an NLTK tokenizer
lowercase all the words
remove twitter usernames beginning with @ using regex
remove URLs starting with http using regex
process hashtags ,for this we'll tokenize hashtags,and try to break down multi-word hashtags using a MaxMatch algorithm, and the English word dictionary supplied with NLTK.
