---
title: Exploring Shannon's Prediction And Entropy Of Printed English Paper
date: 2016-03-29 00:00:00
tags:
  - Exploring
  - Natural Language Processing
---
Tried and mostly failing to replicate the results from [Shannon's paper](http://languagelog.ldc.upenn.edu/myl/Shannon1950.pdf) using War and Peace as a stand in for "The English Language".

I say mostly because I'm pretty sure I am measuring the entropy measurements for different length n-grams in the English language but it turns out I'm calculating isolated symbols entropy while Shannon is calculating conditional n-gram entropy.
[Helpful SO answer](https://stackoverflow.com/questions/9604460/how-to-find-out-the-entropy-of-the-english-language)

I did get interesting results for the top 10 unigrams and bigrams:

| Unigram | Probability |
| - | - | 
| [ ] | 0.1826038 |
| [e] | 0.1017603 |
| [t] | 0.07308632 |
| [a] | 0.06643674 |
| [o] | 0.06226344 |
| [n] | 0.05945337 |
| [i] | 0.05626013 |
| [h] | 0.05403983 |
| [s] | 0.05258396 |
| [r] | 0.04791417 |

| Bigram | Probability |
| - | - | 
| [e ] | 0.03586495 |
| [ t] | 0.02825758 |
| [d ] | 0.02448941 |
| [he] | 0.02429185 |
| [th] | 0.02381377 |
| [ a] | 0.02245183 |
| [s ] | 0.02028996 |
| [t ] | 0.01880665 |
| [ h] | 0.01607567 |
| [in] | 0.01563341 |

[Source Code](https://github.com/DForshner/CSharpExperiments/blob/master/ShannonPredictionAndEntropyOfPrintedEnglish.cs)