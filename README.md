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
Take a look at the following image. It represents the layers of the neural network you'll be building throughout this notebook. layer_0 is the input layer, layer_1 is a hidden layer, and layer_2 is the output layer.


![IMG2](https://github.com/Ratna04priya/Sentiment-Classification-Analysis/blob/master/sentiment_network_2.png)

Now, Created a numpy array called layer_0 and initialize it to all zeros. You will find the zeros function particularly helpful here. Be sure you create layer_0 as a 2-dimensional matrix with 1 row and vocab_size columns.
 
 layer_0 contains one entry for every word in the vocabulary, as shown in the above image. We need to make sure we know the index of each word, so run the following cell to create a lookup table that stores the index of every word.
 
 ![IMG2](https://github.com/Ratna04priya/Sentiment-Classification-Analysis/blob/master/sentiment_network.png)
 
 Now, the implementation of update_input_layer. It should count how many times each word is used in the given review, and then store those counts at the appropriate indices inside layer_0.
 
 ## 4. Building a Network
 We've included the framework of a class called SentimentNetork. Implement all of the items marked TODO in the code. These include doing the following:

 1. Create a basic neural network much like the networks you've seen in earlier lessons and in Project 1, with an input layer, a hidden layer, and an output layer.
    
2.  Do not add a non-linearity in the hidden layer. That is, do not use an activation function when calculating the hidden layer outputs.
    
3.  Re-use the code from earlier in this notebook to create the training data (see TODOs in the code)
    Implement the pre_process_data function to create the vocabulary for our training data generating functions
    Ensure train trains over the entire corpus

## 5. Understanding Neural Noise
We've included it here so you can run the cells along with the video without having to type in everything.


## 6. Reducing Noise in Our Input Data
 Specifically, do the following:

    Copy the SentimentNetwork class you created earlier into the following cell.
    Modify update_input_layer so it does not count how many times each word is used,
    but rather just stores whether or not a word was used.
    
## 7. Analyzing Inefficiencies in our Network

![IMG3](https://github.com/Ratna04priya/Sentiment-Classification-Analysis/blob/master/sentiment_network_sparse.png)

![IMG4](https://github.com/Ratna04priya/Sentiment-Classification-Analysis/blob/master/sentiment_network_sparse_2.png)

## 8. Making our Network More Efficient

Make the SentimentNetwork class more efficient by eliminating unnecessary multiplications and additions that occur during forward and backward propagation. 

## 9. Reducing Noise by Strategically Reducing the Vocabulary

Improve SentimentNetwork's performance by reducing more noise in the vocabulary. Specifically, do the following:

    Copy the SentimentNetwork class from the previous project into the following cell
    Modify pre_process_data:
    
## 10. Analysis of Data

To see "What's Going on in the Weights?".


 
