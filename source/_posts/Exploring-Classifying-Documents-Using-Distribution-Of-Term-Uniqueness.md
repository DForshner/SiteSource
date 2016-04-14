---
title: Exploring Classifying Documents Using Distribution Of Term Probabilities
date: 2016-04-07 00:00:00
tags:
- Natural Language Processing
- Exploring
---
I'm looking a way to classify product listings as either a product or a product accessory.  My current idea is to classify listings based on how their term probabilities are distributed.

The idea is to find the probability of each term in a listing and use them to build a histogram to get an idea how the common and unique terms are distributed for a listing.

**Examples of common words**: camera, digital, zoom, optical, with, lcd, megapixel, lens, canon, black, and, mp, digitalkamera, cm, 27

**Examples of unique words**: rings, eb575152vu, i9000, galaxys, 1080mah, funtionality, bp511a, zs7, enel5, 1100mah, mll3, 228825, np20, negative, scanner

I'm assuming that a *typical* product listing generally has one model number (unique) and a bunch of common terms while an accessory listing usually has multiple model numbers.  If this is true it should be possible to classify a listing as either a product or a product accessory from the distribution of term probabilities.

From what I'm seeing so far, it seems to be possible to classify accessory listings that have a high ratio of unique terms.

*Note: I would have used a histogram graph but I couldn't get the google charts histogram to work with a custom scale.*

**Examples of product listings:**

*samsung sh100 142mp wifi digital camera with 5x optical zoom in silver 8gb accessory kit*
{% googlecharts ColumnChart 600 200 %}
  Term Probability Distribution
  {"legend": { "position": "none" }}
  "Probability", "Count", { role: 'style' }
  '50.0', 5, '#358452'
  '25.0', 0, '#358452'
  '12.05', 3, '#358452'
  '6.025', 2, '#358452'
  '3.0125', 1, '#358452'
  '1.05625', 1, '#358452'
  '0.7812', 1, '#358452'
  '0.3906', 2, '#358452'
  '0.1953', 0, '#358452'
  '0.0976', 0, '#358452'
  '0.0488', 0, '#358452'
  '0.0244', 0, '#358452'
  '0.0122', 0, '#358452'
  '0.0061', 0, '#358452'
  '0.0003', 0, '#358452'
{% endgooglecharts %}

*canon eos rebel t3i 18 mp cmos digital slr camera and digic 4 imaging body only*
{% googlecharts ColumnChart 600 200 %}
  Term Probability Distribution
  {"legend": { "position": "none" }}
  "Probability", "Count", { role: 'style' }
  '50.0', 2, '#358452'
  '25.0', 1, '#358452'
  '12.05', 3, '#358452'
  '6.025', 1, '#358452'
  '3.0125', 4, '#358452'
  '1.05625', 2, '#358452'
  '0.7812', 0, '#358452'
  '0.3906', 1, '#358452'
  '0.1953', 0, '#358452'
  '0.0976', 1, '#358452'
  '0.0488', 1, '#358452'
  '0.0244', 0, '#358452'
  '0.0122', 0, '#358452'
  '0.0061', 0, '#358452'
  '0.0003', 0, '#358452'
{% endgooglecharts %}

**Examples of accessory listings:**

*310 digital camera video mask now rated to 65 feet*)
{% googlecharts ColumnChart 600 200 %}
  Term Probability Distribution
  {"legend": { "position": "none" }}
  "Probability", "Count", { role: 'style' }
  '50.0', 0, '#B65C49'
  '25.0', 2, '#B65C49'
  '12.05', 0, '#B65C49'
  '6.025', 0, '#B65C49'
  '3.0125', 0, '#B65C49'
  '1.05625', 0, '#B65C49'
  '0.7812', 1, '#B65C49'
  '0.3906', 0, '#B65C49'
  '0.1953', 1, '#B65C49'
  '0.0976', 2, '#B65C49'
  '0.0488', 0, '#B65C49'
  '0.0244', 0, '#B65C49'
  '0.0122', 1, '#B65C49'
  '0.0061', 0, '#B65C49'
  '0.0003', 3, '#B65C49'
{% endgooglecharts %}

*optekas extreme travelers essentials kit by opteka package inlcudes excursion series c900 fullsize waterproof canvas bag 6501300mm and 500mm telephoto lenses heavy duty tripod and monopod and much more for pentax k10d k20d k100d k110d k200d ist digital slr cameras*
{% googlecharts ColumnChart 600 200 %}
  Term Probability Distribution
  {"legend": { "position": "none" }}
  "Probability", "Count", { role: 'style' }
  '50.0', 0, '#B65C49'
  '25.0', 1, '#B65C49'
  '12.05', 0, '#B65C49'
  '6.025', 5, '#B65C49'
  '3.0125', 1, '#B65C49'
  '1.05625', 2, '#B65C49'
  '0.7812', 5, '#B65C49'
  '0.3906', 1, '#B65C49'
  '0.1953', 4, '#B65C49'
  '0.0976', 1, '#B65C49'
  '0.0488', 9, '#B65C49'
  '0.0244', 3, '#B65C49'
  '0.0122', 5, '#B65C49'
  '0.0061', 3, '#B65C49'
  '0.0003', 0, '#B65C49'
{% endgooglecharts %}

I had to use a nonlinear scale (I used powers of 2) for the histogram buckets or all the unique (small probability) words ended up in the same bucket.

There is a high rate of false positives (products being identified as accessories) when the listings are in languages other than English.  With so few non-English listings every word in these listings is unique across all listings.  It may be possible to figure out what language the listings are by using identifying listings which have unusual character n-grams distributions but I don't now if there will be enough text per listing to do this reliably.

*jendigital jd 5200 z3 digitalkamera 50 2560 x 1920 32mb*
{% googlecharts ColumnChart 600 200 %}
  Term Probability Distribution
  {"legend": { "position": "none" }}
  "Probability", "Count", { role: 'style' }
  '50.0', 0, '#B65C49'
  '25.0', 0, '#B65C49'
  '12.05', 0, '#B65C49'
  '6.025', 0, '#B65C49'
  '3.0125', 2, '#B65C49'
  '1.05625', 1, '#B65C49'
  '0.7812', 1, '#B65C49'
  '0.3906', 0, '#B65C49'
  '0.1953', 0, '#B65C49'
  '0.0976', 0, '#B65C49'
  '0.0488', 1, '#B65C49'
  '0.0244', 1, '#B65C49'
  '0.0122', 2, '#B65C49'
  '0.0061', 0, '#B65C49'
  '0.0003', 0, '#B65C49'
{% endgooglecharts %}

[The messy code](https://github.com/DForshner/CSharpExperiments/blob/master/ClassifyingDocumentsUsingDistributionOfTermUniqueness.cs)