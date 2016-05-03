---
title: "Working Out Bayes' Theorem"
date: 2014-05-03 00:00:00
tags:
- Random
- Math
---
*This is mostly an excuse to play around with the MathJax library*

{% img /images/BayesDemo.png 200 200 %}

$Num(A) = 50$
$Num(B) = 15$
$Num(A∩B) = 5$
$Num(A∪B) = 65$

Get probabilities from counts
$P(A) = \frac{50}{65} \approx 0.769$
$P(B) = \frac{15}{65} \approx 0.231$
$P(A∩B) = \frac{5}{65} \approx 0.0769$

Get conditional probabilities from counts
$P(A|B) = \frac{Num(A∩B)}{Num(B)} = \frac{5}{15} \approx 0.333$
$P(B|A) = \frac{Num(A∩B)}{Num(A)} = \frac{5}{65} \approx 0.077$

Use the above to get counts from probabilities
$Num(A) = P(A) \times Num(A∪B) = \frac{0.769}{65} = 50$
$Num(B) = P(B) \times Num(A∪B) = \frac{0.231}{65} = 15$
$Num(A∩B) = P(A|B) \times Num(B) = \frac{0.333}{15} = 5$
$Num(A∩B) = P(B|A) \times Num(A) = \frac{0.077}{65} = 5$

Turn counts into probabilities to get the conditional probability from other probabilities
$P(A|B) = \frac{Num(A∩B)}{Num(B)}$
$P(A|B) = \frac{P(B|A) \times Num(A)}{P(B) \times Num(A∪B)}$
$P(A|B) = \frac{P(B|A) \times P(A) \times Num(A∪B)}{P(B) \times Num(A∪B)}$

$Bayes' Theorem = P(A|B) = \frac{P(B|A) \times P(A)}{P(B)}$