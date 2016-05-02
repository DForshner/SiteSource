---
title: Text Mining with Twitter and R Meetup
date: 2016-04-29 00:00:00
tags:
- Natural Language Processing
- Meetup
---
A follow along workshop on using R to do data mining on tweets.

**Notes**
* Data pipeline: **E**xtract → **C**lean → **T**ransform → **A**nalyize
* Clean
  * Remove: Unicode emoji, punctuation, links, stop words, numbers, dates, URLs, white space
  * Normalize to lowercase
  * <u>Stemming</u> - Truncate words to their radicals
    * Examples: cats → cat, ponies → poni
* Analysis
  * <u>Part of speech tagging</u> - Tag each word with its part of speech in a sentence using definition and context.
    * Example: They refuse to permit -> [pronoun] [verb] [to] [verb]
  * <u>Word association</u> - Dot product of two words in a term document matrix gives correlation coefficient.
  * <u>Clustering</u> - Grouping similar tweets(docs) together
    * <u>K-means</u> - Centroidal model, each cluster is represented by a single mean vector.
      * Algorithm: create random clusters → assign points to nearest cluster centroid → recalculate cluster centroids to the average of assigned data points → repeat.
    * <u>Hierarchical</u> - Connectivity model
    * Use cosine similarity as the distance function.  Cosine similarity normalizes for tweet(doc) length during the comparison.
  * <u>Topic Mining</u> - Use probability of terms to discover information from documents.  Documents may belong to multiple topics.

*Word association example:*

| Docs | word 1 | word 2 | word 3 | word 4 |
| - | - | - | - |
| 1 | 0 | 0 | 0 | 0 |
| 2 | 1 | 0 | 0 | 0 |
| 3 | 1 | 1 | 0 | 0 |
| 4 | 1 | 1 | 1 | 1 |
Correlation(word 2, word 3) = DotProduct([1,0,0,0], [1,1,0,0]) = 0.5

[Meetup Event](http://www.meetup.com/Waterloo-Data-Science/events/230320500/)