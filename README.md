# Sentiment analysis using Naive Bayes and Logistic regression
* ## Idea ![](https://github.com/Antanskas/Sentiment_analysis/blob/master/repository_images/idea.png)
  * Analyze films review data and classify positives and negatives of them
* ## Environment ![colab img](https://github.com/Antanskas/Sentiment_analysis/blob/master/repository_images/colab.png)
  * Google colaboratory server
  * Python 3
* ## Dataset ![](https://github.com/Antanskas/Sentiment_analysis/blob/master/repository_images/books.png)
  * Film reviews [dataset](http://www.cs.cornell.edu/people/pabo/movie-review-data/rt-polaritydata.tar.gz)
    * rt-polarity.pos contains 5331 positive snippets
    * rt-polarity.neg contains 5331 negative snippets
* ## Models ![](https://github.com/Antanskas/Sentiment_analysis/blob/master/repository_images/model.png)
  * Naive Bayes
  * Logistic regression
* ## Results ![](https://github.com/Antanskas/Sentiment_analysis/blob/master/repository_images/results.png)
  * Naive Bayes: 
    * Mean test accuracy: 77.58 %
    * f1-score for positive class: 0.78
    * f1-score for negative class: 0.78
    * execution time with GridSearch: 0.259s
    * execution time without GridSearch: 0.077s
    * execution time calculating from scratch: 0.0058s
  * Logistic regression
    * Mean test accuracy: 74.70 %
    * f1-score for positive class: 0.77
    * f1-score for negative class: 0.77
    * execution time with GridSearch: 2.11s
    * execution time without GridSearch: 0.075s
* ## Questions ![](https://github.com/Antanskas/Sentiment_analysis/blob/master/repository_images/questions.png)
 #### 1. Describe text processing pipeline you have selected.  
1) Because models do not work with plain text I needed to convert it to numerical representation. For that I needed to have units - tokens later to be encoded. In a first attempt i decided to use keras tokenizer but then came to conclusion that with keras tokenizer I am loosing information about every word frequency in a sentence (one hot encoding only unique words) and do not have information about how common or unique each word is in whole dataset.  
2) Then I switched to Sklearn CountVectorizer which solves frequency problem but does not covers uniqueness. It works like one_hot_encoding but integer value of each token after encoding means frequence in the sentence.  
3) After that I came to sklearn TfidfVectorizer which covers all these problems - basically saving more information with this method. With help oh TfidfVectorizer I encoded my tokenized data matrix into sparse matrix (increase efficiency and protects from storage problems while most of the entries in each example are zeros) of tfidf scores where each score means frequency and uniqueness of each token (word). In short - lower tfidf-score means more common/frequent word in single example and more unique word in total dataset.  
Using TfidfVectorizer improves f1-scores for both methods compared with previous 2 attempts.
 #### 2. Why you have selected these two classification methods?    
 They are easy to implement, fast, doing reasonably good performance.
 #### 3. Compare selected classification methods. Which one is better? Why?  
 As we see both of them showing similar results, but for Naive Bayes method I found that we need to tune less hyperparameters. Execution time are similar when no GridSearch is using for both algorithms but if doing calculations from scratch for Naive Bayes, then its doing around 15 times faster compared with logistic regression.
 #### 4. How would you compare selected classification methods if the dataset was imbalanced?  
 By checking into confusion matrix, classification report. Basically f-score is good enought metrix to use on unbalanced data for  checking models performance because it is not affected of negative and positive examples rates.
 
