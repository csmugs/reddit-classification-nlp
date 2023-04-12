# Project 3 - Subreddits

## Problem Statement

This is a binary classification problem asking if we can predict the Subreddit, cats or dogs, based on selftext or the title, or both.

The ideal outcome is to provide the marketing team with top 'Buzz Words' they can use to directly appeal to either dog or cat lovers. We also aim to be able to identify cat or dog owners based on the way they post on Reddit.

## Contents:

- Background
- Data Collection
- Data Cleaning
- Exploratory Data Analysis
- Modeling
- Conclusions and Recommendations

---

## Background

### Subreddits

* [`r/cats`]: Subreddits for cat posts
* [`r/dogs`]: Subreddits for dog posts


### Data Dictionary

|Feature|Type|Dataset|Description|
|---|---|---|---|
|subreddit|object|pet|The Subreddit - Either 'cats' or 'dogs'|
|selftext|object|pet|The body of the Reddit post|
|title|object|pet|The title of the Reddit post|
|text_length|int64|pet|The length of the selftext|
|title_length|int64|tpet|The length of the title|
|selftext_word_count|int64|pet|The number of words counted in the selftext|
|title_word_count|int64|pet|The number of words counted in the title|
|text_and_title|object|pet|A combination column of selftext and title|

---

### Findings on Trends in the Data

One of the most unique findings was right in the beginning during the data cleaning stage: 82% of the selftext from our 'cats' Subreddit were missing values. And considering I only selected 1000 data entries for each Subreddit, this meant I was missing almost all of the selftext for 'cats'.¶
Because selftext is considered the body of the post, a missing value when initially analyzing our data does not mean that Reddit user were posting blank messages. Instead, we can assume that if no text was present in the body, that users were instead posting images, videos, or gifs.
Lastly, our best model was a stacked model of Logistic Regression, Naive Bayes, and Random Forests, which gave us a training score of 99.23%, testing score of 96.4%, and a sensitivity of 95.6%.


### Conclusions and Recommendations

With 82% of our 'cats' selftext missing, this tells me that the majority of users prefer to post via visuals rather than text. Whereas on the other hand users joined in the 'dogs' Subreddit prefer posting with text, or at the very least, in a combination of text and visuals.
Because of this I recommend that any marketing for cat products be mainly visuals, and with as few words as possible, including only what is necessary. But with dog products, I recommend using some, all, or a combination of the following 'Buzz Words':¶
dog
just
dogs
like
time
know
vet
old
pet
need
Because cats and dogs are clearly such opposite categories, there was a high possibility of our models performing too well. To challenge this, I removed give-away stopwords such as 'dog', 'dogs', 'puppy', 'puppies', 'cat', 'cats', 'kitty', 'kitties', etc.
And with a sensitivity of 95.6%, our model's ability to correctly predict whether a text belonged to a 'cats' or 'dogs' Subreddit was impressive. However, this may still be because of how different the two Subreddits are; making it too easy for our models to perform near perfectly.

---






