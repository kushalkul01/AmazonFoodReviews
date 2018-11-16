# AmazonFoodReviews
A splendid feature of the companies working in the space of ecommerce is that the previous buyers can leave a review on any product. The review can be positive or negative. This polarity largely depends on the words chosen for a review. The task here was to train the model on Positive (4 and 5 stars) and Negative (1 and 2 stars) reviews of Amazon Fine Food Reviews Dataset and test whether the new review will be positive or negative.

The data can be availed from Kaggle from the following link: https://www.kaggle.com/snap/amazon-fine-food-reviews

## Methodology
Since this project is about harnessing the power of words as features, we will need to convert each word into a numeric/vectorized feature.
In order to achieve that, there are 4 types of featurizations used-
a. Bag of Words Model
b. TF-IDF Model
c. Average Word2Vec Model
d. TF-IDF Weighted Word2Vec Model

The flow of program is something like this-

1. Data Loading-
  The data is saved in the form of SQLite file which can be directly loaded using pandas.

2. Data Preprocessing-

    2a. From the data, we will first remove 3 star ratings as they cannot be demarcated into positive or negative. They can be              considered as moderate.
  
    2b. The words like "the, and, this" etc do not impart any meaning to the sentence, they just add to the noise. Such words are also       called 'stopwords'. For eg in the sentence "This vermicelli tastes like heaven", the only words that impart meaning are                 'vermicelli','tastes', 'heaven'. Hence we will not consider stopwords in the data.
  
    2c. Use only root word for a group of words. For eg the words 'like, liked, liking' etc are quite similar and will be reduced to         their root form using SnowballStemmer. 
  
    2d. Remove all punctuation marks like ? , ! and HTML tags

    2e. Since the data spans a period of around 10 years, it has to be split based on time. This is also called time based splitting.

3. Featurization-

  For most of the time, all the featurization techniques mentioned above will be applied and studied. However, at times we will select     only feasible techniques. For eg Decision Tree would take long time to work on high dimentionality. So while working with decision       trees and its related technologies (like Random Forest), we will use only Word2Vec based models due to their low dimensionality.

4. Model will be applied based on scoring and its hyperparameters would be tuned using cross validation techniques. 
