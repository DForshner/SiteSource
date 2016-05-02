---
title: Exploring Finding Entity Aliases Using N-Gram Similarity
date: 2016-05-01 00:00:00
tags:
- Exploring
- Natural Language Processing
---
This is my second attempt at generating entity aliases from a set of product listings.  In my [first attempt](/2016/04/11/Exploring-Finding-Entity-Aliases-Using-MinHash-Approximate-Similarity/) I tried to use MinHash to group similar product listings, but it didn't work out.  This time, I'm going to be joining on n-grams of the manufacturer name and model number and then scoring the joins by the inverse term probability of the model n-grams.

I'm planning to use this in a pre-processing stage so that when I block by canonical manufacturer names I can include listings that have different variations of the canonical name.

For each listing, I'm attempting to find a *similar* canonical product record.  The criteria I'm using for something being similar are:
1. Similar manufacture using character n-gram similarity
2. Similar model using shingles made from model parts

If I find enough instances where a listing is similar to a canonical product, I'll consider the listing's manufacturer name to be an alias for the canonical product's manufacturer name.

Here are some aliases I was able to find:

| Canonical | Alias |
| - | - |
| fujifilm | fuji |
| kodak | eastman kodak company |
| canon | canon canada |
| fujifilm | fujifilm electronic imaging europe gmbh firstorder |
| panasonic | panasonic deutschland gmbh |
| sony | sony uk consumer electronics instock account |
| fujifilm| fuji photo film europe gmbh |
| fujifilm | fujifilm imaging systems |
| kodak | kodak stock account |
| fujifilm | fujifilm canada |
| canon | canon uk ltd |
| olympus | olympus canada |

My main goal was to relate listings with a manufacturer of **fuji** to **fujifilm** so it looks like this is going to work.  I had to change the scoring method to use the inverse term probably because some of the model names have common numbers or words *(ex: "zoom")* which caused lots of false positives.

[Messy Source Code](https://github.com/DForshner/CSharpExperiments/blob/master/AliasGenerationBySimilarManufacturerAndModel.cs)