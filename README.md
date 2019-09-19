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
* ## Models
  * Naive Bayes
  * Logistic regression
* ## Results
  * Naive Bayes: 
    * Mean test accuracy: 77.0 %
    * f1-score for positive class: 0.76
    * f1-score for negative class: 0.78
  * Logistic regression
    * Mean test accuracy: 76.34 %
    * f1-score for positive class: 0.77
    * f1-score for negative class: 0.76
* ## Questions
  1. Describe text processing pipeline you have selected.
  2. Why you have selected these two classification methods?
  3. Compare selected classification methods. Which one is better? Why?
  4. How would you compare selected classification methods if the dataset was imbalanced?
