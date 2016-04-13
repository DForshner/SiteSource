---
title: Exploring Finding Entity Aliases Using MinHash Approximate Similarity
date: 2016-04-12 00:00:00
tags:
  - Exploring
  - Failure
  - Natural Language Processing
---
I'm trying to generate a list of aliases for entities by finding similar documents that have different entity names as attributes.  Assuming that an entity has multiple similar documents associated with it that are listed under its different aliases I should be able to generate a set of aliases by grouping similar documents together.

The data I'm working with has multiple versions of the same manufacturer.

| Manufacturer | Listing Text |
| - | - |
| Fujifilm Canada | Fujifilm FinePix JV100 12 MP Digital Camera with 3x Optical Zoom and 2.7-Inch LCD (Black) |
| FUJIFILM | Fujifilm FinePix XP10 12 MP Waterproof Digital Camera with 5x Optical Zoom and 2.7-Inch LCD (Black) |
| Fujifilm Imaging Systems | Fujifilm Finepix Z700EXR Digitalkamera (12 Megapixel, 5-fach opt.Zoom, 8,9 cm Display, Bildstabilisator) silber |
| FUJIFILM Electronic Imaging Europe GmbH - Firstorder | Fujifilm FINEPIX Z90 Digitalkamera (14 Megapixel, 5-fach opt. Zoom, 7,6 cm (3 Zoll) Display) silber |
| Fuji Photo Film Europe GmbH | Fujifilm FINEPIX JX280 Digitalkamera (14 Megapixel, 5-fach opt. Zoom, 6,9 cm (2,7 Zoll) Display) schwarz |

While these are all Finepix listings the manufacture name is different for each one.  This prevents me from blocking on the manufacturer's name as a first stage when matching products to listings.

I tried using the [MinHash](https://en.wikipedia.org/wiki/MinHash) technique to find approximately similar documents but I don't think there's enough text per listing to get a good join.  Using only unique tokens to generate the min hashes helped but I'm getting too many false negatives on the Fuji listings for this to be useful.

Next, I'm going to generate n-grams using model numbers from the products file and doing a plain old [Jaccard similarity coefficient](https://en.wikipedia.org/wiki/Jaccard_index) instead.  Hopefully, that can let me group listings for the same model together.

I'll  probably come back to this code and try using it for another problem with long texts.  The examples of MinHash I've seen are on longer documents where they use shingles(n-grams where n > 1) instead of just unigrams.

[Messy Source Code](https://github.com/DForshner/CSharpExperiments/blob/master/FindingEntityAliasesUsingMinHashApproximateDocumentSimilarity.cs)