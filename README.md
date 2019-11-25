# Kaggle-Text-Classification
Using Neutral Network and SVM to classify text as whether they need to be simplified.
In many real-world applications, there is a need to make sure the text information is comprehensible/readable by the audience who do not have a high reading level. These may include students, kids, adults with learning/reading difficulties, and those who have English as a second language. The simple Wikipedia (https://en.wikipedia.org/wiki/Simple_English_Wikipedia), for example, is created for this purpose. Before the editors spend effort to simplify the text and increase its readability, it's nice to suggest them which part of the text needs to be simplified.

We set up a text classification task. Every document (a line in the data file) is a sentence from an Wikipedia article.

Your goal is to classify each document (sentence) into ONE of the two categories, based on whether it needs to be simplified.

0: the sentence does NOT need to be simplified

1: the sentence DOES need to be simplified

The training data contains 416,768 sentences, already labeled with one of the above categories. The test data contains 119,092 comments that are unlabeled. The submission should be a .csv (comma separated free text) file with a header line "ID,Category" followed by exactly 119,092 lines. In each line, there should be exactly two integers, separated by a comma. The first integer is the line ID of a test sentence **(0-119,091)**, and the second integer is the category your classifier predicts one of (0,1).

You can make 10 submissions per day. Once you submit your results, you will get an accuracy score computed based on 50% of the test data. This score will position you somewhere on the leaderboard. Once the competition ends, you will see the final accuracy computed based on 100% of the test data. The evaluation metric is the accuracy of your classifier - so the higher the better.

You can use any classifiers, any combination of features, and either supervised or semi-supervised methods. You can choose to use feature selection, or not. You can also be creative and make use of external data sources that do not contain the exact text comments in the data.

# My Code
I tackled this challenge from two fields: Through classic classification model and through deep learning.<br>
For classic classification method, I used Linear SVM, and achieved 80% accuracy.
For deep learning methods, I tried a lot of neural networks such as TextCNN, LSTM(Long-Short-Term-Memory), Han(Hierarchical Attention Network). It turns out that LSTM had the best performance, with around 70%. A good comparison between different neural network on text classification can be found here: https://medium.com/jatana/report-on-text-classification-using-cnn-rnn-han-f0e887214d5f <br>

<h2>Even though LSTM gave the best performance, it is still a lot worse than traditional methods.</h2>
This is because the natural of this challenge, whether a text needs to be simplied or not usually only depends on certain keywords, but has nothing to do with its strucutre. For example, sentences with word "I'm" in it certainly needs simplification. <br>

I did not perform the usual text data pre-processing such as removing stop-words, converting to lowercase, or stemming, because they might contain the important information about simplification. I also tried pre-process the data, and the result is way worse than before. This demonstrates my decision.

# Results and Achievement
My linear SVM achieved around 80% accuracy, which ranked #8 overall.
![GitHub Logo](https://github.com/JoelGuo1/Kaggle-Text-Classification/blob/master/Ranking.JPG)
