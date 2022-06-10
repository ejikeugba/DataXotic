---
title: "Amazon Kindle Store Reviews Sentiment Analysis"
date: 2018-11-18T12:33:46+10:00
draft: false
weight: 1
heroHeading: "Amazon Kindle Store Reviews"
heroSubHeading: "Sentiment analysis."
heroBackground: "./images/backgpic.jpg"
thumbnail: "./images/amazonKindle2.jpg" 
---

Amazon\'s e-commerce platform is one of the biggest online shopping platforms globally. Considering its large customer base with an unprecedented amount of data on user experience, trying to summarize or understand the underlying pattern of available reviews could be a very daunting task.

Sentiment analysis or opinion mining provides an analytical procedure for extracting the hidden polarities in a given body of text. It offers a powerful tool for detecting the nature of opinion reflected in documents, websites, social media feeds, etc.

This project considers a dataset of product reviews from the Amazon Kindle Store category from May 1996 to July 2014. The dataset was assessed from Kaggle and contains a total of 982619 entries. Sentiment analysis of the customers' reviews was conducted in R using the tidytext and other relevant packages.

![PolarityScore.png](/project/sentiment/whitespace.png)

#### Pre-processing:

First, the corpus of interest was subjected to thorough cleansing using the standard pre-processing functions. For instance, the character vectors of the kindle review were turned into a text source using VectorSource() and were subsequently turned into a corpus using VCorpus(). With the help of cleaning functions like removePunctuation(), stripWhitespace() and replace_abbreviation(), the unwanted characters in the corpus were all removed.

&nbsp;

#### Sentiment scores:

After applying the tidy operation on the corpus such that each row contains a single word. The polarity scores of the unique words in the corpus were obtained. These were visualized based on their corresponding positive and negative scores (see Fig. 1 & 2). As observed, the reviews seem dominated by positive sentiments.

&nbsp;

![PolarityScore.png](/project/sentiment/PolarityScore.png)
![PolarityScore.png](/project/sentiment/whitespace.png)
![PolarityScore.png](/project/sentiment/wordFrequencies.png)

&nbsp;

#### Polarity curve:

To understand the pattern of customers' sentiments over time, a plot of the chronological polarities of the customer's reviews was obtained. This was achieved with the GAM smoothing method in the ggplot2 package. As observed in Figure 3, sentiment tracking over time shows a decreasing trend between 2000 and 2010 and an increase from 2010 to 2015. There was also an increase in the precision of estimates over time.

![PolarityScore.png](/project/sentiment/whitespace.png)

![PolarityScore.png](/project/sentiment/chronologicalPol.png)

&nbsp;

#### Lexical analyzer:

We further employed the "bing", "afnn" and "nrc" lexicons to implement filter() over the texts. Bing dichotomises sentiments into positive and negative. Words in the corpus with strong (green) and poor (red) polarities are visualized in a word cloud (Figure 4). Some top positive Words include: book, read, great, love, enjoyed, story and others.

![PolarityScore.png](/project/sentiment/whitespace.png)

![PolarityScore.png](/project/sentiment/cloudplot1.png)

&nbsp;

The afinn lexicon captures sentiments based on numeric values from 5 to -5. Obtained results are shown in Figure 5, with affin scores grouped based on the numerical ratings in the kindle store reviews (1 to 5). As expected, poor ratings are averagely associated with negative words, while good reviews correspond with positive words.

&nbsp;

![PolarityScore.png](/project/sentiment/boxplotAfinn.png)

The nrc lexicon labels words across multiple emotional states. In this particular instance, words in the review were tagged using the Plutchik's wheel of emotion. These are visualized in figures 6, 7 and 8. As observed, anticipation, joy and trust were the strongest sentiments in the review.

![PolarityScore.png](/project/sentiment/whitespace.png)

![PolarityScore.png](/project/sentiment/cloudplot2.png)

&nbsp;

![PolarityScore.png](/project/sentiment/plutchikSentiments.png)

&nbsp;

![PolarityScore.png](/project/sentiment/radarPlot.png)

![PolarityScore.png](/project/sentiment/whitespace.png)
![PolarityScore.png](/project/sentiment/whitespace.png)

#### Summary:

In summary, customer reviews of the Amazon kindle store category yielded impressively positive results. The top positive words in Plutchik's wheel of emotion include anticipation, joy and trust. Nevertheless, the chronological polarities of reviewers' sentiments shows a decrease in measure over a decade of time and a subsequent improvement afterwards. Moreover, it was observed that lower numerical ratings were associated with negative sentiments, while higher ratings were associated with positive sentiments.
