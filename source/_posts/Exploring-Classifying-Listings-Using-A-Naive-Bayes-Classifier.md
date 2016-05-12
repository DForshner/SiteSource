---
title: Exploring Classifying Listings Using A Naive Bayes Classifier
date: 2016-05-06 00:00:00
tags:
- Exploring
- Machine Learning
---
I built a Naive Bayes classifier listings as being either for a camera or an accessory.  To generate the training set, I'm using a heuristic classifier I developed earlier and then going through the results manually.

Steps to run:
1) Create a preliminary training set using a heuristic based classifier.  Only a randomly selected subset of the listings should be used to build the training set. As there are far more camera listings than accessory listings, it's important to reflect that ratio in the training set.
2) Manually go through the training data to remove any entries.  Try to remove incorrect classifications in pairs to keep the ratio of camera listings to accessory listings the same.
3) Run the Bayes classifier using the training set you created.  To not be considered a camera a listing must contain more than 2 "accessory" words and more than 90% of the words need to be "camera" words.

*The +/- signs prepended to each term show how they contributed to a listing being classified as a camera*

**Positives:**

| Listing | Classification |
| - | - |
| +fujifilm +finepix +z70 +12 +mp +digital +camera +with +5x +optical +zoom +and +2 +7 +inch +lcd +bronze [Camera] | Camera |
| +pentax +k +x +12 +4 +mp +digital +slr +with +2 +7 +inch +lcd +and +18 +55mm +f +3 +5 +5 +6 +al +and +50 +200mm +f +4 +5 +6 +ed +lenses +black | Camera |
| +vivitar -vivicam vx029bl +10 +1mp +digital +camera +blue | Camera |
| +sony dsct2b +digital +camera +black +8 +1mp +3x +optical +zoom +2 +7 +lcd +4gb internal +memory | Camera |
| +agfaphoto +precisa 107 +digitalkamera +12 +megapixel +5 +fach +opt +zoom +6 +8 +cm +2 +7 +zoll +display +bildstabilisiert +schwarz | Camera |
|  lenco +dc 511 +digitalkamera +12 +megapixel +8 +fach +digital +zoom +6 +cm +2 +4 +zoll +tft +lcd +orange | Camera |

**Negatives:**

| Listing | Classification |
| - | - |
| -duragadget premium wrist +camera +carrying -strap +with +2 +year +warranty -for +panasonic +lumix -fh27 -fh25 -fp5 -fp7 -fh5 -fh2 -s3 +s1 | Accessory |
| cushioned neo absorption +camera -strap -for +nikon +canon +pentax +panasonic +olympus +fujifilm +kodak +sony +and +more +digital +slr -cameras +card +reader +included | Accessory |
| -sigmatek -ds 740 +7 +digital +photo -frame +black -ds -240 +2 +4 +mini +digital +photo -frame +2 -covers | Accessory |
| biostek -ds -240 +2 +4 +mini +digital +photo -frame +2 -covers +cleaning -applicator -for +digital +photo -frames | Accessory |
| -fototasche -kameratasche -typ hardbox hellblau -set +mit +4 +gb +sd -karte -für +samsung st60 es55 es60 +es65 es70  | Accessory |

**False positives:**

| Listing | Classification |
| - | - |
| kingston kingston valueram 512 mo ddr sdram pc3200 cas3 wet wipe dispenser +100 wipes dust removal spray +250 ml foam -cleaner -for screens +and keyboards +150 ml | Camera |
| -duragadget +deluxe +mini flat folding +camera +camcorder +tripod stand -for +canon +ixus 1000hs +ixus 300hs +ixus +210 +ixus 200is +ixus 130 +ixus 120is | Camera |

[Source Code](https://github.com/DForshner/CSharpExperiments/blob/master/NaiveBayesCameraListingClassifier.cs)