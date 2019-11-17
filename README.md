# Sentiment-Classification-Analysis
**Sentiment Classification Framing Problems for a Neural Network.**

_Sentiment Analysis examines the problem of studying texts, like posts and reviews, uploaded by users on microblogging platforms, forums, and electronic businesses, regarding the opinions they have about a product, service, event, person or idea._

The most common use of Sentiment Analysis is this of classifying a text to a class. Depending on the dataset and the reason, Sentiment Classification can be binary (positive or negative) or multi-class (3 or more classes) problem.

In addition, among researchers and stakeholders, you can find either similar or completely different opinions concerning the relation between emotion detection and sentiment analysis, depending on their perspective. However, regardless the result or approach, they all adopt the same techniques.

## Analysis of a Neural Network.

The analysis is divided into sub projects -

## 1. Perparation of Dataset
### Curate a Dataset

The data in reviews.txt we're using has already been preprocessed a bit and contains only lower case characters. If we were working from raw data, where we didn't know it was all lower case, we would want to add a step here to convert it. That's so we treat different variations of the same word, like The, the, and THE, all the same way.

### Develop a Predictive Theory

By labelling and assigning the corrosponding reviews with it.

## 2. Quick Theory Validation

We'll create three Counter objects, one for words from postive reviews, one for words from negative reviews, and one for all the words. We'll Examine all the reviews. For each word in a positive review, increase the count for that word in both your positive counter and the total words counter; likewise, for each word in a negative review, increase the count for that word in both your negative counter and the total words counter.

_As you can see, common words like "the" appear very often in both positive and negative reviews. Instead of finding the most common words in positive or negative reviews, what you really want are the words found in positive reviews more often than in negative reviews, and vice versa. To accomplish this, you'll need to calculate the ratios of word usage between positive and negative reviews._

 Now,
 We check all the words you've seen and calculate the ratio of postive to negative uses and store that ratio in pos_neg_ratios.
 
 

Looking closely at the values you just calculated, we see the following:

1. Words that you would expect to see more often in positive reviews – like "amazing" – have a ratio greater than 1. The more skewed a word is toward postive, the farther from 1 its positive-to-negative ratio will be.
    Words that you would expect to see more often in negative reviews – like "terrible" – have positive values that are less than 1. The more skewed a word is toward negative, the closer to zero its positive-to-negative ratio will be.
    Neutral words, which don't really convey any sentiment because you would expect to see them in all sorts of reviews – like "the" – have values very close to 1. A perfectly neutral word – one that was used in exactly the same number of positive reviews as negative reviews – would be almost exactly 1. The +1 we suggested you add to the denominator slightly biases words toward negative, but it won't matter because it will be a tiny bias and later we'll be ignoring words that are too close to neutral anyway.

2. Right now, 1 is considered neutral, but the absolute value of the postive-to-negative rations of very postive words is larger than the absolute value of the ratios for the very negative words. So there is no way to directly compare two numbers and see if one word conveys the same magnitude of positive sentiment as another word conveys negative sentiment. So we should center all the values around netural so the absolute value fro neutral of the postive-to-negative ratio for a word would indicate how much sentiment (positive or negative) that word conveys.
    When comparing absolute values it's easier to do that around zero than one.

To fix these issues, we'll convert all of our ratios to new values using logarithms.
In the end, extremely positive and extremely negative words will have positive-to-negative ratios with similar magnitudes but opposite signs.

## 3. Transforming Text into Numbers

### Creating the Input/Output Data
Created a set named vocab that contains every word in the vocabulary.
 
 
 
 
 
