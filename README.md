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
    * Mean test accuracy: 77.0 %
    * f1-score for positive class: 0.76
    * f1-score for negative class: 0.78
  * Logistic regression
    * Mean test accuracy: 76.34 %
    * f1-score for positive class: 0.77
    * f1-score for negative class: 0.76
* ## Questions ![](https://github.com/Antanskas/Sentiment_analysis/blob/master/repository_images/questions.png)
 #### 1. Describe text processing pipeline you have selected.  
 Because models do not work with plain text I needed to convert it to numerical representation. For that we need to have units - tokens later to be encoded. For that part I choosed keras tokenizer and splitted entiries into words (word-level tokenization). When having small units for each example, I needed to represent them numerically - to create numerical feature vectors for each example. By using tokenizer.text_to_matrix(), similarly like one_hot_encoding, I encoded each example as matrix row with lenght == number of unique words in dataset. 0 means absence of token which assigned integer value == 0's position in row. 1 means appearance of token at least once. That way I keptinformation about each examples unique words numerically
 #### 2. Why you have selected these two classification methods?    
 They are easy to implement, fast.
 #### 3. Compare selected classification methods. Which one is better? Why?  
 As we see both of them showing similar results, that way I would select using logistic regression because Naive Bayes method is based on Naive Bayes theorem where there are two really important assumptions which differs from real worl data: all features (words are independent) and position of features does not matter too.
 #### 4. How would you compare selected classification methods if the dataset was imbalanced?  
 By checking into confusion matrix, classification report. Basically f-score is good enought metrix to use on unbalanced data for checking models performance.
 
